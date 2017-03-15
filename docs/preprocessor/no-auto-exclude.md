---
title: "no_auto_exclude | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_auto_exclude"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_auto_exclude - атрибут"
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# no_auto_exclude
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Отключает автоматическое исключение.  
  
## Синтаксис  
  
```  
no_auto_exclude  
```  
  
## Заметки  
 Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов.  Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы.  В этом случае для каждого исключенного элемента будет выводиться ошибка [Предупреждение компилятора \(уровень 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md).  Отменить такое автоматическое исключение можно при помощи данного атрибута.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)