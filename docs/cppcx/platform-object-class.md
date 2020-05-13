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
ms.openlocfilehash: 8300ec484bdb58919ce8e450b706dd07c275ceee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363686"
---
# <a name="platformobject-class"></a>Класс Platform::Object

Обеспечивает общее поведение для классов рефов и реф-структур в приложениях Windows Runtime. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Object : Object
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Object::Object](#ctor)|Инициализирует новый экземпляр класса Object.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Object::Equals](#equals)|Определяет, равен ли указанный объект текущему объекту.|
|[Object::GetHashCode](#gethashcode)|Возвращает хэш-код для этого экземпляра.|
|[Object::ReferenceEquals](#referenceequals)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|
|[ToString](#tostring)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|
|[GetType](#gettype)|Получает объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий текущий экземпляр.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Object`

`Object`

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

## <a name="objectequals-method"></a><a name="equals"></a>Объект::Метод равных

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

**верно,** если объекты равны, в противном случае **ложные**.

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a>Объект::Метод GetHashCode

Возвращает значение идентификатора `IUnknown`* для этого экземпляра, если это COM-объект, или вычисляемое хэш-значение, если это не COM-объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Числовое значение, которое однозначно идентифицирует этот объект.

### <a name="remarks"></a>Remarks

Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Вы можете сравнить хэш-коды с помощью [Object::Equals](#equals). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей `IUnknown` в неуправляемом коде.

## <a name="objectgettype-method"></a><a name="gettype"></a>Объект::GetType Метод

Возвращает [платформу::Тип](../cppcx/platform-type-class.md) объекта, описывающий тип времени выполнения объекта.

### <a name="syntax"></a>Синтаксис

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

[Платформа:Тип](../cppcx/platform-type-class.md) объекта, описывающий тип времени выполнения объекта.

### <a name="remarks"></a>Remarks

Статический [тип::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) может быть использован для получения [значения значение enumeration платформы:TypeCode,](../cppcx/platform-typecode-enumeration.md) представляющее текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса реф, кроме [Платформы:String](../cppcx/platform-string-class.md) is Object (1).

[Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) class используется в AI Windows как независимый с языком способ передачи информации типа между компонентами Windows и приложениями. Платформа[T::Тип класса](../cppcx/platform-type-class.md) имеет операторов `Type` `TypeName`для преобразования между и .

Используйте оператора [typeid](../extensions/typeid-cpp-component-extensions.md) `Platform::Type` для возврата объекта для имени класса, например при навигации между страницами XAML:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a>Объект::Объект конструктор

Инициализирует новый экземпляр класса Object.

### <a name="syntax"></a>Синтаксис

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a>Объект::СправкаРавновайметод

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

**верно,** если два объекта одинаковы; в противном случае, **ложные**.

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a>Объект::Метод Тострнина (КЗ/КХ)

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

[Название платформы](platform-namespace-c-cx.md)<br/>
[Платформа:Тип класса](platform-type-class.md)<br/>
[Система типов](type-system-c-cx.md)
