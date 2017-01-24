---
title: "Не найден доступный &quot;&lt;имя_процедуры&gt;&quot;, не являющийся универсальным типом | Microsoft Docs"
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
  - "vbc32117"
  - "bc32117"
helpviewer_keywords: 
  - "BC32117"
ms.assetid: a7bf8b67-8a0a-499e-9992-dc00e09b7ff4
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Не найден доступный &quot;&lt;имя_процедуры&gt;&quot;, не являющийся универсальным типом
Оператор вызывает процедуру, которая имеет несколько перегруженных версий, но все они являются универсальными, и вызов не предоставляет аргументы типа.  
  
 Если имеется только одна универсальная версия и она вызывается без аргументов типа, компилятор может попытаться выполнить *определение типа*. Дополнительные сведения см. в подразделе "Определение типа" в разделе [Универсальные процедуры в Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md). Однако если имеется несколько универсальных версий, компилятор не может выбрать одну из них, пока не будут предоставлены аргументы типа. Если указывается один аргумент типа, необходимо указать аргумент типа для каждого параметра типа, который определяет одна из перегруженных версий.  
  
 **Идентификатор ошибки:** BC32117  
  
### Исправление ошибки  
  
-   Вызовите процедуру со списком аргументов типа.  
  
## См. также  
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Перегрузка процедур](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Универсальные типы в Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Универсальные процедуры в Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)