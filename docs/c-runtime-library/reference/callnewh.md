---
title: _callnewh
ms.date: 11/04/2016
apiname:
- _callnewh
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
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 98526f6c8c40b71104345563db71ef098b6cfb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643668"
---
# <a name="callnewh"></a>_callnewh

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
|0|Ошибка: новый обработчик либо не установлен, либо не активен.|
|1|Успешное завершение: новый обработчик установлен и активен. Выделение памяти можно повторить.|

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
