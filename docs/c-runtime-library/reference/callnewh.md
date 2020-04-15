---
title: _callnewh
ms.date: 4/2/2020
api_name:
- _callnewh
- _o__callnewh
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: d93de7f963a370810ed3b30af04d6d602abf6313
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333665"
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

*Размер*<br/>
Объем памяти, который [оператор new](../../cpp/new-operator-cpp.md) пытается выделить.

## <a name="return-value"></a>Возвращаемое значение

|Значение|Описание|
|-----------|-----------------|
|0|Ошибка: новый обработчик либо не установлен, либо не активен.|
|1|Успешное завершение: новый обработчик установлен и активен. Выделение памяти можно повторить.|

## <a name="exceptions"></a>Исключения

Эта функция вызывает [bad_alloc](../../standard-library/bad-alloc-class.md), если *новый обработчик* обнаружить не удается.

## <a name="remarks"></a>Remarks

*Новый обработчик* вызывается, если [оператору new](../../cpp/new-operator-cpp.md) не удается успешно выделить память. После этого новый обработчик может инициировать соответствующее действие, например освобождение памяти для успешного выполнения последующих распределений.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>См. также раздел

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
