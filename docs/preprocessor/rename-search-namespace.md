---
title: "rename_search_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rename_search_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rename_search_namespace - атрибут"
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# rename_search_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Имеет ту же функцию, что и атрибут [rename\_namespace](../preprocessor/rename-namespace.md), однако применяется для библиотек типов, для которых вы использовали директиву \#import с атрибутом [auto\_search](../preprocessor/auto-search.md).  
  
## Синтаксис  
  
```  
rename_search_namespace("NewName")  
```  
  
#### Параметры  
 `NewName`  
 Новое имя пространства имен.  
  
## Заметки  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)