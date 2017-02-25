---
title: "check_stack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.check_stack"
  - "check_stack_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "check_stack - прагма"
  - "прагмы, check_stack"
  - "прагмы, check_stack - таблица использования"
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# check_stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает компилятору на необходимость выключения стековых зондов, если задано значение **off** \(или **–**\), либо включения стековых зондов, если задано значение **on** \(или **\+**\).  
  
## Синтаксис  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | –}  
```  
  
## Заметки  
 Если аргумент не указан, стековые зонды обрабатываются в соответствии с настройкой по умолчанию.  Эта директива \#pragma начинает действовать с первой функции, определенной после вхождения данной директивы.  Стековые зонды не являются частью макросов или функций, создаваемых как встроенные.  
  
 Если аргумент директивы \#pragma **check\_stack** не задан, используется проверка стека, указанная в командной строке.  Дополнительные сведения см. в [справочнике по компилятору](../build/reference/compiler-options.md).  Сводка взаимодействия директивы **\#pragma check\_stack** и параметра [\/Gs](../build/reference/gs-control-stack-checking-calls.md) приведена в следующей таблице.  
  
### Использование директивы \#pragma check\_stack  
  
|Синтаксис|Скомпилировано с использованием<br /><br /> параметра \/Gs?|Действие|  
|---------------|---------------------------------------------------------|--------------|  
|**\#pragma check\_stack\( \)** или<br /><br /> **\#pragma check\_stack**|Да|Отключает проверку стека для последующих функций|  
|**\#pragma check\_stack\( \)** или<br /><br /> **\#pragma check\_stack**|Нет|Включает проверку стека для последующих функций|  
|**\#pragma check\_stack\(on\)**<br /><br /> или **\#pragma check\_stack \+**|"Да" или "Нет"|Включает проверку стека для последующих функций|  
|**\#pragma check\_stack\(off\)**<br /><br /> или **\#pragma check\_stack –**|"Да" или "Нет"|Отключает проверку стека для последующих функций|  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)