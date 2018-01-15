---
title: "free | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: free
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
f1_keywords: free
dev_langs: C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be3f7141a8483aa7b0d43195b08506691e34fe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)