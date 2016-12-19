---
title: "Option Strict On не разрешает сужение из типа &quot;&lt;имя_типа1&gt;&quot; в тип &quot;&lt;имя_типа2&gt;&quot; при копировании значения параметра ByRef &quot;&lt;имя_параметра&gt;&quot; обратно в соответствующий аргумент. | Microsoft Docs"
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
  - "bc32029"
  - "vbc32029"
helpviewer_keywords: 
  - "BC32029"
ms.assetid: fc9ae5d2-b506-47cf-a50c-116fda5ed206
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On не разрешает сужение из типа &quot;&lt;имя_типа1&gt;&quot; в тип &quot;&lt;имя_типа2&gt;&quot; при копировании значения параметра ByRef &quot;&lt;имя_параметра&gt;&quot; обратно в соответствующий аргумент.
Вызов процедуры предоставляет аргумент `ByRef` с типом данных, который расширяется до объявленного типа аргумента, и `Option Strict` — `On`. Расширяющее преобразование допускается при передаче аргумента в процедуру, но если эта процедура изменяет содержимое аргумента переменной в вызывающем коде, обратное преобразование будет сужающим. С `Option Strict On` сужающие преобразования не допускаются.  
  
 **Идентификатор ошибки:** BC32029  
  
### Исправление ошибки  
  
-   Предоставьте все аргументы `ByRef` в вызов процедуры с тем же типом данных, что и объявленный тип, или установите `Option Strict Off`.  
  
## См. также  
 [Оператор Option Strict](../Topic/Option%20Strict%20Statement.md)   
 [Передача аргументов по значению и по ссылке](../Topic/Passing%20Arguments%20by%20Value%20and%20by%20Reference%20\(Visual%20Basic\).md)   
 [Расширяющие и сужающие преобразования](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Явные и неявные преобразования](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)