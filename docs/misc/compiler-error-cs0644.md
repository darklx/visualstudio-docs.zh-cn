---
title: "编译器错误 CS0644 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0644"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0644"
ms.assetid: 835f3ee2-f897-4ba2-ad13-af629a9ab7fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0644
“class1”无法从特殊类“class2”派生  
  
 类不能从任何以下基类中显式继承：  
  
-   **System.Enum**  
  
-   **System.ValueType**  
  
-   **System.Delegate**  
  
-   **System.Array**  
  
 这些均用作编译器的隐式基类。 例如，**System.ValueType** 是结构的隐式基类。  
  
 以下示例生成 CS0644：  
  
```  
// CS0644.cs class MyClass : System.ValueType   // CS0644 { }  
```