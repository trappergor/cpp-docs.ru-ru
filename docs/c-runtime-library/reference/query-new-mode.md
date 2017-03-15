---
title: "_query_new_mode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 38b5022412f3f07806fcb7a2cea373457c8b405f
ms.lasthandoff: 02/24/2017

---
# <a name="querynewmode"></a>_query_new_mode
Возвращает целое число, указывающее новый режим обработчика, заданный `_set_new_mode` для `malloc`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущий новый режим обработчика, а именно, 0 или 1, для `malloc`. Возвращаемое значение 1 указывает, что в случае сбоя процесса выделения памяти `malloc` вызывает новую подпрограмму обработчика; возвращаемое значение 0 указывает, что функция не выполняет этого действия.  
  
## <a name="remarks"></a>Примечания  
 Функция C++ `_query_new_mode`возвращает целое число, указывающее новый режим обработчика, заданный функцией C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) для [malloc](../../c-runtime-library/reference/malloc.md). Новый режим обработки указывает, должна ли функция `malloc` при сбое процесса выделения памяти вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). По умолчанию в случае сбоя `malloc` не вызывает новую подпрограмму обработчика. Можно использовать `_set_new_mode` для переопределения этого поведения по умолчанию, чтобы в случае сбоя предоставления памяти функция `malloc` вызывала новую подпрограмму обработчика таким же образом, как это делает оператор **new** при таком же сбое. Дополнительные сведения см. в разделе о [новых и удаленных операторах](../../cpp/new-and-delete-operators.md) справочника по языку C++.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)
