---
title: "free | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- free
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fa01be1421c4b241a86a02e97cb444404ce8f734
ms.lasthandoff: 02/24/2017

---
# <a name="free"></a>free
Освобождает блок памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Ранее выделенный блок памяти, который требуется освободить.  
  
## <a name="remarks"></a>Примечания  
 Функция `free` освобождает блок памяти (`memblock`), который был выделен ранее вызовом функции `calloc`, `malloc` или `realloc`. Число освобожденных байтов эквивалентно количеству байтов, запрошенному при выделении блока (или выделении заново, если использовалась функция `realloc`). Если `memblock` имеет значение `NULL`, указатель не обрабатывается и функция `free` немедленно возвращает управление. Попытка освободить недопустимый указатель (указатель на блок памяти, который не был выделен функцией `calloc`, `malloc` или `realloc`) может повлиять на последующие запросы выделения памяти и вызвать ошибки.  
  
 В случае возникновения ошибки при освобождении памяти для `errno` задаются сведения о характере сбоя, полученные от операционной системы. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 После освобождения блока памяти функция [_heapmin](../../c-runtime-library/reference/heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, функция `free` соответствует функции [_free_dbg](../../c-runtime-library/reference/free-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Функция `free` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
 Для освобождения памяти, которая выделена функцией [_malloca](../../c-runtime-library/reference/malloca.md), используйте функцию [_freea](../../c-runtime-library/reference/freea.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`free`|\<stdlib.h> и \<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [malloc](../../c-runtime-library/reference/malloc.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)
