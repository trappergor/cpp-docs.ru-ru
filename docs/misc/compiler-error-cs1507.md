---
title: "Ошибка компилятора CS1507 | Microsoft Docs"
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
  - "CS1507"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1507"
ms.assetid: e1be3aba-81dc-4f65-87a4-d3f90b82dc7d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS1507
Невозможно скомпоновать файл ресурсов "файл" при сборке модуля  
  
 Параметр [\/linkresource](../Topic/-linkresource%20\(C%23%20Compiler%20Options\).md) использовался в одной компиляции с [\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md), что недопустимо. Например, использование следующих параметров приведет к возникновению ошибки CS1507:  
  
```  
csc /linkresource:rf.resource /target:module in.cs  
```  
  
 Однако внедрение ресурсов \([\/resource](../Topic/-resource%20\(C%23%20Compiler%20Options\).md)\) разрешено.