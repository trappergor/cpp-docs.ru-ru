---
title: Интерфейс Platform::IBoxArray
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: a35a8b7d9f23bcb624755353e27e52de4b873c5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497047"
---
# <a name="platformiboxarray-interface"></a>Интерфейс Platform::IBoxArray

`IBoxArray` является оболочкой для массивов типов значений, передаваемых через двоичный интерфейс приложений (ABI) или хранящихся в коллекциях элементов `Platform::Object^` , таких как коллекции в элементах управления XAML.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип упакованного значение в каждом элементе массива.

### <a name="remarks"></a>Примечания

`IBoxArray` — Это C + +/ CX имя `Windows::Foundation::IReferenceArray`.

### <a name="members"></a>Участники

Интерфейс `IBoxArray` наследует от интерфейса `IValueType` . Интерфейс`IBoxArray` также содержит следующие члены:

|Метод|Описание|
|------------|-----------------|
|[Значение](#value)|Возвращает распакованный массив, который ранее хранился в этом экземпляре `IBoxArray` .|

## <a name="value"></a> Свойство IBoxArray::Value

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

[Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)