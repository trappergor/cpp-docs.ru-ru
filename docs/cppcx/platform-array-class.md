---
title: Класс Platform::Array
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: 597f8e32e2da95370169cdbfe2ccd209296322cc
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751665"
---
# <a name="platformarray-class"></a>Класс Platform::Array

Представляет изменяемый одномерный массив, который можно получать и передавать через двоичный интерфейс приложений (ABI).

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Участники

Platform::Array наследует все его методы из [класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) и реализует `Value` свойство [интерфейс Platform::IBoxArray](../cppcx/platform-iboxarray-interface.md).

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструкторы массивов](#ctor)|Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.|

### <a name="methods"></a>Методы

См. в разделе [класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Свойства

|||
|-|-|
|[Array::Value](#value)|Получает дескриптор текущего массива.|

### <a name="remarks"></a>Примечания

Класс Array является запечатанным и наследовать его нельзя.

Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и поэтому невозможно передать IVector < Platform::Array\<T >> как возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

Дополнительные сведения о времени и как использовать Platform::Array, см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и поэтому невозможно передать IVector < Platform::Array\<T >> как возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

Этот класс определен в заголовке vccorlib.h, который автоматически включается компилятором. Он отображается в IntelliSense, но не в обозревателе объектов, так как он не открытого типа, определенного в platform.winmd.

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

## <a name="ctor"></a>  Конструкторы массивов

Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.

## <a name="syntax"></a>Синтаксис

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Параметр шаблона класса.

*size*<br/>
Количество элементов в массиве.

*data*<br/>
Указатель на массив данных типа `T`, используемый для инициализации данного объекта Array.

### <a name="remarks"></a>Примечания

Дополнительные сведения о том, как создавать экземпляры Platform::Array, см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Метод Array::Get

Извлекает ссылку на элемент массива с указанным индексом.

## <a name="syntax"></a>Синтаксис

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Параметры

*Индекс*<br/>
Отсчитываемый от нуля индекс, указывающий на элемент в массиве. Минимальный индекс равен 0, а максимальный индекс равен значению, заданному в `size` параметр в [Array-конструктор](#ctor).

### <a name="return-value"></a>Возвращаемое значение

Элемент массива, заданный параметром `index`.

## <a name="value"></a>  Свойство Array::value

Получает дескриптор текущего массива.

## <a name="syntax"></a>Синтаксис

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор текущего массива.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)<br/>
[Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
