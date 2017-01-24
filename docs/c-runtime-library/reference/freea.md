---
title: "_freea | Microsoft Docs"
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
  - "_freea"
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
apitype: "DLLExport"
f1_keywords: 
  - "freea"
  - "_freea"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_freea - функция"
  - "freea - функция"
  - "освобождение памяти"
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _freea
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает блок памяти.  
  
## Синтаксис  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### Параметры  
 `memblock`  
 Ранее выделенный блок памяти, который необходимо освободить.  
  
## Возвращаемое значение  
 Нет.  
  
## Заметки  
 Функция `_freea` освобождает блок памяти \(`memblock`\), который был выделен ранее вызовом [\_malloca](../../c-runtime-library/reference/malloca.md).  `_freea` проверяет, была ли выделена память в куче или в стеке.  Если была выделена в стеке, `_freea` не выполняет никаких действий.  Если была выделена в куче, число освобожденных байтов эквивалентно запрошенному при выделении блока количеству байтов.  Если `memblock` имеет значение `NULL`, указатель не обрабатывается и `_freea` немедленно возвращает управление.  Попытка освободить недопустимый указатель \(указатель на блок памяти, который не был выделен `_malloca`\) может повлиять на последующие запросы на выделение и вызывать ошибки.  
  
 \_`freea` вызывает `free` внутри, если обнаружит, что память выделена в куче.  Определение расположения памяти \(в куче или в стеке\) осуществляется с помощью маркера, размещенного в памяти по адресу непосредственно перед выделенной памятью.  
  
 При возникновении ошибки освобождения памяти, в `errno` заносятся данные операционной системы, которые объясняют причину ошибки.  Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 После освобождения блока памяти, [\_heapmin](../../c-runtime-library/reference/heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и передачи их обратно операционной системе.  Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.  
  
 Вызов `_freea` должен сопровождать все вызовы `_malloca`.  Вызов `_freea` дважды для одной и той же памяти является ошибкой.  Когда приложение скомпоновано с отладочной версией библиотеки времени выполнения C, особенно с возможностями [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md), активированными определением `_CRTDBG_MAP_ALLOC`, проще найти отсутствующие или дублированные вызовы `_freea`.  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_freea` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные.  Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_freea`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример в разделе [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)