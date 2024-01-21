# 六、正则表达式

> 原文：[Regular Expressions](https://ds100.org/course-notes/regex/regex.html)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

*学习成果*

+   了解 Python 字符串操作，`pandas` `Series`方法

+   解析和创建正则表达式，使用参考表

+   使用词汇（闭包、元字符、组等）描述正则表达式元字符

**这些内容在第 6 和第 7 讲中涵盖。**

## 6.1 为什么处理文本？

上一堂课，我们了解了定量和定性变量类型之间的区别。后者包括字符串数据——第 6 讲的主要焦点。在本笔记中，我们将讨论操纵文本所需的工具：`python`字符串操作和正则表达式。

处理文本有两个主要原因。

1.  规范化：将具有多种格式的数据转换为标准形式。

    +   通过操纵文本，我们可以将具有不匹配字符串标签的表格连接起来。

1.  将信息提取到新特征中。

    +   例如，我们可以从文本中提取日期和时间特征。

## 6.2 Python 字符串方法

首先，我们将介绍一些有用的字符串操作方法。以下表格包括`python`和`pandas`支持的一些字符串操作。`python`函数操作单个字符串，而它们在`pandas`中的等效函数是**矢量化**的——它们操作字符串数据的`Series`。

| 操作 | Python | `Pandas` (`Series`) |
| --- | --- | --- |
| 转换 | `s.lower()` | `ser.str.lower()` |
| | `s.upper()` | `ser.str.upper()` |
| 替换 + 删除 | `s.replace(_)` | `ser.str.replace(_)` |
| 分割 | `s.split(_)` |  `ser.str.split(_)` |
| 子字符串 | `s[1:4]` | `ser.str[1:4]` |
| 成员资格 | `'_' in s` | `ser.str.contains(_)` |
| 长度 | `len(s)` | `ser.str.len()` |

我们将在规范化的下一节讨论`python`字符串函数和`pandas` `Series`方法之间的区别。

### 6.2.1 规范化

假设我们想要合并给定的表格。

代码

```py
import pandas as pd

with open('data/county_and_state.csv') as f:
 county_and_state = pd.read_csv(f)

with open('data/county_and_population.csv') as f:
 county_and_pop = pd.read_csv(f)
```

```py
display(county_and_state), display(county_and_pop);
```

|  | County | State |
| --- | --- | --- |
| 0 | De Witt County | IL |
| 1 | Lac qui Parle County | MN |
| 2 | Lewis and Clark County | MT |
| 3 | St John the Baptist Parish | LS |

|  | County | Population |
| --- | --- | --- |
| 0 | De Witt County | 16798 |
| 1 | Lac qui Parle County | 8067 |
| 2 | Lewis and Clark County | 55716 |
| 3 | St John the Baptist Parish | 43044 |

上次，我们使用**主键**和**外键**来连接两个表格。虽然这两个键都不存在于我们的`DataFrame`中，但是`"County"`列看起来足够相似。我们能否将这些列转换为一个标准的规范形式，以便合并这两个表格？

#### 6.2.1.1 使用`python`字符串操作进行规范化

以下函数使用`python`字符串操作将单个县名转换为规范形式。它通过消除空格、标点和不必要的文本来实现这一点。

```py
def canonicalize_county(county_name):
 return (
 county_name
 .lower()
 .replace(' ', '')
 .replace('&', 'and')
 .replace('.', '')
 .replace('county', '')
 .replace('parish', '')
 )

canonicalize_county("St. John the Baptist")
```

```py
'stjohnthebaptist'
```

我们将使用`pandas` `map`函数将`canonicalize_county`函数应用于每个`DataFrame`中的每一行。这样做，我们将在每个`DataFrame`中创建一个名为`clean_county_python`的新列，其中包含规范形式。

```py
county_and_pop['clean_county_python'] = county_and_pop['County'].map(canonicalize_county)
county_and_state['clean_county_python'] = county_and_state['County'].map(canonicalize_county)
display(county_and_state), display(county_and_pop);
```

|  | County | State | clean_county_python |
| --- | --- | --- | --- |
| 0 | De Witt County | IL | dewitt |
| 1 | Lac qui Parle County | MN | lacquiparle |
| 2 | Lewis and Clark County | MT | lewisandclark |
| 3 | St. John the Baptist | LS | stjohnthebaptist |

|  | County | Population | clean_county_python |
| --- | --- | --- | --- |
| 0 | De Witt County | 16798 | dewitt |
| 1 | Lac qui Parle County | 8067 | lacquiparle |
| 2 | Lewis and Clark County | 55716 | lewisandclark |
| 3 | St. John the Baptist | 43044 | stjohnthebaptist |

#### 6.2.1.2 使用 Pandas Series 方法进行规范化

或者，我们可以使用`pandas` `Series`方法来创建这个标准化的列。为此，我们必须在调用任何方法之前调用我们`Series`对象的`.str`属性，比如`.lower`和`.replace`。注意这些方法名称与它们在内置的 Python 字符串函数中的等效函数名称相匹配。

以这种方式链接多个 `Series` 方法可以消除使用 `map` 函数的需要（因为这段代码是矢量化的）。

```py
def canonicalize_county_series(county_series):
 return (
 county_series
 .str.lower()
 .str.replace(' ', '')
 .str.replace('&', 'and')
 .str.replace('.', '')
 .str.replace('county', '')
 .str.replace('parish', '')
 )

county_and_pop['clean_county_pandas'] = canonicalize_county_series(county_and_pop['County'])
county_and_state['clean_county_pandas'] = canonicalize_county_series(county_and_state['County'])
display(county_and_pop), display(county_and_state);
```

```py
/var/folders/7t/zbwy02ts2m7cn64fvwjqb8xw0000gp/T/ipykernel_88082/2523629438.py:3: FutureWarning:

The default value of regex will change from True to False in a future version. In addition, single character regular expressions will *not* be treated as literal strings when regex=True.

/var/folders/7t/zbwy02ts2m7cn64fvwjqb8xw0000gp/T/ipykernel_88082/2523629438.py:3: FutureWarning:

The default value of regex will change from True to False in a future version. In addition, single character regular expressions will *not* be treated as literal strings when regex=True. 
```

|  | County | Population | clean_county_python | clean_county_pandas |
| --- | --- | --- | --- | --- |
| 0 | DeWitt | 16798 | dewitt | dewitt |
| 1 | Lac Qui Parle | 8067 | lacquiparle | lacquiparle |
| 2 | Lewis & Clark | 55716 | lewisandclark | lewisandclark |
| 3 | St. John the Baptist | 43044 | stjohnthebaptist | stjohnthebaptist |

|  | County | State | clean_county_python | clean_county_pandas |
| --- | --- | --- | --- | --- |
| 0 | De Witt County | IL | dewitt | dewitt |
| 1 | Lac qui Parle County | MN | lacquiparle | lacquiparle |
| 2 | Lewis and Clark County | MT | lewisandclark | lewisandclark |
| 3 | St John the Baptist Parish | LS | stjohnthebaptist | stjohnthebaptist |

### 6.2.2 提取

提取探讨了从文本数据中获取有用信息的想法。这在模型构建中将特别重要，我们将在几周内学习这个问题。

假设我们想要从一个 `.txt` 文件中读取一些数据。

```py
with open('data/log.txt', 'r') as f:
 log_lines = f.readlines()

log_lines
```

```py
['169.237.46.168 - - [26/Jan/2014:10:47:58 -0800] "GET /stat141/Winter04/ HTTP/1.1" 200 2585 "http://anson.ucdavis.edu/courses/"\n',
 '193.205.203.3 - - [2/Feb/2005:17:23:6 -0800] "GET /stat141/Notes/dim.html HTTP/1.0" 404 302 "http://eeyore.ucdavis.edu/stat141/Notes/session.html"\n',
 '169.237.46.240 - "" [3/Feb/2006:10:18:37 -0800] "GET /stat141/homework/Solutions/hw1Sol.pdf HTTP/1.1"\n']
```

假设我们想要提取日、月、年、小时、分钟、秒和时区。不幸的是，这些项目不是从字符串的开头固定位置开始的，所以通过一些固定偏移量进行切片是行不通的。

相反，我们可以进行一些巧妙的思考。注意到相关信息包含在一组方括号中，进一步由 `/` 和 `:` 分隔。我们可以聚焦在文本的这个区域，并在这些字符上分割数据。`Python` 的内置 `.split` 函数使这变得容易。

```py
first = log_lines[0] # Only considering the first row of data

pertinent = first.split("[")[1].split(']')[0]
day, month, rest = pertinent.split('/')
year, hour, minute, rest = rest.split(':')
seconds, time_zone = rest.split(' ')
day, month, year, hour, minute, seconds, time_zone
```

```py
('26', 'Jan', '2014', '10', '47', '58', '-0800')
```

这段代码有两个问题：

1.  `Python` 的内置函数限制我们一次只能提取一条记录的数据，

    +   这可以使用 `map` 函数或 `pandas` `Series` 方法来解决。

1.  这段代码相当冗长。

    +   这是一个更大的问题，更难解决

在下一节中，我们将介绍正则表达式 - 一种解决问题 2 的工具。

## 6.3 正则表达式基础知识

**正则表达式（“RegEx”）**是一个指定搜索模式的字符序列。它们被编写用来从文本中提取特定信息。正则表达式本质上是 `python` 中嵌入的一种较小的编程语言，通过 `re` 模块提供。因此，它们有独立的语法和各种功能的方法。

正则表达式在数据科学之外的许多应用中都很有用。例如，社会安全号码（SSN）经常使用正则表达式进行验证。

```py
r"[0-9]{3}-[0-9]{2}-[0-9]{4}" # Regular Expression Syntax

# 3 of any digit, then a dash,
# then 2 of any digit, then a dash,
# then 4 of any digit
```

```py
'[0-9]{3}-[0-9]{2}-[0-9]{4}'
```

有很多资源可以学习和实验正则表达式。以下是一些资源：

+   [官方正则表达式指南](https://docs.python.org/3/howto/regex.html)

+   [Data 100 参考资料](https://ds100.org/sp22/resources/assets/hw/regex_reference.pdf)

+   [Regex101.com](https://regex101.com/)

    +   确保在左侧的类别下选择 `Python`。

### 6.3.1 基础正则表达式语法

正则表达式有四种基本操作。

| 操作 | 顺序 | 语法示例 | 匹配 | 不匹配 |
| --- | --- | --- | --- | --- |
| `或`：<code>&#124;</code> | 4 | <code>AA&#124;BAAB</code> | `AA` `BAAB` | 任何其他字符串 |
| `连接` | 3 | `AABAAB` | `AABAAB` | 任何其他字符串 |
| `闭包`：`*`（零个或多个） | 2 | `AB*A` | `AA` `ABBBBBBA` | `AB` `ABABA` |
| `分组`：`()`（括号） | 1 | <code>A(A&#124;B)AAB</code>  | `AAAAB` `ABAAB` | 任何其他字符串 |
| | | `(AB)*A` | `A` `ABABABABA` |  `AA` `ABBA` |

注意这些元字符操作的顺序。这些**元字符**不是字面字符，而是操作相邻字符。`()` 优先级最高，然后是 `*`，最后是 `|`。这使我们能够区分非常不同的正则表达式命令，比如 `AB*` 和 `(AB)*`。前者读作“`A` 然后零个或多个 `B`”，而后者指定“零个或多个 `AB`”。

#### 6.3.1.1 示例

**问题 1**：给出一个匹配 `moon`、`moooon` 等的正则表达式。你的表达式应该匹配任何偶数个 `o`，但不包括零个（即不匹配 `mn`）。

**答案 1**：`moo(oo)*n`

+   在捕获组之前硬编码`oo`可以确保不匹配`mn`。

+   `(oo)*`的捕获组确保`o`的数量是偶数。

**问题 2**：只使用基本操作，制定一个正则表达式，匹配`muun`，`muuuun`，`moon`，`moooon`等。你的表达式应该匹配任何偶数个`u`或`o`，但不包括零（即不匹配`mn`）。

**答案 2**：`m(uu(uu)*|oo(oo)*)n`

+   以`m`开头和`n`结尾确保只匹配以`m`开头和以`n`结尾的字符串。

+   注意外部捕获组围绕着`|`。

    +   考虑正则表达式`m(uu(uu)*)|(oo(oo)*)n`。这错误地匹配了`muu`和`oooon`。

        +   每个 OR 子句是`|`左右两侧的所有内容。不正确的解决方案只匹配字符串的一半，并且忽略了`m`开头或`n`结尾。

        +   必须在`|`周围加上括号。这样，每个 OR 子句都是`|`**组内**左右两侧的所有内容。这确保了`m`开头*和*`n`结尾都被匹配。

## 6.4 正则表达式扩展

以下提供了更复杂的正则表达式函数。

| 操作 | 语法示例 | 匹配 | 不匹配 |
| --- | --- | --- | --- |
| `任意字符`：`.`（除换行符外） | `.U.U.U.` | `CUMULUS JUGULUM` | `SUCCUBUS TUMULTUOUS` |
| `字符类`：`[]`（匹配`[]`中的一个字符） | `[A-Za-z][a-z]*` | 单词首字母大写 | 驼峰命名 `4illegal` |
| `重复"a"次`：`{a}`  | `j[aeiou]{3}hn` | `jaoehn` `jooohn` | `jhn` `jaeiouhn` |
| `重复"a 到 b"次`：`{a, b}`  | `j[0u]{1,2}hn` | `john` `juohn` | `jhn` `jooohn` |
| `至少一个`：`+` | `jo+hn` | `john` `joooooohn` | `jhn` `jjohn` |
| `零或一次`：`?` | `joh?n` | `jon` `john` | 任何其他字符串 |

字符类匹配其类中的单个字符。这些字符可以是硬编码的 - 在`[aeiou]`的情况下 - 或者可以指定简写以表示一系列字符。例如：

1.  `[A-Z]`：任何大写字母

1.  `[a-z]`：任何小写字母

1.  `[0-9]`：任何单个数字

1.  `[A-Za-z]`：任何大写或小写字母

1.  `[A-Za-z0-9]`：任何大写或小写字母或单个数字

#### 6.4.0.1 示例

让我们分析一些复杂正则表达式的例子。

| 匹配 | 不匹配 |
| --- | --- |
| `.*SPB.*` | |
| `RASPBERRY SPBOO` | `SUBSPACE SUBSPECIES` |
| `[0-9]{3}-[0-9]{2}-[0-9]{4}` | |
| `231-41-5121` `573-57-1821` | `231415121` `57-3571821` |
| `[a-z]+@([a-z]+\.)+(edu&#124;com)` | |
| `horse@pizza.com` `horse@pizza.food.com` | `frank_99@yahoo.com` `hug@cs` |

**解释**

1.  `.*SPB.*`只匹配包含子字符串`SPB`的字符串。

    +   `.*`元字符匹配任意数量的非负字符。换行符不计入其中。

1.  这个正则表达式匹配任意 3 个数字，然后是一个破折号，然后是任意 2 个数字，然后是一个破折号，然后是任意 4 个数字。

    +   你会认出这是熟悉的社会安全号码正则表达式。

1.  匹配任何带有`com`或`edu`域的电子邮件，其中电子邮件的所有字符都是字母。

    +   域名前必须至少有一个`.`。在任何元字符（在本例中是`.`）之前包括一个反斜杠`\`告诉正则表达式精确匹配该字符。

## 6.5 方便的正则表达式

以下是一些更方便的正则表达式。

| 操作 | 语法示例 | 匹配 | 不匹配 |
| --- | --- | --- | --- |
| `内置字符类` | `\w+` | `Fawef_03` |  `this person` |
| | `\d+`  | `231123` |  `423 people` |
| | `\s+` |  `空白` |   `非空白` |
| `字符类否定`：`[^]`（除了给定的字符之外的所有内容） | `[^a-z]+.` | `PEPPERS3982` `17211!↑å` | `porch` `CLAmS` |
| `转义字符`：`\`（匹配下一个字符的字面意义） | `cow\.com` | `cow.com` | `cowscom` |
| `行首`：`^` | `^ark` | `ark two` `ark o` `ark` | `dark` |
| `行尾`：`$` | `ark$` | `dark` `ark` `o ark` | `ark two` |
| `零或更多的懒惰版本`：`*?` | `5.*?5` | `5005` `55` | `5005005` |

### 6.5.1 贪婪性

为了充分理解表中的最后一个操作，我们必须讨论贪婪性。RegEx 是贪婪的 - 它会在字符串中寻找最长可能的匹配。为了举例说明这一点，考虑模式`<div>.*</div>`。给定下面的句子，我们希望粗体部分会被匹配：

“`这是一个正则表达式<div>中</div>的贪婪性的<div>示例</div>`。”

实际上，RegEx 处理给定模式的文本的方式如下：

1.  “寻找确切的字符串`<div>`”

1.  然后，“寻找任何字符 0 次或更多次”

1.  然后，“寻找确切的字符串`</div>`”

结果将是从最左边的`<div>`到最右边的`</div>`（包括在内）的所有字符。我们可以通过使我们的模式非贪婪来修复这个问题，`<div>.*?</div>`。您可以在文档中阅读更多信息[这里](https://docs.python.org/3/howto/regex.html#greedy-versus-non-greedy)。

### 6.5.2 示例

让我们重新审视一下从给定的`.txt`文件中提取日期/时间数据的早期问题。数据看起来是这样的。

```py
log_lines[0]
```

```py
'169.237.46.168 - - [26/Jan/2014:10:47:58 -0800] "GET /stat141/Winter04/ HTTP/1.1" 200 2585 "http://anson.ucdavis.edu/courses/"\n'
```

**问题**：给出一个正则表达式，匹配括号内和包括括号在内的所有内容 - 天，月，年，小时，分钟，秒和时区。

**答案**：`$$.*$$`

+   注意匹配字面上的`[`和`]`是必要的。因此，在`[`和`]`之前都需要转义字符`\` — 否则这些元字符将匹配字符类。

+   我们需要匹配`[`和`]`之间的特定格式。对于这个例子，`.*`就足够了。

**备选方案**：`$$\w+/\w+/\w+:\w+:\w+:\w+\s-\w+$$`

+   这个解决方案更安全。

    +   想象一下在`[`和`]`之间的数据是垃圾 - `.*`仍然会匹配它。

    +   备选方案只会匹配符合正确格式的数据。

## Python 和 Pandas 中的正则表达式（RegEx 组）

### 6.6.1 规范化

#### 6.6.1.1 使用正则表达式进行规范化

在本笔记的早期，我们使用`python`字符串操作和`pandas`的`Series`方法来检查规范化的过程。然而，我们提到这种方法有一个主要缺陷：我们的代码过于冗长。有了我们对正则表达式的知识，让我们来修复这个问题。

为此，我们需要了解`re`模块中的一些函数。其中之一是替换函数：`re.sub(pattern, rep1, text)`。它的行为类似于`python`内置的`.replace`函数，并返回所有`pattern`的实例被`rep1`替换后的文本。

这里的正则表达式删除了被`<>`（也称为 HTML 标签）包围的文本。

按顺序，模式匹配... 1\. 单个`<` 2\. 任何不是`>`的字符：div，td valign...，/td，/div 3\. 单个`>`

在`text`中的任何子字符串，只要满足所有三个条件，都将被替换为`''`。

```py
import re

text = "<div><td valign='top'>Moo</td></div>"
pattern = r"<[^>]+>"
re.sub(pattern, '', text) 
```

```py
'Moo'
```

注意在正则表达式模式之前的`r`；这指定了正则表达式是原始字符串。原始字符串不识别转义序列（即 Python 换行元字符`\n`）。这使它们对于正则表达式非常有用，因为正则表达式通常包含字面上的`\`字符。

换句话说，不要忘记用`r`标记你的 RegEx。

#### 6.6.1.2 使用`pandas`进行规范化

我们还可以使用`pandas`的`Series`方法进行正则表达式。这使我们能够操作整列数据，而不是单个值。代码很简单：

`ser.str.replace(pattern, repl, regex=True`).

考虑以下带有单列的`DataFrame` `html_data`。

代码

```py
data = {"HTML": ["<div><td valign='top'>Moo</td></div>", \
 "<a href='http://ds100.org'>Link</a>", \
 "<b>Bold text</b>"]}
html_data = pd.DataFrame(data)
```

```py
html_data
```

|  | HTML |
| --- | --- |
| 0 | `<div><td valign='top'>Moo</td></div>` |
| 1 | `<a href='http://ds100.org'>Link</a>` |
| 2 | `<b>Bold text</b>` |

```py
pattern = r"<[^>]+>"
html_data['HTML'].str.replace(pattern, '', regex=True)
```

```py
0          Moo
1         Link
2    Bold text
Name: HTML, dtype: object
```

### 6.6.2 提取

#### 6.6.2.1 使用正则表达式进行提取

就像规范化一样，`re`模块提供了从字符串中提取相关文本的功能：

`re.findall(pattern, text)`。此函数返回与`pattern`匹配的所有实例的列表。

使用熟悉的社会安全号码的正则表达式：

```py
text = "My social security number is 123-45-6789 bro, or maybe it’s 321-45-6789."
pattern = r"[0-9]{3}-[0-9]{2}-[0-9]{4}"
re.findall(pattern, text) 
```

```py
['123-45-6789', '321-45-6789']
```

#### 6.6.2.2 使用`pandas`进行提取

`pandas`类似地在数据`Series`上提供提取功能：`ser.str.findall(pattern)`

考虑以下`DataFrame` `ssn_data`。

代码

```py
data = {"SSN": ["987-65-4321", "forty", \
 "123-45-6789 bro or 321-45-6789",
 "999-99-9999"]}
ssn_data = pd.DataFrame(data)
```

```py
ssn_data
```

|  | SSN |
| --- | --- |
| 0 | 987-65-4321 |
| 1 | forty |
| 2 | 123-45-6789 bro or 321-45-6789 |
| 3 | 999-99-9999 |

```py
ssn_data["SSN"].str.findall(pattern)
```

```py
0                 [987-65-4321]
1                            []
2    [123-45-6789, 321-45-6789]
3                 [999-99-9999]
Name: SSN, dtype: object
```

该函数返回一个列表，其中包含给定字符串中模式匹配的每一行。

正如你所期望的，`pandas`还为其他`re`函数提供了类似的等效功能。`Series.str.extract`接受一个模式，并返回字符串中每个捕获组的第一个匹配的`DataFrame`。相比之下，`Series.str.extractall`返回每个捕获组的所有匹配的多索引`DataFrame`。你可以在下面的输出中看到差异：

```py
pattern_cg = r"([0-9]{3})-([0-9]{2})-([0-9]{4})"
ssn_data["SSN"].str.extract(pattern_cg)
```

|  | 0 | 1 | 2 |
| --- | --- | --- | --- |
| 0 | 987 | 65 | 4321 |
| 1 | NaN | NaN | NaN |
| 2 | 123 | 45 | 6789 |
| 3 | 999 | 99 | 9999 |

```py
ssn_data["SSN"].str.extractall(pattern_cg)
```

|  |  | 0 | 1 | 2 |
| --- | --- | --- | --- | --- |
|  | match |  |  |  |
| 0 | 0 | 987 | 65 | 4321 |
| 2 | 0 | 123 | 45 | 6789 |
| 1 | 321 | 45 | 6789 |
| 3 | 0 | 999 | 99 | 9999 |

### 6.6.3 正则表达式捕获组

早些时候，我们使用括号`（` `）`来指定正则表达式中操作的最高顺序。然而，它们还有另一层含义；括号经常用来表示**捕获组**。捕获组本质上是一组较小的正则表达式，用于匹配文本数据中的多个子字符串。

让我们看一个例子。

#### 6.6.3.1 示例 1

```py
text = "Observations: 03:04:53 - Horse awakens. \
 03:05:14 - Horse goes back to sleep."
```

假设我们想要捕获时间数据（小时，分钟和秒）的所有出现作为*单独的实体*。

```py
pattern_1 = r"(\d\d):(\d\d):(\d\d)"
re.findall(pattern_1, text)
```

```py
[('03', '04', '53'), ('03', '05', '14')]
```

注意给定的模式有 3 个捕获组，每个都由正则表达式`(\d\d)`指定。然后我们使用`re.findall`返回这些捕获组，每个都包含 3 个匹配的元组。

这些正则表达式捕获组可以是不同的。我们可以使用`(\d{2})`的速记法来提取相同的数据。

```py
pattern_2 = r"(\d\d):(\d\d):(\d{2})"
re.findall(pattern_2, text)
```

```py
[('03', '04', '53'), ('03', '05', '14')]
```

#### 6.6.3.2 示例 2

有了捕获组的概念，让自己相信以下正则表达式是如何工作的。

```py
first = log_lines[0]
first
```

```py
'169.237.46.168 - - [26/Jan/2014:10:47:58 -0800] "GET /stat141/Winter04/ HTTP/1.1" 200 2585 "http://anson.ucdavis.edu/courses/"\n'
```

```py
pattern = r'$$(\d+)\/(\w+)\/(\d+):(\d+):(\d+):(\d+) (.+)$$'
day, month, year, hour, minute, second, time_zone = re.findall(pattern, first)[0]
print(day, month, year, hour, minute, second, time_zone)
```

```py
26 Jan 2014 10 47 58 -0800
```

## 6.7 正则表达式的局限性

今天，我们探讨了在数据整理中使用正则表达式处理文本数据的能力。然而，还有一些需要注意的事项。

编写正则表达式就像编写程序一样。

+   需要熟悉语法。

+   写起来可能比读起来更容易。

+   可能很难调试。

正则表达式在某些类型的问题上表现糟糕：

+   对于解析分层结构，比如 JSON，使用`json.load()`解析器，而不是 RegEx！

+   复杂特性（例如有效的电子邮件地址）。

+   计数（a 和 b 的实例数相同）。 （不可能）

+   复杂属性（回文，平衡括号）。 （不可能）

最终的目标不是记住所有的正则表达式。相反，目标是：

+   了解 RegEx 的能力。

+   解析和创建 RegEx，使用参考表

+   使用词汇（元字符，转义字符，组等）描述正则表达式元字符。

+   区分`()`，`[]`，`{}`

+   设计自己的字符类，使用，，[…-…]，^等。

+   使用`python`和`pandas`的 RegEx 方法。
