---
title: "Операнд TryCast должен быть ссылочного типа, а &quot;&lt;имя_типа&gt;&quot; является типом значения | Microsoft Docs"
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
  - "BC30792"
  - "vbc30792"
helpviewer_keywords: 
  - "BC30792"
ms.assetid: 3325fce5-dbc0-4d1d-9530-31f4720bfe6e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операнд TryCast должен быть ссылочного типа, а &quot;&lt;имя_типа&gt;&quot; является типом значения
Оператор `TryCast` используется с типом значения для по крайней мере одного из аргументов.  
  
 `TryCast` проверяет отношение наследования или реализации между двумя аргументами. Таким образом, он допускает только ссылочные типы аргументов. Для получения дополнительной информации см. [Типы значений и ссылочные типы](../Topic/Value%20Types%20and%20Reference%20Types.md).  
  
 **Идентификатор ошибки:** BC30792  
  
### Исправление ошибки  
  
-   Используйте оператор `DirectCast` или `CType` для выполнения преобразования. Они оба допускают типы значений.  
  
## См. также  
 [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [Типы значений и ссылочные типы](../Topic/Value%20Types%20and%20Reference%20Types.md)