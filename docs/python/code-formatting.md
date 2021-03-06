---
title: "在 Visual Studio 中设置 Python 代码格式 | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 80e23d4e3973590d5046468e9efb826afd1417d5
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="formatting-python-code"></a>设置 Python 代码格式

在 Visual Studio 中，可以快速重新设置代码格式以匹配预先配置的格式设置选项。

- 若要设置选定内容的格式：请选择“编辑”>“高级”>“设置选定内容的格式”或按 Ctrl+E、F。
- 若要设置整个文件的格式：请选择“编辑”>“高级”>“设置文档的格式”或按 Ctrl+E、D。

通过“工具”>“选项”>“文本编辑器”>“Python”>“格式”及其嵌套选项卡设置选项，并且默认情况下设置为匹配 [PEP 8 样式指南](http://www.python.org/dev/peps/pep-0008/)的超集。 “常规”选项卡确定何时应用格式；本主题中介绍了设置其他三个选项卡。

借助 [Visual Studio 中的 Python 支持](installation.md)，还可在**“编辑”>“高级”**菜单中添加有用的[“填充注释段落”](#fill-comment-paragraph-command)命令，如下所述。

## <a name="spacing"></a>间距

**间距**控制各种语言构造周围插入或删除空格的位置。 每个选项都有三个可能值：

- 已选中：确保间距已应用。
- 清除：删除所有间距。
- 不确定：保留原始格式。

下表提供关于各种选项的示例：

| 类定义选项 | 已选中 | 清除 |
| --- | --- | --- | 
| 在类定义名称和基列表之间插入空格 | `class X (object): pass` | `class X(object): pass` | 
| 在基列表括号内插入空格 | `class X( object ): pass` | `class X(object): pass` |
| 在空的基列表括号内插入空格 | `class X( ): pass` | `class X(): pass` |

<br/>

| 函数定义选项 | 已选中 | 清除 |
| --- | --- | --- |
| 在函数声明名称和参数列表间插入空格 | `def X (): pass` | `def X(): pass` | 
| 在参数列表括号内插入空格 | `def X( a, b ): pass` | `def X(a, b): pass` |
| 在空的参数列表括号内插入空格 | `def X( ): pass` | `def X(): pass` |
| 在默认参数值中的“=”周围插入空格 | `includes X(a = 42): pass` | `includes X(a=42): pass` |
| 在返回批注运算符前后插入空格 | `includes X() -> 42: pass` | `includes X()->42: pass` |

<br/>

| 运算符选项 | 已选中 | 清除 |
| --- | --- | --- |
| 在二元运算符周围插入空格 | `a + b` | `a+b` |
| 在赋值周围插入空格 | `a = b` | `a=b` |

<br/>

| 表达式间距选项 | 已选中 | 清除 |
| --- | --- | --- |
| 在函数调用名称和参数列表间插入空格 | `X ()` | `X()` |
| 在空参数列表的括号中插入空格 | `X( )` | `X()` |
| 在参数列表的括号中插入空格 | `X( a, b )` | `X(a, b)` |
| 在表达式的括号内插入空格 | `( a )` | `(a)` |
| 在空的元组括号内插入空格 | `( )` | `()` |
| 在元组括号内插入空格 | `( a, b )` | `(a, b)` |
| 在空方括号中插入空格 | `[ ]` | `[]` |
| 在列表的方括号内插入空格 | `[ a, b ]` | `[a, b]` |
| 在左方括号前插入空格 | `x [i]` | `x[i]` |
| 在方括号中插入空格 | `x[ i ]` | `x[i]` |

<br/>

## <a name="statements"></a>语句

“语句”选项用于控制以其他更 Python 的形式自动重写各种语句。

| 选项 | 设置格式前 | 设置格式后 |
| --- | --- | --- |
| 将导入的模块置于新行 | `import sys, pickle` | `import sys`<br/>`import pickle` |
| 移除不必要的分号 | `x = 42;` | `x = 42` |
| 将多个语句置于新行 | `x = 42; y = 100` | `x = 42`<br/>`y = 100` |


## <a name="wrapping"></a>换行

“换行”选项用于设置“最大注释宽度”（默认值为 80）。 设置“对过宽的注释换行”选项后，Visual Studio 会重新设置注释格式，使其不超过该最大宽度。

```python
# Wrapped to 40 columns
# There should be one-- and preferably
# only one --obvious way to do it.
```

```python
# Not-wrapped:
# There should be one-- and preferably only one --obvious way to do it.
```



## <a name="fill-comment-paragraph-command"></a>填充注释段落命令

使用“编辑”>“高级”>“填充注释段落”（Ctrl+E、P）可重排并设置注释文本格式，从而组合短行、分割长行。

例如: 

```python
# foo 
# bar
# baz
```

更改为：

```python
# foo bar baz
```

```python
# This is a very long long long long long long long long long long long long long long long long long long long comment
```

更改为：

```python
# This is a very long long long long long long long long long long long long
# long long long long long long long comment
```