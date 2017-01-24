---
title: "Аргументы типов нельзя использовать в выражении &quot;&lt;выражение&gt;&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32058"
  - "vbc32058"
helpviewer_keywords: 
  - "BC32058"
ms.assetid: c6b9b49c-6fb2-47b8-a8bb-464562d3adfd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Аргументы типов нельзя использовать в выражении &quot;&lt;выражение&gt;&quot;
Псевдоним импорта определен с помощью предложения [Of](../Topic/Of%20Clause%20\(Visual%20Basic\).md), которое передает аргументы типов в псевдоним импорта.  
  
 Аргументы типов используются для универсальных типов, а универсальными могут быть только классы, структуры, интерфейсы, процедуры и делегаты. Ни пространства имен, ни псевдонимы импорта не могут быть универсальными.  
  
 **Идентификатор ошибки:** BC32058  
  
### Исправление ошибки  
  
-   Удалите предложение `Of` и его аргументы типов из псевдонима импорта.  
  
## См. также  
 [Оператор Imports \(пространство имен .NET и тип\)](../Topic/Imports%20Statement%20\(.NET%20Namespace%20and%20Type\).md)   
 [Ссылки и оператор Imports](../Topic/References%20and%20the%20Imports%20Statement%20\(Visual%20Basic\).md)   
 [НЕ В СБОРКЕ. Разрешение ссылки, если у нескольких переменных одинаковые имена](http://msdn.microsoft.com/ru-ru/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [Универсальные типы в Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Список типов](../Topic/Type%20List%20\(Visual%20Basic\).md)