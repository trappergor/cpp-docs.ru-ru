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
ms.openlocfilehash: 77313f8c4dcc87fa9de852afe2d60e614f8fc3a3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865747"
---
# <a name="platformobject-class"></a>Класс Platform::Object

Предоставляет общее поведение для ссылочных классов и структур ссылок в среда выполнения Windows приложениях. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Object : Object
```

### <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Объект:: Object](#ctor)|Инициализирует новый экземпляр класса Object.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Object:: Equals](#equals)|Определяет, равен ли указанный объект текущему объекту.|
|[Object:: GetHashCode](#gethashcode)|Возвращает хэш-код для этого экземпляра.|
|[Объект:: ReferenceEquals](#referenceequals)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|
|[ToString](#tostring)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|
|[GetType](#gettype)|Получает объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий текущий экземпляр.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Object`

`Object`

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

## <a name="equals"></a>Метод Object:: Equals

Определяет, равен ли указанный объект текущему объекту.

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

**значение true** , если объекты равны; в противном случае — **значение false**.

## <a name="gethashcode"></a>Метод Object:: GetHashCode

Возвращает значение идентификатора `IUnknown`* для этого экземпляра, если это COM-объект, или вычисляемое хэш-значение, если это не COM-объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Числовое значение, которое однозначно идентифицирует этот объект.

### <a name="remarks"></a>Remarks

Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Сравнить хэш-коды можно с помощью [Object:: Equals](#equals). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей `IUnknown` в неуправляемом коде.

## <a name="gettype"></a>Метод Object:: GetType

Возвращает объект [Platform:: Type](../cppcx/platform-type-class.md) , описывающий тип объекта во время выполнения.

### <a name="syntax"></a>Синтаксис

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Объект [Platform:: Type](../cppcx/platform-type-class.md) , описывающий тип объекта во время выполнения.

### <a name="remarks"></a>Remarks

Статический [Тип:: GetTypeCode](../cppcx/platform-type-class.md#gettypecode) можно использовать для получения значения [перечисления Platform:: TypeCode](../cppcx/platform-typecode-enumeration.md) , представляющего текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса ссылки помимо [Platform:: String](../cppcx/platform-string-class.md) — Object (1).

Класс [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) используется в интерфейсах API Windows как независимый от языка способ передачи сведений о типах между компонентами Windows и приложениями. Класс T[Platform:: Type](../cppcx/platform-type-class.md) имеет операторы для преобразования между `Type` и `TypeName`.

Используйте оператор [typeid](../extensions/typeid-cpp-component-extensions.md) , чтобы получить объект `Platform::Type` для имени класса, например при переходе между страницами XAML:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="ctor"></a>Конструктор объекта:: Object

Инициализирует новый экземпляр класса Object.

### <a name="syntax"></a>Синтаксис

```cpp
public:Object();
```

## <a name="referenceequals"></a>Метод Object:: ReferenceEquals

Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.

### <a name="syntax"></a>Синтаксис

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>Параметры

*obj1*<br/>
Первый объект для сравнения.

*obj2*<br/>
Второй объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если два объекта одинаковы; в противном случае — **значение false**.

## <a name="tostring"></a>Метод Object:: ToString (C++/CX)

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

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Класс Platform::Type](platform-type-class.md)<br/>
[Система типов](type-system-c-cx.md)
