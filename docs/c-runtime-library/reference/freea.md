---
title: "_freea | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _freea
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
apitype: DLLExport
f1_keywords:
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf2bd2d3dacba307f529798727e7af745bf7cf9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="freea"></a>_freea
Освобождает блок памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Ранее выделенный блок памяти, который требуется освободить.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Отсутствует.  
  
## <a name="remarks"></a>Примечания  
 Функция `_freea` освобождает блок памяти (`memblock`), который был выделен ранее вызовом функции [_malloca](../../c-runtime-library/reference/malloca.md). Функция `_freea` проверяет, была ли память выделена в стеке или в куче. Если она была выделена в стеке, функция `_freea` не выполняет никаких действий. Если память выделена в куче, число освобожденных байтов эквивалентно количеству байтов, запрошенному при выделении блока. Если `memblock` имеет значение `NULL`, указатель не обрабатывается и функция `_freea` немедленно возвращает управление. Попытка освободить недопустимый указатель (указатель на блок памяти, который не был выделен функцией `_malloca`) может повлиять на последующие запросы выделения памяти и вызвать ошибки.  
  
 `_freea` вызовы `free` внутренним образом в том случае, если обнаруживается, что память выделяется в куче. Информация о том, выделена ли память в куче или в стеке, определяется меткой, которая устанавливается в памяти по адресу, непосредственно предшествующему выделенному блоку памяти.  
  
 В случае возникновения ошибки при освобождении памяти для `errno` задаются сведения о характере сбоя, полученные от операционной системы. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 После освобождения блока памяти функция [_heapmin](../../c-runtime-library/reference/heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.  
  
 Вызов `_freea` должен сопровождать все вызовы `_malloca`. Повторный вызов функции `_freea` для того же блока памяти приведет к ошибке. Если приложение связано с отладочной версией библиотеки времени выполнения C, в особенности в том случае, если функции [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) включены посредством определения `_CRTDBG_MAP_ALLOC`, найти пропущенные или повторные вызовы функции `_freea` будет проще. Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Функция `_freea` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h> и \<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)