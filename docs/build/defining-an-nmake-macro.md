---
title: "Определение макроса NMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "определение макроса (NMAKE)"
  - "макросы, NMAKE - программа"
  - "макрос (NMAKE), определение"
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Определение макроса NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
macroname=string  
```  
  
## Заметки  
 *Имя\_макроса* представляет собой сочетание букв, цифр и знаков подчеркивания \(\_\) длиной до 1 024 символов, с учетом регистра.  *Имя\_макроса* может содержать вызванный макрос.  Если все *имя\_макроса* состоит из вызванного макроса, вызываемый макрос не может быть пустым или неопределенным.  
  
 `string` может быть любой последовательностью от ноля до нескольких знаков.  Пустая строка содержит ноль знаков или только пробелы, или знаки табуляции.  `string` может содержать вызов макроса.  
  
## Дополнительные сведения  
 [Специальные знаки в макросах](../build/special-characters-in-macros.md)  
  
 [Пустой и неопределенный макрос](../build/null-and-undefined-macros.md)  
  
 [Где следует определять макросы](../Topic/Where%20to%20Define%20Macros.md)  
  
 [Приоритет в определениях макросов](../build/precedence-in-macro-definitions.md)  
  
## См. также  
 [Макросы и программа NMAKE](../Topic/Macros%20and%20NMAKE.md)