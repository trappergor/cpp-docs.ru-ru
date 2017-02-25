---
title: "rename_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rename_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rename_namespace - атрибут"
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# rename_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Переименовывает пространство имен, к которому относится содержимое библиотеки типов.  
  
## Синтаксис  
  
```  
rename_namespace("NewName")  
```  
  
#### Параметры  
 `NewName`  
 Новое имя пространства имен.  
  
## Заметки  
 Принимает один аргумент, *NewName*, указывающий новое имя пространства имен.  
  
 Чтобы удалить пространство имен, используйте атрибут [no\_namespace](../Topic/no_namespace.md).  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)