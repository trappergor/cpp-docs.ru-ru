---
title: "Выделение памяти | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.memory
dev_langs: C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cdaf9fe5b2d41491683d34ea029a546433cd709d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="memory-allocation"></a>Выделение памяти
Используйте эти подпрограммы для выделения, освобождения и повторного выделения памяти.  
  
### <a name="memory-allocation-routines"></a>Подпрограммы выделения памяти  
  
|Подпрограмма|Применение|  
|-------------|---------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Выделение памяти из стека|  
|[calloc](../c-runtime-library/reference/calloc.md)|Выделение хранилища для массива, инициализация всех байт в выделенном блоке нулями.|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Отладочная версия `calloc`; доступна только в отладочных версиях библиотек среды выполнения|  
|[Оператор delete](../c-runtime-library/operator-delete-crt.md)|Освобождение выделенного блока|  
|[оператор delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Освобождение выделенного блока|  
|[_expand](../c-runtime-library/reference/expand.md)|Расширение или сжатие блока памяти без перемещения|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Отладочная версия `_expand`; доступна только в отладочных версиях библиотек среды выполнения|  
|[free](../c-runtime-library/reference/free.md)|Освобождение выделенного блока|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Отладочная версия `free`; доступна только в отладочных версиях библиотек среды выполнения|  
|[_freea](../c-runtime-library/reference/freea.md)|Освобождение выделенного блока из стека|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Получение HANDLE Win32 кучи CRT.|  
|[_heapadd](../c-runtime-library/heapadd.md)|Добавление памяти в кучу|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Проверка согласованности кучи|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Освобождение неиспользуемой памяти в куче|  
|[_heapset](../c-runtime-library/heapset.md)|Заполнение свободных записей кучи указанным значением|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Возвращение сведений о каждой записи в куче|  
|[malloc](../c-runtime-library/reference/malloc.md)|Выделение блока памяти из кучи|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Отладочная версия `malloc`; доступна только в отладочных версиях библиотек среды выполнения|  
|[_msize](../c-runtime-library/reference/msize.md)|Возвращение размера выделенного блока|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Отладочная версия `_msize`; доступна только в отладочных версиях библиотек среды выполнения|  
|[new](../c-runtime-library/operator-new-crt.md)|Выделение блока памяти из кучи|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Выделение блока памяти из кучи|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Возвращение адреса текущей новой процедуры обработчика, как задано `_set_new_handler`|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Возвращение целого числа, указывающего новый режим обработчика, заданный `_set_new_mode` для `malloc`|  
|[realloc](../c-runtime-library/reference/realloc.md)|Перераспределение нового размера блока|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Отладочная версия `realloc`; доступна только в отладочных версиях библиотек среды выполнения|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Включение механизма обработки ошибок в случае сбоя оператора `new` (при выделении памяти) и включение компиляции стандартных библиотек C++|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|Установка нового режима обработчика для `malloc`|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)