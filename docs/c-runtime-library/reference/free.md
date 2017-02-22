---
title: "free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "free"
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
  - "free"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "блоки памяти, освобождение"
  - "Функция free"
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает блок памяти.  
  
## Синтаксис  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### Параметры  
 `memblock`  
 Ранее выделенный блок памяти, который необходимо освободить.  
  
## Заметки  
 Функция `free` освобождает блок памяти \(`memblock`\), который был выделен ранее вызовом `calloc`, `malloc` или `realloc`.  Число освобожденных байтов равно количеству байтов, которые были выделены \(или выделены заново, если использовалась функция `realloc`\).  Если `memblock` имеет значение `NULL`, указатель не обрабатывается и `free` немедленно возвращает управление.  Попытка освободить недопустимый указатель \(указатель на блок памяти, который не был выделен `calloc`, `malloc` или `realloc`\) может повлиять на последующие запросы на выделение и вызывать ошибки.  
  
 При возникновении ошибки освобождения памяти, в `errno` заносятся данные операционной системы, которые объясняют причину ошибки.  Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 После освобождения блока памяти, [\_heapmin](../../c-runtime-library/reference/heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и передачи их обратно операционной системе.  Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, `free` соответствует [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `free` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные.  Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
 Для освобождения памяти, которая выделена [\_malloca](../../c-runtime-library/reference/malloca.md), используйте [\_freea](../../c-runtime-library/reference/freea.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`free`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [malloc](../../c-runtime-library/reference/malloc.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [\_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_freea](../../c-runtime-library/reference/freea.md)