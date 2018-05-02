---
title: _query_new_mode | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 67a7b52bc2a16e5c87e6ba83c3ba9c2710c2ed88
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="querynewmode"></a>_query_new_mode

Возвращает целое число, указывающее новый режим обработчика, заданный **_set_new_mode** для **malloc**.

## <a name="syntax"></a>Синтаксис

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает текущий новый режим обработки, а именно: 0 или 1, для **malloc**. Возвращаемое значение 1 указывает, что на сбои при выделении памяти, **malloc** вызывает новую подпрограмму обработчика; возвращаемое значение 0 указывает, что это не.

## <a name="remarks"></a>Примечания

C++ **_query_new_mode** функция возвращает целое число, указывающее новый режим обработки, который задается параметром C++ [_set_new_mode](set-new-mode.md) функции для [malloc](malloc.md). Новый режим обработки указывает, должна ли сбои при выделении памяти, **malloc** является вызов новую подпрограмму обработчика задается [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывать новую подпрограмму обработчика в случае ошибки. Можно использовать **_set_new_mode** Чтобы переопределить это поведение, поэтому, при сбое **malloc** вызывает новую подпрограмму обработчика так же, как **новый** делает оператор в случае сбоя на Выделите память. Дополнительные сведения см. в разделе о [новых и удаленных операторах](../../cpp/new-and-delete-operators.md) справочника по языку C++.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
