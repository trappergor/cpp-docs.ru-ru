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
ms.openlocfilehash: ea2517ad64cfd6742ef072d24e94a9b3899cea2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392080"
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

`IBoxArray` — C++имя /CX `Windows::Foundation::IReferenceArray`.

### <a name="members"></a>Участники

Интерфейс `IBoxArray` наследует от интерфейса `IValueType` . Интерфейс`IBoxArray` также содержит следующие члены:

|Метод|Описание|
|------------|-----------------|
|[Значение](#value)|Возвращает распакованный массив, который ранее хранился в этом экземпляре `IBoxArray` .|

## <a name="value"></a> IBoxArray::Value Property

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
