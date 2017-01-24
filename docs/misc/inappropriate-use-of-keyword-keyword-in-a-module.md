---
title: "Недопустимое использование ключевого слова &quot;&lt;ключевое_слово&gt;&quot; в модуле | Microsoft Docs"
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
  - "vbc42028"
  - "BC42028"
helpviewer_keywords: 
  - "BC42028"
ms.assetid: a9bc1e9d-ba2c-4a71-b147-0fb66f670316
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Недопустимое использование ключевого слова &quot;&lt;ключевое_слово&gt;&quot; в модуле
Модули не имеют экземпляров, не поддерживают наследование и не реализуют интерфейсы. Поэтому следующие ключевые слова не применяются к объявлению модуля:  
  
-   [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)  
  
-   [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md)  
  
-   [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)  
  
-   [Private](../Topic/Private%20\(Visual%20Basic\).md)  
  
-   [Protected](../Topic/Protected%20\(Visual%20Basic\).md)  
  
-   [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)  
  
-   [Shared](../Topic/Shared%20\(Visual%20Basic\).md)  
  
-   [Static](../Topic/Static%20\(Visual%20Basic\).md)  
  
 Единственные ключевые слова, поддерживаемые в [Оператор Module](../Topic/Module%20Statement.md), — [Public](../Topic/Public%20\(Visual%20Basic\).md) и [Friend](../Topic/Friend%20\(Visual%20Basic\).md).  
  
 Кроме того, нельзя использовать оператор [Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md) или [Инструкция Inherits](../Topic/Inherits%20Statement.md) в блоке операторов модуля.  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Идентификатор ошибки:** BC42028  
  
### Исправление ошибки  
  
-   Если предполагается, что элемент программирования будет модулем, следует использовать только ключевое слово `Public` или `Friend` в его объявлении. По умолчанию модуль использует ключевое слово `Friend`, если не указан его уровень доступа.  
  
-   Если вы планируете создавать экземпляры этого элемента программирования, следует объявить его как класс. После этого можно использовать ключевые слова, применяемые к объявлению класса.  
  
## См. также  
 [Оператор Class](../Topic/Class%20Statement%20\(Visual%20Basic\).md)