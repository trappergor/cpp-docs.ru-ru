---
title: "realloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "realloc"
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
  - "_brealloc"
  - "_nrealloc"
  - "realloc"
  - "_frealloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция _brealloc"
  - "Функция realloc"
  - "Функция nrealloc"
  - "Функция frealloc"
  - "Функция _nrealloc"
  - "блоки памяти, повторное выделение"
  - "память, повторное выделение"
  - "Функция _frealloc"
  - "повторное выделение блоков памяти"
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перераспределяет блоки памяти.  
  
## Синтаксис  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### Параметры  
 `memblock`  
 Указатель на ранее выделенный блок памяти.  
  
 `size`  
 Новый размер в байтах.  
  
## Возвращаемое значение  
 `realloc` возвращает указатель `void` в перераспределенном \(и, возможно, перемещенном\) блоке памяти.  
  
 Если доступной памяти недостаточно, чтобы расширить блок до заданного размера, исходный блок останется без изменений и будет возвращен `NULL`.  
  
 Если `size` равен нулю, то блок, на который указывает `memblock`, освобождается; возвращаемое значение равно `NULL`, и `memblock` продолжает указывать на освобождённый блок.  
  
 Возвращаемое значение указывает на дисковое пространство, которое гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от `void`, используйте приведение типа для возвращаемого значения.  
  
## Заметки  
 Функция `realloc` изменяет размер выделенного блока памяти.  Аргумент `memblock` указывает на начало блока памяти.  Если `memblock` равен `NULL`, `realloc` ведет себя так же, как `malloc`, и выделяет новый блок размером `size` байтов.  Если `memblock` не `NULL`, он должен быть указателем, возвращенным предыдущим вызовом `calloc`, `malloc` или `realloc`.  
  
 Аргумент `size` предоставляет новый размер блока в байтах.  Содержимое блока неизменны до меньшего из старого и нового размеров, хотя новый блок может находиться в другом месте.  Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный `realloc`, не обязательно будет указателем, переданным через аргумент `memblock`.  `realloc` не обнуляет вновь выделенную память в случае роста буфера.  
  
 `realloc` задает для параметра `errno` значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 `realloc` вызывает `malloc`, чтобы использовать C\+\+ функцию [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) для установки нового режима обработки.  Указывает, может ли новый режим обработки, при сбое вызова `malloc`, использовать новую процедуру обработчика как набор [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `malloc` не вызывает новую процедуру обработчика при сбое выделения памяти.  Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти методом `realloc` метод `malloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор `new` при сбое по той же причине.  Чтобы переопределить значение по умолчанию, вызовите  
  
```  
_set_new_mode(1)  
```  
  
 ранее в программе или выполняйте компоновку с NEWMODE.OBJ \(см. [Параметры ссылок](../Topic/Link%20Options.md)\).  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, `realloc` соответствует [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `realloc` помечен `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`realloc`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **Size of block after malloc of 1000 longs: 4000**  
**Size of block after realloc of 1000 more longs: 8000**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)