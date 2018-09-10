---
title: Интерфейс Platform::IBox | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 540b759153b8fac0532a8817d89e704d55fbffd3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102082"
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

|Метод|Описание|
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