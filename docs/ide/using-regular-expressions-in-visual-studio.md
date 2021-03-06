---
title: "在 Visual Studio 中使用正则表达式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
- Visual Studio, regular expressions
ms.assetid: 718a617d-0e05-47e1-a218-9746971527f4
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c01023649879c34838cbca3172aec6b5a053f4bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="using-regular-expressions-in-visual-studio"></a>在 Visual Studio 中使用正则表达式
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 使用 .NET Framework 正则表达式来查找和替换文本。 有关 .NET 正则表达式的详细信息，请参阅 [.NET Framework 正则表达式](/dotnet/standard/base-types/regular-expressions)。  
  
 在 Visual Studio 2012 之前，Visual Studio 在查找和替换窗口中使用自定义的正则表达式语法。 请参阅 [Visual Studio 正则表达式转换](https://msdn.microsoft.com/en-us/library/2k3te2cs\(v=vs.110\).aspx)，了解如何将一些比较常用的自定义正则表达式符号转换为 .NET 版本。  
  
> [!TIP]
>  在 Windows 操作系统中，大多数行以“\r\n”（回车符后跟新行）结束。 这些字符不可见，但在编辑器中存在并传递给 .NET 正则表达式服务。  
  
> [!TIP]
>  有关在替换模式中使用的正则表达式的信息，请参阅[替换](/dotnet/standard/base-types/substitutions-in-regular-expressions)。 若要使用已编号的捕获组，语法是 `$1`用于指定编号组）和 `(x)`（指定相关组）。 例如，已分组的正则表达式 `(\d)([a-z])` 在以下字符串中查找四个匹配项：**1a 2b 3c 4d**。 替换字符串 `z$1` 将该字符串转换为 **z1 z2 z3 z4**。  
  
## <a name="regular-expressions-in-visual-studio"></a>Visual Studio 中的正则表达式  
 以下是一些示例  
  
|目标|表达式|示例|  
|-------------|----------------|-------------|  
|与任何单个字符匹配（换行符除外）。|。|`a.o` 匹配“around”中的“aro”及“about”中的“abo”，但不匹配“across”中的“acro”。|  
|零次或多次匹配前面的表达式（匹配尽可能多的字符）|*|`a*r` 匹配“rack”中的“r”，“ark”中的“ar”和“aardvark”中的“aar”|  
|零次或多次匹配任何字符（通配符 *）|.*|c.*e 匹配“racket”中的“cke”，“comment”中的“comme”和“code”中的“code”|  
|一次或多次匹配前面的表达式（匹配尽可能多的字符）|+|`e.+e` 匹配“feeder”中的“eede”，而不是“ee”。|  
|一次或多次匹配任意字符（通配符 ?）|.+|e.+e 匹配“feeder”中的“eede”，而不是“ee”。|  
|零次或多次匹配前面的表达式（匹配尽可能多的字符）|*?|`e.*?e` 匹配“feeder”中的“ee”，而不是“eede”。|  
|一次或多次匹配前面的表达式（匹配尽可能多的字符）|+?|`e.+?e` 匹配“enterprise”中的“ente”和“erprise”，但不匹配整个单词“enterprise”。|  
|将匹配字符串定位到行或字符串的开头|^|`^car` 仅在出现于行开头时才匹配单词“car”。|  
|将匹配字符串定位到行尾|\r?$|`End\r?$` 仅在出现于行尾时才匹配“end”。|  
|匹配集中的任何单个字符|[abc]|`b[abc]` 匹配“ba”、“bb”和“bc”。|  
|匹配的字符范围中的任意字符|[a-f]|`be[n-t]` 匹配“between”中的“bet”，“beneath”中的“ben”，“beside”中的“bes”，但不匹配“below”。|  
|捕获包含在括号中的表达式并对其进行隐式编号|()|`([a-z])X\1` 匹配“aXa”和“bXb”，但不匹配“aXb”。 ". “\1”指第一个表达式组“[a-z]”。|  
|使匹配无效|(?!abc)|`real (?!ity)` 匹配“realty”和“really”中的“real”，但不匹配“reality”。 它还可找到“realityreal”中的第二个“real”（而非第一个“real”）。|  
|匹配不在给定字符集中的任意字符|[^abc]|`be[^n-t]` 匹配“before”中的“bef”，“behind”中的“beh”和“below”中的“bel”，但不匹配“beneath”。|  
|匹配符号前或符号后的表达式。|&#124;|`(sponge&#124;mud) bath` 匹配“sponge bath”和“mud bath”。|  
|对反斜杠后面的字符进行转义|\|`\^` 匹配字符 ^。|  
|指定前面的字符或组的出现次数|{x}，其中 x 是出现次数|`x(ab){2}x` 匹配“xababx”，`x(ab){2,3}x` 匹配“xababx”和“xabababx”，但不匹配“xababababx”。|  
|匹配 Unicode 字符类中的文本，其中“X”是 Unicode 数字。 有关 Unicode 字符类的详细信息，请参阅 <br /><br /> [Unicode Standard 5.2 字符属性](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf)。|\p{X}|`\p{Lu}` 匹配“Thomas Doe”中的“T”和“D”。|  
|与字边界匹配|`\b`（在字符类 \b 的外部指定字边界，而在字符类内部指定退格符）。|`\bin` 匹配“inside”中的“in”，不匹配“pinto”。|  
|与换行符（即回车符后跟新行）相匹配。|\r?\n|仅当“End”是一行的最后一个字符串，且“Begin”是下一行的第一个字符串时，`End\r?\nBegin` 才匹配“End”和“Begin”。|  
|匹配任意字母数字字符|\w|`a\wd` 匹配“add”和“a1d”，不匹配“a d”。|  
|匹配任意空格字符。|(?([^\r\n])\s)|`Public\sInterface` 匹配词组“Public Interface”。|  
|匹配任意数字字符|\d|`\d` 匹配“3456”中的“3”，“23”中的“2”和“1”中的“1”。|  
|匹配 Unicode 字符|\uXXXX，其中 XXXX 指定 Unicode 字符值。|`\u0065` 匹配字符“e”。|  
|匹配标识符|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|匹配“Type1”，但不匹配“&type1”或“#define”。|  
|与引号中的字符串匹配|((\\".+?\\")&#124;('.+?'))|匹配单引号或双引号内的任意字符串。|  
|匹配十六进制数|\b0[xX]([0-9a-fA-F]\)\b|匹配“0xc67f”但不匹配“0xc67fc67f”。|  
|匹配整数和小数|\b[0-9]*\\.\*[0-9]+\b|匹配“1.333”。|  
  
## <a name="see-also"></a>另请参阅  
 [查找和替换文本](../ide/finding-and-replacing-text.md)