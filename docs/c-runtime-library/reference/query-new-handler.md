---
title: "_query_new_handler | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _query_new_handler
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
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61ace3b5d57515ee10fbb58992f708a465064980
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="querynewhandler"></a>_query_new_handler
Возвращает адрес текущей новой подпрограммы обработчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес текущей новой подпрограммы обработчика, как задано `_set_new_handler`.  
  
## <a name="remarks"></a>Примечания  
 Функция C++ `_query_new_handler` возвращает адрес текущей функции обработки исключений, заданной функцией C++ [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Функция `_set_new_handler` используется для определения функции обработки исключений, которая получает управление, если оператор **new** не смог выделить память. Дополнительные сведения см. в разделе о [новых и удаленных операторах](../../cpp/new-and-delete-operators.md) справочника по языку C++.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)