---
title: "Предупреждение компилятора (уровень&#160;3) CS0642 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0642"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0642"
ms.assetid: e2df58c0-9b7e-4e50-8e31-e0134955f62c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Предупреждение компилятора (уровень&#160;3) CS0642
Возможно, ошибочный пустой оператор  
  
 Точка с запятой, стоящая после условного оператора, может быть причиной изменения предполагаемого способа выполнения кода.  
  
 Для отключения этого предупреждения можно воспользоваться параметром компилятора **\/nowarn** либо директивой `#pragmas warning`. Дополнительные сведения см. в разделе [\/nowarn \(Suppress Specified Warnings\)](../Topic/-nowarn%20\(C%23%20Compiler%20Options\).md) или [\#pragma warning](../Topic/%23pragma%20warning%20\(C%23%20Reference\).md).  
  
 При компиляции следующего примера будет выдано предупреждение CS0642:  
  
```  
// CS0642.cs // compile with: /W:3 class MyClass { public static void Main() { int i; for (i = 0; i < 10; i += 1);   // CS0642 semicolon intentional? { System.Console.WriteLine (i); } } }  
```