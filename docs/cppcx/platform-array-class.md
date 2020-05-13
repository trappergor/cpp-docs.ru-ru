---
title: Класс Platform::Array
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Array
- VCCORLIB/Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: d625d80df67a3c8207467ad629afd4c2bf88db18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318659"
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

Платформа::Array наследует все свои методы от [платформы::WriteOnlyArray класса](../cppcx/platform-writeonlyarray-class.md) и реализует `Value` свойство [платформы::IBoxArray Интерфейс](../cppcx/platform-iboxarray-interface.md).

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструкторы массивов](#ctor)|Инициализирует одномерный, изменяемый массив типов, указанный параметром шаблона класса, *T*.|

### <a name="methods"></a>Методы

Смотрите [платформу::WriteOnlyArray класса](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Свойства

|||
|-|-|
|[Массив::Значение](#value)|Получает дескриптор текущего массива.|

### <a name="remarks"></a>Remarks

Класс Array является запечатанным и наследовать его нельзя.

Система типа Windows Runtime не поддерживает концепцию зубчатых массивов и поэтому не\<может пройти iVector<Platform::Array T>> как значение возврата или параметр метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

Для получения дополнительной информации о том, когда и как использовать платформу:: Array, [см.](../cppcx/array-and-writeonlyarray-c-cx.md)

Этот класс определен в заголовке vccorlib.h, который автоматически включается компилятором. Это видно в IntelliSense, но не в объекте браузера, потому что это не публичный тип, определенный в platform.winmd.

### <a name="requirements"></a>Требования

Вариант компилятора: **/ ЗВ**

## <a name="array-constructors"></a><a name="ctor"></a>Конструкторы массивов

Инициализирует одномерный, изменяемый массив типов, указанный параметром шаблона класса, *T*.

## <a name="syntax"></a>Синтаксис

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Параметр шаблона класса.

*Размер*<br/>
Количество элементов в массиве.

*данные*<br/>
Указатель на массив данных типа `T`, используемый для инициализации данного объекта Array.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о том, как создавать экземпляры Платформы:: Array, [см. Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="arrayget-method"></a><a name="get"></a>Array::получить метод

Извлекает ссылку на элемент массива с указанным индексом.

## <a name="syntax"></a>Синтаксис

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Параметры

*Индекс*<br/>
Отсчитываемый от нуля индекс, указывающий на элемент в массиве. Минимальный индекс равен 0, а максимальным `size` индексом является значение, указанное параметром в [конструкторе Array.](#ctor)

### <a name="return-value"></a>Возвращаемое значение

Элемент массива, заданный параметром `index`.

## <a name="arrayvalue-property"></a><a name="value"></a>Array::Значение свойства

Получает дескриптор текущего массива.

## <a name="syntax"></a>Синтаксис

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор текущего массива.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)<br/>
[Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
