---
title: Класс Platform::Type
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: 456dbff652c8f1b800308ff757930b425616a83f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781748"
---
# <a name="platformtype-class"></a>Класс Platform::Type

Содержит сведения среды выполнения о типе — в частности, имя строки и код типа. Получен путем вызова [Object::GetType](../cppcx/platform-object-class.md#gettype) любого объекта, или с помощью [typeid](../extensions/typeid-cpp-component-extensions.md) оператор на имени класса или структуры.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Примечания

Класс `Type` удобен в приложениях, где должна выполняться непосредственная обработка с использованием оператора `if` или `switch` , образующего ветви на основе типа объекта времени выполнения. Код типа, описывающий категорию типа извлекаются с помощью [Type::GetTypeCode](#gettypecode) функция-член.

## <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[Метод Type::GetTypeCode](#gettypecode)|Возвращает значение [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) для объекта.|
|[Метод Type::ToString](#tostring)|Возвращает имя типа, указанного в своих метаданных.|

## <a name="public-properties"></a>Открытые свойства

|||
|-|-|
|[Type::FullName](#fullname)|Возвращает [Класс Platform::String](../cppcx/platform-string-class.md)^, который представляет полное имя типа и использует . (точка) в качестве разделителя, не:: (двойное двоеточие) — например, `MyNamespace.MyClass`.|

## <a name="conversion-operators"></a>Операторы преобразования

|||
|-|-|
|[оператор Type^](../cppcx/operator-type-hat.md)|Обеспечивает преобразование `Windows::UI::Xaml::Interop::TypeName` в `Platform::Type`.|
|[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)|Обеспечивает преобразование `Platform::Type` в `Windows::UI::Xaml::Interop::TypeName`.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="fullname"></a> Свойство Type::FullName

Извлекает полное имя текущего типа в виде `Namespace.Type`.

### <a name="syntax"></a>Синтаксис

```cpp
String^ FullName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа.
### <a name="example"></a>Пример

```

//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="gettypecode"></a> Метод Type::GetTypeCode

Возвращает числовой тип категории встроенных типов.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления Platform::TypeCode.

### <a name="remarks"></a>Примечания

Эквивалентом метода-члена GetTypeCode() является свойство `typeid`.

## <a name="tostring"></a> Метод Type::ToString

Извлекает имя типа.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа, указанного в своих метаданных.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
