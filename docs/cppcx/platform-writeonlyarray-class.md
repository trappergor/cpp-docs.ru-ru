---
title: Класс Platform::WriteOnlyArray
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
ms.openlocfilehash: 5652123d4866262515f804dba790af51610eb426
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500523"
---
# <a name="platformwriteonlyarray-class"></a>Класс Platform::WriteOnlyArray

Представляет одномерный массив, который используется в качестве входного параметра, когда вызывающая сторона передает массив в метод для заполнения.

Этот класс ссылок объявлен в vccorlib.h как закрытый; следовательно, он не передается в метаданные и использовать его можно только из С++. Этот класс предназначен для использования только в качестве входного параметра, который получает массив, выделенный вызывающим объектом. Его невозможно построить из пользовательского кода. Оно позволяет методу C++ осуществлять запись непосредственно в этот массив — шаблон, известный как *FillArray* . Дополнительные сведения см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="syntax"></a>Синтаксис

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Эти методы имеют внутреннюю доступность, то есть доступны только в компоненте или приложении С++.

|name|Описание|
|----------|-----------------|
|[WriteOnlyArray:: Begin](#begin)|Итератор, который указывает на первый элемент массива.|
|[WriteOnlyArray::D ATA](#data)|Указатель на буфер данных.|
|[WriteOnlyArray:: end](#end)|Итератор, указывающий на элемент, следующий за последним элементом в массиве.|
|[WriteOnlyArray:: FastPass](#fastpass)|Указывает, сможет ли массив использовать механизм FastPass, то есть прозрачную оптимизацию, выполняемую системой. Не используйте его в коде|
|[WriteOnlyArray:: Length](#length)|Возвращает число элементов в массиве.|
|[WriteOnlyArray::set](#set)|Присваивает заданному элементу заданное значение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WriteOnlyArray`

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

**Метаданных** Platform. winmd

**Пространство имен:** Платформа

## <a name="begin"></a>  Метод WriteOnlyArray::begin

Возвращает указатель на первый элемент массива.

### <a name="syntax"></a>Синтаксис

```cpp
T* begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый элемент массива.

### <a name="remarks"></a>Примечания

Этот итератор можно использовать с алгоритмами STL, такими как `std::sort`, для выполнения действий с элементами в массиве.

## <a name="data"></a>  Свойство WriteOnlyArray::Data

Указатель на буфер данных.

### <a name="syntax"></a>Синтаксис

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные байты массива.

## <a name="end"></a>  Метод WriteOnlyArray::end

Возвращает указатель на элемент, следующий за последним элементом в массиве.

### <a name="syntax"></a>Синтаксис

```cpp
T* end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор указателя на элемент, следующий за последним элементом в массиве.

### <a name="remarks"></a>Примечания

Этот итератор можно использовать с алгоритмами STL для выполнения операций, таких как `std::sort`, в элементах массива.

## <a name="fastpass"></a>  Свойство WriteOnlyArray::FastPass

Указывает, можно ли выполнить внутреннюю оптимизацию FastPass. Не предназначен для использования в пользовательском коде.

### <a name="syntax"></a>Синтаксис

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, является ли массив FastPass.

## <a name="get"></a>Метод WriteOnlyArray:: Get

Возвращает элемент по указанному индексу.

### <a name="syntax"></a>Синтаксис

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>Параметры

*индексарг*<br/>
Используемый индекс.

### <a name="return-value"></a>Возвращаемое значение

## <a name="length"></a>  Свойство WriteOnlyArray::Length

Возвращает число элементов в выделенном вызывающим объектом массиве.

### <a name="syntax"></a>Синтаксис

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

## <a name="set"></a>  Функция WriteOnlyArray::set

Задает указанное значение по заданному индексу массива.

### <a name="syntax"></a>Синтаксис

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>Параметры

*индексарг*<br/>
Задаваемый индекс элемента.

*валуеарг*<br/>
Задаваемое в `indexArg` значение.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, который только что был установлен.

### <a name="remarks"></a>Примечания

Дополнительные сведения о том, как интерпретировать значение HRESULT, см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes).

## <a name="see-also"></a>См. также

[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
