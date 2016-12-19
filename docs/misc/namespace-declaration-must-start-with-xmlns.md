---
title: "Объявление пространства имен должно начинаться с xmlns | Microsoft Docs"
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
  - "bc31187"
  - "vbc31187"
helpviewer_keywords: 
  - "BC31187"
ms.assetid: 64c6a033-7cdc-48a0-bff0-bdd045cb13ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Объявление пространства имен должно начинаться с xmlns
Пространство имен XML было указано без обязательного идентификатора `xmlns`. Идентификатор `xmlns` должен содержать только символы в нижнем регистре.  
  
 **Идентификатор :** BC31187  
  
### Исправление ошибки  
  
-   Используйте идентификатор `xmlns` при объявлении пространства имен XML. Ниже представлен пример:  
  
    ```vb#  
    Imports <xmlns:ns="http://SampleNamespace">  
    ```  
  
## См. также  
 [Оператор Imports \(пространство имен XML\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)   
 [XML\-литералы](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)