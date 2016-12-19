---
title: "Ошибка компилятора CS0753 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0753"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0753"
ms.assetid: 287dd9da-da74-4290-9fa1-21ef1a8150fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0753
Разделяемыми могут быть только методы, классы, структуры и интерфейсы.  
  
 Модификатор [partial](../Topic/partial%20\(Type\)%20\(C%23%20Reference\).md) может использоваться только с классами, структурами, интерфейсами и методами.  
  
### Исправление ошибки  
  
1.  Удалите модификатор `partial` из переменной или из языковой конструкции.  
  
## Пример  
 В следующем коде возникает ошибка CS0753:  
  
```  
// cs0753.cs using System; public partial class C { partial int num; // CS0753 public static int Main() { return 1; } }  
```  
  
## См. также  
 [Разделяемые классы и методы](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)