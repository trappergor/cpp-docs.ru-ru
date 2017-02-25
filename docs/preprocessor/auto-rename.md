---
title: "auto_rename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_rename"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_rename - атрибут"
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# auto_rename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Переименовывает зарезервированные слова C\+\+ путем добавления двух знаков подчеркивания \(\_\_\) к именам переменных, чтобы разрешить потенциальные конфликты имен.  
  
## Синтаксис  
  
```  
auto_rename  
```  
  
## Заметки  
 Этот атрибут используется при импорте библиотеки типов, в которой в качестве имен переменных используется одно или несколько зарезервированных слов C или C\+\+ \(ключевых слов или макросов\).  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)