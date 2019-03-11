---
title: Platform::ValueType - класс
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 889cf3a53468491517d37978ca09472756ad9b7e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747155"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType - класс

Базовый класс для экземпляров типов значений.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[ValueType::ToString](#tostring)|Возвращает строковое представление объекта. Наследуется от [Platform::Object](../cppcx/platform-object-class.md).|

### <a name="remarks"></a>Примечания

Класс ValueType используется для создания типов значений. Класс ValueType является производным от класса Object, который содержит базовые элементы. Однако компилятор отсоединяет эти базовые элементы от типов значений, которые являются производными от класса ValueType. При упаковке типа значения компилятор снова присоединяет эти базовые элементы.

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="tostring"></a> Метод ValueType::ToString

Возвращает строковое представление объекта.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Представляющий значение Platform::String.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
