---
title: "_msize | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _msize
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
- msize
- _msize
dev_langs: C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e678d5ba1abcf552fa5e4576578a5a220fe50f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="msize"></a>_msize
Возвращает размер блока памяти, выделенного в куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на блок памяти.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_msize` возвращает размер (в байтах) как целое число без знака.  
  
## <a name="remarks"></a>Примечания  
 Функция `_msize` возвращает размер блока памяти (в байтах), выделенного вызовом функции `calloc`, `malloc` или `realloc`.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, функция `_msize` соответствует функции [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Эта функция проверяет свои параметры. Кроме того, если `memblock` является пустым указателем, функция `_msize` вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка обработана, функция задает для параметра `errno` значение `EINVAL` и возвращает –1.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример использования функции [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)