---
title: "inject_statement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inject_statement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inject_statement - атрибут"
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# inject_statement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.  
  
## Синтаксис  
  
```  
inject_statement("source_text")  
```  
  
#### Параметры  
 `source_text`  
 Исходный текст, вставляемый в файл заголовка библиотеки типов.  
  
## Заметки  
 Текст вставляется в начало объявления пространства имен, в которое помещается содержимое библиотеки типов в файле заголовка.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)