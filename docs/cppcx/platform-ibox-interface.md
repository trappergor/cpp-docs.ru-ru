---
title: Интерфейс Platform::IBox
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
ms.openlocfilehash: 24e70ad646e2673869b135e8cc7657910b9b499c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747064"
---
# <a name="platformibox-interface"></a>Интерфейс Platform::IBox

[Platform::IBox](../cppcx/platform-ibox-interface.md) — это имя C++ для интерфейса `Windows::Foundation::IReference` .

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
interface class IBox
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Введите запакованное значение.

### <a name="remarks"></a>Примечания

Интерфейс `IBox<T>` в основном используется внутри кода для представления типов значений, допускающих значение null, как описано в разделе [Классы и структуры значения (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md). Этот интерфейс также используется для упаковки типов значений, передаваемых в методы C++, которые принимают параметры типа `Object^`. Можно в явном виде определить входной параметр как `IBox<SomeValueType>`. Например, см. в разделе [упаковки-преобразования](../cppcx/boxing-c-cx.md).

### <a name="requirements"></a>Требования

### <a name="members"></a>Участники

Интерфейс `Platform::IBox` наследуется от интерфейса [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) . Интерфейс`IBox` содержит следующие члены:

**Свойства**

|Метод|Описание:|
|------------|-----------------|
|[Значение](#value)|Возвращает распакованное значение, которое ранее хранилось в этом экземпляре `IBox` .|

## <a name="value"></a> Свойство IBox::Value

Возвращает значение, которое было изначально сохранено в этом объекте.

### <a name="syntax"></a>Синтаксис

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Параметры

*T*<br/>
Введите запакованное значение.

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Возвращает значение, которое было изначально сохранено в этом объекте.

### <a name="remarks"></a>Примечания

Например, см. в разделе [упаковки-преобразования](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
