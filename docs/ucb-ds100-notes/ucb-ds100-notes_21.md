# 二十、SQL I

> 原文：[SQL I](https://ds100.org/course-notes/sql_I/sql_I.html)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

*学习成果*

+   确定数据库可能优于 CSV 文件的情况

+   使用`SELECT`，`FROM`，`WHERE`，`ORDER BY`，`LIMIT`和`OFFSET`编写基本的 SQL 查询

+   使用`GROUP BY`执行聚合操作

到目前为止，在本课程中，我们已经完成了整个数据科学生命周期：我们学会了如何加载和探索数据集，制定问题，并使用预测和推断工具得出答案。在本学期的剩余几周中，我们将再次经历整个生命周期，这次使用不同的工具、思想和抽象。

## 20.1 数据库

有了这个目标，让我们回到生命周期的最开始。我们首先通过查看`pandas`库开始了数据分析工作，该库为我们提供了强大的工具，用于操作（主要是）CSV 文件中存储的表格数据。在研究和工业领域，数据科学家经常需要访问无法轻松存储在 CSV 格式中的大量数据。与他人合作处理 CSV 数据也可能会很棘手-真实世界的数据科学家可能会在多个用户尝试进行修改时遇到问题，或者更糟的是，数据应该由谁访问和谁不应该访问的安全问题。

**数据库**是一个大型的、有组织的数据集合。数据库由**数据库管理系统（DBMS）**管理，这是一种存储、管理和促进访问一个或多个数据库的软件系统。数据库有助于减轻使用 CSV 进行数据存储时出现的许多问题：它们提供可靠的存储，可以在系统崩溃或磁盘故障时幸存，被优化用于计算无法适应内存的数据，并包含特殊的数据结构以提高性能。使用数据库而不是 CSV 还可以从数据管理的角度获得进一步的好处。DBMS 可以应用设置来配置数据的组织方式，阻止某些数据异常（例如，强制执行非负权重或年龄），并确定谁有权访问数据。它还可以确保安全的并发操作，其中多个用户读取和写入数据库不会导致致命错误。

正如您可能已经猜到的那样，我们无法使用通常的`pandas`方法来处理数据库中的数据。相反，我们将转向结构化查询语言。

## 20.2 结构化查询语言和数据库模式

**结构化查询语言**，或**SQL**（通常发音为“sequel”，尽管这是[激烈辩论的话题](https://patorjk.com/blog/2012/01/26/pronouncing-sql-s-q-l-or-sequel/)），是一种专门设计用于与数据库通信的编程语言。您可能在 CS 61A 或 Data C88C 等课程中遇到过它。与 Python 不同，它是一种**声明性编程语言** - 这意味着与编写完成任务所需的确切逻辑不同，SQL 代码的一部分“声明”了所需的最终输出应该是什么，并且让程序确定应该实现什么逻辑。

重申一点，SQL 是一种与 Python 完全不同的语言。但是，Python 确实有特殊的引擎，允许我们在 Jupyter 笔记本中运行 SQL 代码。虽然这通常不是 SQL 在教育环境之外的使用方式，但我们将使用这种工作流程来说明如何使用我们本学期已经使用过的工具构建 SQL 查询。您将在实验 10 中了解如何在 Jupyter 中运行 SQL 查询。

下面的语法对您来说可能会很陌生；现在，只需专注于理解显示的输出。我们将稍后澄清 SQL 代码。

首先，我们将查看一个名为`basic_examples.db`的数据库。

```py
# Load the SQL Alchemy Python library
import sqlalchemy
import pandas as pd
```

```py
# load %%sql cell magic
%load_ext sql
```

连接到 SQLite 数据库`basic_examples.db`。

```py
%%sql
sqlite:///data/basic_examples.db 
```

```py
%%sql
SELECT * 
FROM sqlite_master
WHERE type="table"
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| type | Name | tbl_name | rootpage | sql |
| --- | --- | --- | --- | --- |
| table | sqlite_sequence | sqlite_sequence | 7 | `CREATE TABLE sqlite_sequence(name,seq)` |
| table | Dragon | Dragon | 2 | `CREATE TABLE Dragon (` |
| | | | |  `name TEXT PRIMARY KEY,` |
| | | | |  `year INTEGER CHECK (year >= 2000),` |
| | | | |  `cute INTEGER` |
| | | | |  `)`|
| table | Dish | Dish | 4 | `CREATE TABLE Dish (` |
| | | | |  `name TEXT PRIMARY KEY,` |
| | | | |  `type TEXT,` |
| | | | |  `cost INTEGER CHECK (cost >= 0)` |
| | | | |  `)` |
| table | Scene | Scene | 6 | `CREATE TABLE Scene (` |
| | | | |  `id INTEGER PRIMARY KEY AUTOINCREMENT,` |
| | | | |  `biome TEXT NOT NULL,` |
| | | | |  `city TEXT NOT NULL,` |
| | | | |  `visitors INTEGER CHECK (visitors >= 0),` |
| | | | |  `created_at DATETIME DEFAULT (DATETIME('now'))` |
| | | | |  `)` |

上面的摘要显示了有关数据库的信息。数据库包含四个表，名称分别为`sqlite_sequence`、`Dragon`、`Dish`和`Scene`。上面最右边的列列出了用于构造每个表的命令。

让我们更仔细地看一下用于创建`Dragon`表的命令（上面的第二个条目）。

```py
CREATE TABLE Dragon (name TEXT PRIMARY KEY,
                     year INTEGER CHECK (year >= 2000),
                     cute INTEGER)
```

语句`CREATE TABLE`用于指定表的**模式**-表的组织逻辑的描述。模式遵循一组格式：

+   `ColName`：列的名称

+   `DataType`：要存储在列中的数据类型。一些最常见的 SQL 数据类型是`INT`（整数）、`FLOAT`（浮点数）、`TEXT`（字符串）、`BLOB`（任意数据，如音频/视频文件）和`DATETIME`（日期和时间）。

+   “约束”：对要存储在列中的数据的一些限制。常见的约束有`CHECK`（数据必须遵守某个条件）、`PRIMARY KEY`（指定列为表的主键）、`NOT NULL`（数据不能为空）和`DEFAULT`（如果没有给定特定条目，则为默认填充值）。

我们看到`Dragon`包含三列。其中第一列“名称”包含文本数据。它被指定为表的**主键**；也就是说，“名称”中包含的数据唯一标识表中的每个条目。因为“名称”是表的主键，表中的两个条目不能具有相同的名称-“名称”的给定值对于每个龙是唯一的。列“年份”包含整数数据，约束条件是年份值必须大于或等于 2000。最后一列“可爱”包含整数数据，没有对允许的值施加限制。

我们可以通过查看`Dragon`本身来验证这一点。

```py
%%sql
SELECT *
FROM Dragon
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| hiccup | 2010 | 10 |
| drogon | 2011 | -100 |
| drogon 2 | 2019 | 0 |

数据库表（也称为**关系**）的结构与`pandas`中的`DataFrame`非常相似。每一行，有时称为**元组**，代表数据集中的单个记录。每一列，有时称为**属性**或**字段**，描述记录的某些特征。

## 20.3 从表中选择

为了提取和操作存储在 SQL 表中的数据，我们需要熟悉编写 SQL 代码片段的语法，我们称之为**查询**。

SQL 查询的基本单元是`SELECT`语句。`SELECT`指定我们想要从给定表中提取哪些列。我们使用`FROM`告诉 SQL 我们想要从哪个表中`SELECT`我们的数据。

```py
%%sql
SELECT *
FROM Dragon
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| hiccup | 2010 | 10 |
| drogon | 2011 | -100 |
| drogon 2 | 2019 | 0 |

在 SQL 中，`*`表示“所有”。上面的查询抓取`Dragon`中的*所有*列，并在输出的表中显示它们。我们也可以指定要`SELECT`的特定列的子集。请注意，输出的列按照它们被`SELECT`的顺序出现。

```py
%%sql
SELECT cute, year
FROM Dragon
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Cute | Year |
| --- | --- |
| 10 | 2010 |
| -100 | 2011 |
| 0 | 2019 |

就像这样，我们已经编写了两个 SQL 查询。上面的查询中有一些要注意的地方。首先，请注意每个“动词”都是大写写的。按照惯例，SQL 操作应以大写字母编写，但即使您选择保持小写，您的代码也会正常运行。其次，上面的查询将每个语句与新行分隔开。SQL 查询不受查询内部的空格影响；这意味着 SQL 代码通常是在每个语句后写上新行，以使其更易读。分号（`;`）表示查询的结束。在某些 SQL“风味”中，如果没有分号，查询将无法运行；但是，在 Data 100 中，我们将使用的 SQL 版本无论是否有结束分号都可以正常运行。这些笔记中的查询将以分号结束，以养成良好的习惯。

`AS`关键字允许我们在`SELECT`后为列指定一个新名称（称为**别名**）。一般语法是：

```py
SELECT column_name_in_database_table AS new_name_in_output_table
```

```py
%%sql
SELECT cute AS cuteness, year AS birth
FROM Dragon
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| cuteness | birth |
| --- | --- |
| 10 | 2010 |
| -100 | 2011 |
| 0 | 2019 |

要仅`SELECT`列中的*唯一*值，我们使用`DISTINCT`关键字。这将导致列中的任何重复条目被删除。如果我们只想找到`Dragon`中唯一的年份，而没有任何重复，我们将写：

```py
%%sql
SELECT DISTINCT year
FROM Dragon
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Year |
| --- |
| 2010 |
| 2011 |
| 2019 |

每个 SQL 查询必须包括`SELECT`和`FROM`语句。直观地说，这是有道理的 - 我们知道我们将要从表中提取一些信息；为了这样做，我们还需要指示我们要考虑哪个表。

重要的是要注意，SQL 强制执行严格的“操作顺序” - SQL 子句必须*始终*遵循相同的顺序。例如，`SELECT`语句必须始终在`FROM`之前。这意味着任何 SQL 查询都将遵循相同的结构。

```py
SELECT <column list>
FROM <table>
[additional clauses]
```

我们使用的附加子句取决于要实现的具体任务。我们可以通过细化查询来过滤特定条件，聚合特定列或将多个表连接在一起。我们将在本讲座的其余时间中概述一些有用的子句，以增进我们对操作顺序的理解。

## 20.4 应用`WHERE`条件

`WHERE`关键字用于仅选择表的某些行，这些行基于给定的布尔条件进行过滤。

```py
%%sql
SELECT name, year
FROM Dragon
WHERE cute > 0
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year |
| --- | --- |
| hiccup | 2010 | 

我们可以使用`AND`，`OR`和`NOT`关键字给`WHERE`条件添加复杂性，就像在 Python 中一样。

```py
%%sql
SELECT name, year
FROM Dragon
WHERE cute > 0 OR year > 2013
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year |
| --- | --- |
| hiccup | 2010 |
| drogon 2 | 2019 |

为了避免需要通过组合多个条件来编写复杂的逻辑表达式，我们还可以过滤`IN`指定值列表中的条目。这类似于 Python 中的`in`或`.isin`的用法。

```py
%%sql
SELECT name, year
FROM Dragon
WHERE name IN ("hiccup", "puff")
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year |
| --- | --- |
| hiccup | 2010 |

您可能已经注意到我们的表实际上缺少一个值。在 SQL 中，缺失的数据被赋予特殊值`NULL`。`NULL`的行为方式与其他数据类型根本不同。我们不能对`NULL`值使用典型的运算符（=，>和<）（实际上，`NULL == NULL`返回`False`！）；相反，我们检查值是否为`NULL`或`NULL`。

```py
%%sql
SELECT *
FROM Dragon
WHERE cute IS NOT NULL
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| hiccup | 2010 | 10 |
| drogon | 2011 | -100 |
| drogon 2 | 2019 | 0 |

## 20.5 排序和限制输出

如果我们希望输出表按特定顺序显示，`ORDER BY`关键字的行为类似于`pandas`中的`.sort_values()`。

```py
%%sql
SELECT *
FROM Dragon
ORDER BY cute
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| drogon | 2011 | -100 |
| drogon 2 | 2019 | 0 |
| hiccup | 2010 | 10 |

默认情况下，`ORDER BY`将按升序显示结果（最小值在表的顶部）。要按降序排序，我们在指定用于排序的列后使用`DESC`关键字。

```py
%%sql
SELECT *
FROM Dragon
ORDER BY cute DESC
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| hiccup | 2010 | 10 |
| drogon 2 | 2019 | 0 |
| drogon | 2011 | -100 |

我们还可以告诉 SQL 同时按两列`ORDER BY`。这将按照列出的第一列对表进行排序，然后使用第二列中的值来打破任何平局。

```py
%%sql
SELECT *
FROM Dragon
ORDER BY name, cute
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| drogon 2 | 2019 | 0 |
| drogon | 2011 | -100 |
| hiccup | 2010 | 10 |

在许多情况下，我们只关心输出表中的某些行（例如，想要找到表中的前两条龙）。`LIMIT`关键字将输出限制为指定数量的行。它的功能类似于`pandas`中的`.head()`。

```py
%%sql
SELECT *
FROM Dragon
LIMIT 2
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| hiccup | 2010 | 10 |
| drogon | 2011 | -100 |

`OFFSET`关键字表示`LIMIT`应该开始的索引。换句话说，我们可以使用`OFFSET`来将`LIMIT`的开始位置向后移动指定数量的行。例如，我们可能关心表中位置为#2 和#3 的龙。

```py
%%sql
SELECT *
FROM Dragon
LIMIT 2
OFFSET 1
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | Year | Cute |
| --- | --- | --- |
| drogon | 2011 | -100 |
| drogon 2 | 2019 | 0 |

让我们总结一下到目前为止我们学到的东西。我们知道`SELECT`和`FROM`是任何 SQL 查询的基本构建模块。我们可以使用其他子句来完善输出表中的数据。

我们包含的任何子句必须在查询中遵循严格的顺序：

```py
SELECT <column list>
FROM <table>
[WHERE <predicate>]
[ORDER BY <column list>]
[LIMIT <number of rows>]
[OFFSET <number of rows>]
```

在这里，方括号`[ ]`中包含的任何子句都是可选的 - 只有在与我们要执行的表操作相关时才需要使用关键字。还要注意，按照惯例，我们在 SQL 语句中使用大写字母表示关键字，并使用换行符使代码更易读。

## 20.6 使用`GROUP BY`进行聚合

到目前为止，我们已经看到 SQL 提供了与`pandas`给我们的许多相同功能。我们可以从表中提取数据，对其进行过滤和重新排序以满足我们的需求。

在`pandas`中，我们的许多分析工作在很大程度上依赖于能够使用`.groupby()`来对数据集的行进行聚合。SQL 对这一任务的回答是（非常方便地命名为）`GROUP BY`子句。虽然`GROUP BY`的输出与`.groupby()`的输出类似 - 在这两种情况下，我们都获得了一个输出表，其中某些列已被用于分组 - 但在 SQL 中用于分组数据的语法和逻辑与`pandas`的实现有相当大的不同。

为了说明`GROUP BY`，我们将考虑`basic_examples.db`数据库中的`Dish`表。

```py
%%sql
SELECT * 
FROM Dish
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Name | type | cost |
| --- | --- | --- |
| ravioli | entree | 10 |
| ramen | entree | 13 |
| taco | entree | 7 |
| edamame | appetizer | 4 |
| fries | appetizer | 4 |
| potsticker | appetizer | 4 |
| ice cream | dessert | 5 |

假设我们想要找到某种“类型”的菜肴的总成本。为了实现这一目标，我们将编写以下代码。

```py
%%sql
SELECT type, SUM(cost)
FROM Dish
GROUP BY type
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| type | SUM(cost) |
| --- | --- |
| appetizer | 12 |
| dessert | 5 |
| entree | 30 |

这里发生了什么？语句`GROUP BY type`告诉 SQL 根据`type`列中包含的值（记录是开胃菜、主菜还是甜点）对数据进行分组。`SUM(cost)`对每个`type`中的菜肴成本进行求和，并在输出表中显示结果。

你可能会想：为什么`SUM(cost)`在`GROUP BY type`命令之前？我们不需要在计算每个分组中的条目数量之前先形成分组吗？

请记住，SQL 是一种*声明性*编程语言 - SQL 程序员只需陈述他们想要看到的最终结果，然后将如何获得这个结果的任务留给 SQL 本身。这意味着 SQL 查询有时不遵循读者认为“逻辑”的思维顺序。相反，SQL 要求我们在构建查询时遵循其设定的操作顺序。只要我们遵循这个顺序，SQL 就会处理底层逻辑。

在实际操作中：我们这个查询的目标是输出每个“类型”的总成本。为了向 SQL 传达这一点，我们说我们要`SELECT`每个`type`组的`SUM`med`cost`值。

有许多聚合函数可以用来聚合每个组中包含的数据。一些常见的例子是：

+   `COUNT`: 计算与每个组相关联的行数

+   `MIN`: 找到每个组的最小值

+   `MAX`: 找到每个组的最大值

+   `SUM`: 对每个组中的所有记录求和

+   `AVG`: 找到每个组的平均值

我们可以轻松地一次性计算多个聚合（这在`pandas`中非常棘手）。

```py
%%sql
SELECT type, SUM(cost), MIN(cost), MAX(name)
FROM Dish
GROUP BY type
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| type | SUM(cost) | MIN(cost) | MAX(name) |
| --- | --- | --- | --- |
| appetizer | 12 | 4 | potsticker |
| dessert | 5 | 5 | ice cream |
| entree | 30 | 7 | taco |

要计算与每个组相关联的行数，我们使用`COUNT`关键字。调用`COUNT(*)`将计算每个组中的总行数，包括具有空值的行。它在`pandas`中的等价物是`.groupby().size()`。

```py
%%sql
SELECT type, COUNT(*)
FROM Dish
GROUP BY type
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| type | COUNT(*) |
| --- | --- |
| appetizer | 3 |
| dessert | 1 |
| entree | 3 |

在计算每个组中的行数时排除`NULL`值，我们在表中明确调用`COUNT`。这类似于在`pandas`中调用`.groupby().count()`。

```py
%%sql
SELECT year, COUNT(cute)
FROM Dragon
GROUP BY year
```

```py
 * sqlite:///data/basic_examples.db
Done.
```

| Year | COUNT(cute) |
| --- | --- |
| 2010 | 1 |
| 2011 | 1 |
| 2019 | 1 |

有了这个`GROUP BY`的定义，让我们更新一下我们的 SQL 操作顺序。记住：*每个*SQL 查询必须按照这个顺序列出子句。

```py
SELECT <column expression list>
FROM <table>
[WHERE <predicate>]
[GROUP BY <column list>]
[ORDER BY <column list>]
[LIMIT <number of rows>]
[OFFSET <number of rows>];
```

请注意，我们可以在选择过程中使用`AS`关键字重命名列，并且列表达式可以包括聚合函数（`MAX`，`MIN`等）。
