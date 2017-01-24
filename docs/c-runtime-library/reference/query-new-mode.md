---
title: "_query_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_mode"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "query_new_mode"
  - "_query_new_mode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_query_new_mode - функция"
  - "режимы обработчика"
  - "query_new_mode - функция"
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _query_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает целое число, указывающее новый режим обработчика, установленный `_set_new_mode`для `malloc`  
  
## Синтаксис  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## Возвращаемое значение  
 Возвращает текущий новый режим обработки, а именно 0 или 1, для `malloc`.  Возвращаемое значение, равное 1, означает, что при сбое выделения памяти `malloc` вызывает новую процедуру обработчика; возвращаемое значение 0 означает, что она этого не делает этого.  
  
## Заметки  
 Функция `_query_new_mode` языка C\+\+ возвращает целое число, указывающее новый режим обработчика, который устанавливается функцией [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) языка C\+\+ для [malloc](../../c-runtime-library/reference/malloc.md).  Новый режим обработчика указывает, должен ли `malloc` при сбое выделения памяти вызывать новую процедуру обработчика, которая задана [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `malloc` не вызывает новую процедуру обработчика при сбое.  Можно использовать `_set_new_mode`, чтобы переопределить это поведение, чтобы при сбое `malloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор **new** при сбое выделения памяти.  Дополнительные сведения см. в по функциям [оператора delete](../Topic/operator%20delete%20Function.md) и [оператора new](../../misc/operator-new-function.md) в *справочнике по языку C\+\+*.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_query_new_mode`|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)