---
title: _callnewh
ms.date: 11/04/2016
api_name:
- _callnewh
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 3e14450538807b164897c335f7e37d82d8562314
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939380"
---
# <a name="_callnewh"></a>_callnewh

Вызывает *новый обработчик*, установленный на данный момент.

## <a name="syntax"></a>Синтаксис

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Параметры

*size*<br/>
Объем памяти, который [оператор new](../../cpp/new-operator-cpp.md) пытается выделить.

## <a name="return-value"></a>Возвращаемое значение

|Значение|Описание|
|-----------|-----------------|
|0|Состояние Либо новый обработчик не установлен, либо новый обработчик не активен.|
|1|Загрузоч Новый обработчик установлен и активен. Выделение памяти можно повторить.|

## <a name="exceptions"></a>Исключения

Эта функция вызывает [bad_alloc](../../standard-library/bad-alloc-class.md), если *новый обработчик* обнаружить не удается.

## <a name="remarks"></a>Примечания

*Новый обработчик* вызывается, если [оператору new](../../cpp/new-operator-cpp.md) не удается успешно выделить память. После этого новый обработчик может инициировать соответствующее действие, например освобождение памяти для успешного выполнения последующих распределений.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>См. также

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
