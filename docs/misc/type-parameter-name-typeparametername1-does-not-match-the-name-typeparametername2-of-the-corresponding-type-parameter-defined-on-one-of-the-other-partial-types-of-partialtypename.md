---
title: "Имя параметра типа &quot;&lt;имя_параметра_типа1&gt;&quot; не соответствует имени &quot;&lt;имя_параметра_типа2&gt;&quot; соответствующего параметра типа, определенного для одного из других разделяемых типов &quot;&lt;имя_разделяемого_типа&gt;&quot; | Microsoft Docs"
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
  - "vbc30931"
  - "bc30931"
helpviewer_keywords: 
  - "BC30931"
ms.assetid: 01b053c3-d1b5-4e69-b908-3d5cfc73913b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя параметра типа &quot;&lt;имя_параметра_типа1&gt;&quot; не соответствует имени &quot;&lt;имя_параметра_типа2&gt;&quot; соответствующего параметра типа, определенного для одного из других разделяемых типов &quot;&lt;имя_разделяемого_типа&gt;&quot;
Универсальный класс или структура определены в нескольких разделяемых объявлениях с конфликтующими спецификациями параметров типов.  
  
 После разделения определения класса или структуры на несколько разделяемых объявлений компилятор обрабатывает тип как объединение всех разделяемых объявлений. Это относится не только к членам, но и к реализации, наследованию и уровню доступа.  
  
 Для любого параметра типа в определении универсального класса или структуры нельзя указать несколько имен.  
  
 **Идентификатор ошибки:** BC30931  
  
### Исправление ошибки  
  
-   Выберите необходимое имя параметра типа и используйте то же имя в каждом разделяемом объявлении.  
  
## См. также  
 [Partial](../Topic/Partial%20\(Visual%20Basic\).md)   
 [Оператор Class](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Оператор Structure](../Topic/Structure%20Statement.md)   
 [НЕ В СБОРКЕ. Классы: схемы объектов](http://msdn.microsoft.com/ru-ru/2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Структуры](../Topic/Structures%20\(Visual%20Basic\).md)   
 [Универсальные типы в Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Список типов](../Topic/Type%20List%20\(Visual%20Basic\).md)