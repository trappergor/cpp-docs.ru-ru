---
title: _query_new_mode
ms.date: 11/04/2016
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
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 327f22c847793316bd126721b4a66846d7da84dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620029"
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

Возвращает текущий новый режим обработчика, а именно, 0 или 1, для **malloc**. Возвращаемое значение 1 указывает, что в случае сбоя процесса выделения памяти, **malloc** вызывает новую подпрограмму обработчика; возвращаемое значение 0 указывает, что это не так.

## <a name="remarks"></a>Примечания

C++ **_query_new_mode** функция возвращает целое число, указывающее новый режим обработчика, заданный функцией C++ [_set_new_mode](set-new-mode.md) работать для [malloc](malloc.md). Новый режим обработки указывает, что в случае сбоя выделения памяти **malloc** должен вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограмму обработчика в случае сбоя. Можно использовать **_set_new_mode** Чтобы переопределить это поведение, так что, в случае сбоя **malloc** вызывала новую подпрограмму обработчика таким же образом, как **новый** делает оператор при возникновении ошибки Выделите память. Дополнительные сведения см. в разделе о [новых и удаленных операторах](../../cpp/new-and-delete-operators.md) справочника по языку C++.

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
