---
title: __RTDynamicCast
ms.date: 11/04/2016
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: c4b0caadf20d6c5494acf47ee5a788b5ee009c47
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957339"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

Реализация оператора [dynamic_cast](../cpp/dynamic-cast-operator.md) в среде выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>Параметры

*inptr*<br/>
Указатель на полиморфный объект.

*VfDelta*<br/>
Смещение указателя на виртуальную функцию в объекте.

*SrcType*<br/>
Статический тип объекта, на который указывает параметр `inptr`.

*TargetType*<br/>
Планируемый результат преобразования.

*isReference*<br/>
Значение **true**, если входные данные являются ссылкой; значение **false**, если входные данные являются указателем.

## <a name="return-value"></a>Возвращаемое значение

Указатель на соответствующий подобъект при успехе; в противном случае — значение **NULL**.

## <a name="exceptions"></a>Исключения

`bad_cast()`, если входное значение `dynamic_cast<>` является ссылкой и приведение завершается неудачей.

## <a name="remarks"></a>Примечания

Преобразует `inptr` в объект типа `TargetType`. Тип операнда `inptr` должен быть указателем, если `TargetType` является указателем, или l-значением, если `TargetType` является ссылкой. Параметр `TargetType` должен быть указателем или ссылкой на ранее определенный тип класса или указателем на void.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|