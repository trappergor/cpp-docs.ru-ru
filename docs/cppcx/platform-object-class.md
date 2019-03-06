---
title: Класс Platform::Object
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
ms.openlocfilehash: 8267d42e67ddf703b4a3a681509b92978e7de8bb
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422793"
---
# <a name="platformobject-class"></a>Класс Platform::Object

Определяет общее поведение для классов ссылок и структур ссылок в приложениях среды выполнения Windows. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Object : Object
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Object::Object](#ctor)|Инициализирует новый экземпляр класса Object.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Object::Equals](#equals)|Определяет, равен ли заданный объект текущему объекту.|
|[Object::GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|
|[Object::ReferenceEquals](#referenceequals)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|
|[ToString](#tostring)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|
|[GetType](#gettype)|Получает объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий текущий экземпляр.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Object`

`Object`

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

## <a name="equals"></a> Метод Object::Equals

Определяет, равен ли заданный объект текущему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты равны; в противном случае **false**.

## <a name="gethashcode"></a>  Метод Object::GetHashCode

Возвращает значение идентификатора `IUnknown`* для этого экземпляра, если это COM-объект, или вычисляемое хэш-значение, если это не COM-объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Числовое значение, которое однозначно идентифицирует этот объект.

### <a name="remarks"></a>Примечания

Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Можно сравнить хэш-кодов с помощью [Object::Equals](#equals). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей `IUnknown` в неуправляемом коде.

## <a name="gettype"></a>  Метод Object::GetType

Возвращает [Platform::Type](../cppcx/platform-type-class.md) , описывающий тип среды выполнения объекта.

### <a name="syntax"></a>Синтаксис

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий тип среды выполнения объекта.

### <a name="remarks"></a>Примечания

Статический [Type::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) может использоваться для получения [перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) значение, которое представляет текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса ссылок помимо [Platform::String](../cppcx/platform-string-class.md) — объект (1).

[Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) класс используется в API Windows как независимый от языка способ передачи сведений о типе между компонентами Windows и приложениями. T[класс Platform::Type](../cppcx/platform-type-class.md) имеет операторы для преобразования между `Type` и `TypeName`.

Используйте [typeid](../windows/typeid-cpp-component-extensions.md) оператора для выборки `Platform::Type` для имени класса, например, при переходе между страницами XAML:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="ctor"></a>  Конструктор Object::Object

Инициализирует новый экземпляр класса Object.

### <a name="syntax"></a>Синтаксис

```cpp
public:Object();
```

## <a name="referenceequals"></a>  Метод Object::ReferenceEquals

Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.

### <a name="syntax"></a>Синтаксис

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>Параметры

*объекты Obj1*<br/>
Первый из сравниваемых объектов.

*obj2*<br/>
Второй из сравниваемых объектов.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если два объекта одинаковы; в противном случае **false**.

## <a name="tostring"></a>  Метод Object::ToString (C + +/ CX)

Возвращает строку, представляющую текущий объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, представляющая текущий объект. Этот метод можно переопределить, чтобы ссылочный класс или структура содержали пользовательскую строку сообщения:

```cpp
public ref class Tree sealed
{
public:
    Tree(){}
    virtual Platform::String^ ToString() override
    {
      return "I’m a Tree";
    };
};
```

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)<br/>
[Класс Platform::Type](platform-type-class.md)<br/>
[Система типов](type-system-c-cx.md)
