---
title: "_heapadd | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs: C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85f13e082e25702967868d6889e575a6e261f6b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="heapadd"></a>_heapadd
Добавляет память в кучу.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на память кучи.  
  
 `size`  
 Размер добавляемой памяти в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения `_heapadd` возвращает 0; в противном случае функция возвращает –1 и задает для `errno` значение `ENOSYS`.  
  
 Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Начиная с Visual C++ версии 4.0 базовая структура кучи перемещена в библиотеки среды выполнения C для обеспечения поддержки новых функций отладки. В результате `_heapadd` больше не поддерживается на какой-либо платформе, основанной на Win32 API.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_heapadd`|\<malloc.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)