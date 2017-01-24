---
title: "_except_handler3 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_except_handler3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_except_handler3"
  - "except_handler3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_except_handler3 - функция"
  - "except_handler3 - функция"
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _except_handler3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя функция CRT.  Используется платформой для поиска подходящего обработчика исключений для обработки текущего исключения.  
  
## Синтаксис  
  
```  
int _except_handler3(    PEXCEPTION_RECORD exception_record,    PEXCEPTION_REGISTRATION registration,    PCONTEXT context,    PEXCEPTION_REGISTRATION dispatcher );  
```  
  
#### Параметры  
 \[входной\] `exception_record`  
 Сведения о конкретном исключении.  
  
 \[входной\] `registration`  
 Запись, которая указывает, какую таблицу области следует использовать для поиска обработчика исключений.  
  
 \[входной\] `context`  
 Зарезервировано.  
  
 \[входной\] `dispatcher`  
 Зарезервировано.  
  
## Возвращаемое значение  
 Если исключение должно быть отброшено, возвращает значение `DISPOSITION_DISMISS`.  Если исключение должно быть передано на уровень вверх в инкапсулируемые обработчики исключений, возвращает значение `DISPOSITION_CONTINUE_SEARCH`.  
  
## Заметки  
 Если этот метод находит подходящий обработчик исключений, он передает исключение в обработчик.  В этой ситуации метод не возвращается к вызвавшему его коду, и возвращаемое значение несущественно.  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)