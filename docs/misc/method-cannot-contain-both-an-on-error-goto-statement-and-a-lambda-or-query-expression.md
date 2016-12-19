---
title: "Метод не может одновременно содержать оператор On Error GoTo и лямбда-выражение или выражение запроса | Microsoft Docs"
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
  - "bc36595"
  - "vbc36595"
helpviewer_keywords: 
  - "BC36595"
ms.assetid: 4e7cc11e-f53d-4481-afb4-653a81d54483
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Метод не может одновременно содержать оператор On Error GoTo и лямбда-выражение или выражение запроса
Метод содержит и оператор `On Error Goto`, и лямбда\-выражение или запрос LINQ. Нельзя включать в метод оператор `On Error Goto` с лямбда\-выражением или запросом LINQ.  
  
 **Идентификатор ошибки:** BC36595  
  
### Исправление ошибки  
  
1.  Замените код обработки исключений, использующий оператор `On Error Goto`, на оператор `Try...Catch`.  
  
## См. также  
 [Введение в обработку исключений \(Visual Basic\)](http://msdn.microsoft.com/ru-ru/9792f16a-0cd2-40bd-ace2-f7a4344c0e52)   
 [Оператор Try...Catch...Finally](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Знакомство с LINQ в Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [Лямбда\-выражения](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md)   
 [Оператор On Error](../Topic/On%20Error%20Statement%20\(Visual%20Basic\).md)