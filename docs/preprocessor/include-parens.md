---
title: "include() | Microsoft Docs"
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
  - "include()"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include() - атрибут"
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Отключает автоматическое исключение.  
  
## Синтаксис  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### Параметры  
 `Name1`  
 Первый элемент для принудительного включения.  
  
 `Name2`  
 Второй элемент для принудительного включения \(при необходимости\).  
  
## Заметки  
 Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов.  Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы.  Если элементы включены, на что указывает [Предупреждение компилятора \(уровень 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), в то время как они не должны были быть включены, этот атрибут может использоваться для отключения автоматического исключения.  Этот атрибут может принимать любое количество аргументов, каждый из которых является именем включаемого элемента библиотеки типов.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)