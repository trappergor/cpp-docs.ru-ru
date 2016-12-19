---
title: "Option Strict On не позволяет выполнять неявные преобразования из &quot;&lt;тип1&gt;&quot; в &quot;&lt;тип2&gt;&quot;. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30512"
  - "vbc30512"
helpviewer_keywords: 
  - "BC30512"
ms.assetid: b9756d48-05fa-4027-8a80-b4a0ef92099d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On не позволяет выполнять неявные преобразования из &quot;&lt;тип1&gt;&quot; в &quot;&lt;тип2&gt;&quot;.
Предпринята попытка преобразовать тип в другой тип, который не может содержать это значение, например `Long` в `Integer`, а параметр проверки типа \([Оператор Option Strict](../Topic/Option%20Strict%20Statement.md)\) имеет значение `On`.  
  
 Этот тип преобразования называется *сужающим преобразованием*, и во время выполнения может произойти его сбой. По этой причине `Option Strict On` запрещает неявные сужающие преобразования.  
  
 **Идентификатор ошибки:** BC30512  
  
### Исправление ошибки  
  
1.  Определите, существует ли преобразование любого типа из `<type1>` в `<type2>`. Если оба значения являются простыми типами [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)], или если оба значения являются экземплярами классов, обычно можно сделать это определение по таблице в [Расширяющие и сужающие преобразования](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md).  
  
2.  Если существует только сужающее преобразование из `<type1>` в `<type2>`, следует использовать явное приведение типов. Ключевые слова [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md) и [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md) вызывают исключение времени выполнения, если происходит сбой преобразования. Ключевое слово [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md) применяется только к ссылочным типам и возвращает [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) в случае сбоя преобразования.  
  
3.  Если существует сужающее преобразование, и ваша программа может допускать сбой во время выполнения, или вы уверены, что ошибка времени выполнения невозможна, можно указать `Option Strict Off` в начале исходного кода. Но все же следует заключить преобразование в блок [Оператор Try...Catch...Finally](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md), чтобы избежать непредвиденных результатов или преждевременного завершения программы.  
  
4.  Если не существует никакого преобразования из `<type1>` в `<type2>`, вы должны пересмотреть логику программы. Вы могли бы написать код, который может назначать `<type2>` значения, соответствующие ожидаемым значениям `<type1>`.  
  
5.  Если не существует преобразования из `<type1>` в `<type2>`, и один из типов является определенным вами классом или структурой, можно определить оператор преобразования из этого типа или из другого типа. Дополнительные сведения см. в разделе [Практическое руководство. Определение оператора преобразования](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md).  
  
6.  Во всех случаях и в качестве общей рекомендации следует избегать сужающих преобразований, если вы не можете отлавливать сбои в блоке `Catch`и эффективно работать с ними.  
  
## См. также  
 [Оператор Option Strict](../Topic/Option%20Strict%20Statement.md)   
 [Расширяющие и сужающие преобразования](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md)   
 [Оператор Try...Catch...Finally](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Практическое руководство. Определение оператора преобразования](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)