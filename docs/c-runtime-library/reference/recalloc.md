---
title: "_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc"
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
  - "_recalloc"
  - "recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_recalloc - функция"
  - "recalloc - функция"
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Комбинация `realloc` и `calloc`.  Перераспределяет массив в памяти и инициализирует его элементы значением 0.  
  
## Синтаксис  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### Параметры  
 `memblock`  
 Указатель на ранее выделенный блок памяти.  
  
 `num`  
 Количество элементов.  
  
 `size`  
 Длина в байтах каждого элемента.  
  
## Возвращаемое значение  
 `_recalloc` возвращает указатель `void` в перераспределенном \(и, возможно, перемещенном\) блоке памяти.  
  
 Если доступной памяти недостаточно, чтобы расширить блок до заданного размера, исходный блок останется без изменений и будет возвращен `NULL`.  
  
 Если запрошенный размер равен нулю, то блок, на который указывает `memblock`, освобождается; возвращается значение `NULL`, `memblock` дальше указывает на освобожденный блок.  
  
 Возвращаемое значение указывает на дисковое пространство, которое гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от `void`, используйте приведение типа для возвращаемого значения.  
  
## Заметки  
 Функция \_`recalloc` изменяет размер выделенного блока памяти.  Аргумент `memblock` указывает на начало блока памяти.  Если `memblock` равен `NULL`, \_`recalloc` ведет себя так же, как [calloc](../../c-runtime-library/reference/calloc.md), и выделяет новый блок размером `num` \* `size` байтов.  Каждый элемент инициализируется значением 0.  Если `memblock` не `NULL`, он должен быть указателем, возвращенным предыдущим вызовом `calloc`, [malloc](../../c-runtime-library/reference/malloc.md) или [realloc](../../c-runtime-library/reference/realloc.md).  
  
 Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный \_`recalloc`, не обязательно будет указателем, переданным через аргумент `memblock`.  
  
 `_recalloc` задает для параметра `errno` значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 `recalloc` вызывает `realloc` для использования функции C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md), чтобы установить новый режим обработки.  Указывает, может ли новый режим обработки, при сбое вызова `realloc`, использовать новую процедуру обработчика как набор [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `realloc` не вызывает новую процедуру обработчика при сбое выделения памяти.  Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти методом \_`recalloc` метод `realloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор `new` при сбое по той же причине.  Чтобы переопределить значение по умолчанию, вызовите  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, \_`recalloc` соответствует [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_recalloc` помечен `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_recalloc`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Параметры ссылок](../Topic/Link%20Options.md)