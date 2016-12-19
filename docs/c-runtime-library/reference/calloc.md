---
title: "calloc | Microsoft Docs"
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
  - "calloc"
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
  - "calloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "выделение памяти, массивы"
  - "Функция calloc"
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# calloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет массив в памяти и инициализирует его элементы значением 0.  
  
## Синтаксис  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### Параметры  
 `num`  
 Количество элементов.  
  
 `size`  
 Длина в байтах каждого элемента.  
  
## Возвращаемое значение  
 `calloc` возвращает указатель на выделенную память.  Дисковое пространство, на которое указывает возвращаемое значение, гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от `void`, используйте приведение типа для возвращаемого значения.  
  
## Заметки  
 Функция `calloc` выделяет дисковое пространство для массива из `num` элементов, каждый из которых имеет размер `size`.  Каждый элемент инициализируется значением 0.  
  
 `calloc` задает для параметра `errno` значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 `calloc` вызывает `malloc` для использования функции C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md), чтобы установить новый режим обработки.  Указывает, может ли новый режим обработки, при сбое вызова `malloc`, использовать новую процедуру обработчика как набор [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `malloc` не вызывает новую процедуру обработчика при сбое выделения памяти.  Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти методом `calloc` метод `malloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор `new` при сбое по той же причине.  Чтобы переопределить значение по умолчанию, вызовите  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ \(см. [Параметры ссылок](../Topic/Link%20Options.md)\).  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, `calloc` соответствует [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `calloc` помечен `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`calloc`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
  **Allocated 40 long integers**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)