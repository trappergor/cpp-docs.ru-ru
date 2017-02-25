---
title: "_query_new_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_handler"
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
  - "_query_new_handler"
  - "query_new_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_handler - функция"
  - "обработка ошибок"
  - "процедуры обработчика"
  - "query_new_handler - функция"
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает адрес текущей новой процедуры обработчика.  
  
## Синтаксис  
  
```  
  
      _PNH _query_new_handler(  
   void   
);  
```  
  
## Возвращаемое значение  
 Возвращает адрес текущей новой процедуры обработчика, установленный `_set_new_handler`.  
  
## Заметки  
 Функция `_query_new_handler` C\+\+ возвращает адрес текущей функции обработки исключений, установленный функцией [\_set\_new\_handler](../Topic/_set_new_handler.md) C\+\+.  `_set_new_handler` используется для определения функции обработки исключений, получающей управление, если происходит сбой при выделении памяти оператором **new**.  Дополнительные сведения см. в обсуждении функций [оператор new](../../misc/operator-new-function.md) и [оператор delete](../Topic/operator%20delete%20Function.md) в *Справочнике по языку C\+\+*.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_query_new_handler`|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)