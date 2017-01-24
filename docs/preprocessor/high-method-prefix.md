---
title: "high_method_prefix | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "high_method_prefix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "high_method_prefix - атрибут"
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# high_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Задает префикс, используемый при именовании высокоуровневых свойств и методов.  
  
## Синтаксис  
  
```  
high_method_prefix("Prefix")  
```  
  
#### Параметры  
 `Prefix`  
 Префикс, который следует использовать.  
  
## Заметки  
 По умолчанию высокоуровневые свойства и методы обработки ошибок предоставляются функциями\-членами с именами без префикса.  Это имена из библиотеки типов.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)