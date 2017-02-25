---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_new_mode"
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
  - "set_new_mode"
  - "_set_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_new_mode - функция"
  - "режимы обработчика"
  - "set_new_mode - функция"
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _set_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает новый режим обработчика для `malloc`.  
  
## Синтаксис  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### Параметры  
 `newhandlermode`  
 Новый режим обработки для `malloc`; допустимые значения 0 или 1.  
  
## Возвращаемое значение  
 Возвращает предыдущий режим обработки, установленный для `malloc`.  Возвращаемое значение 1 означает, что при сбое выделения памяти `malloc` ранее вызывал новую процедуру обработчика; возвращаемое значение 0 означает, что он не делал этого.  Если аргумент `newhandlermode` не равен 0 или 1, возвращается –1.  
  
## Заметки  
 Функция C\+\+ `_set_new_mode` задает новый режим обработчика события [malloc](../../c-runtime-library/reference/malloc.md).  Указывает, может ли новый режим обработки, при сбое вызова `malloc`, использовать новую процедуру обработчика как набор [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `malloc` не вызывает новую процедуру обработчика при сбое выделения памяти.  Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти методом `malloc` метод `malloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор `new` при сбое по той же причине.  Дополнительные сведения см. в разделах [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) в *Справочнике по языку C\+\+*.  Чтобы переопределить значение по умолчанию, вызовите:  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или компонуйте с использованием Newmode.obj \(см. [Параметры ссылок](../Topic/Link%20Options.md)\).  
  
 Эта функция проверяет свой параметр.  Если `newhandlermode` отлично от 0 или 1, то функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то **\_**`set_new_mode` возвращает \-1 и устанавливает `errno` в `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_new_mode`|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [\_query\_new\_mode](../../c-runtime-library/reference/query-new-mode.md)