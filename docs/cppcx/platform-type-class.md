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
ms.openlocfilehash: 7463a2518e6ec5cc84f59db05cfaf60e43eb9fde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322094"
---
# <a name="platformtype-class"></a>Класс Platform::Type

Содержит сведения среды выполнения о типе — в частности, имя строки и код типа. Получено путем вызывать [объект::GetType](../cppcx/platform-object-class.md#gettype) на любом предмете или используя оператора typeid на [типидов](../extensions/typeid-cpp-component-extensions.md) или названии struct.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Remarks

Класс `Type` удобен в приложениях, где должна выполняться непосредственная обработка с использованием оператора `if` или `switch` , образующего ветви на основе типа объекта времени выполнения. Код типа, описывающий категорию типа, извлекается с помощью функции участника [Type::GetTypeCode.](#gettypecode)

## <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[Тип::GetTypeCode Метод](#gettypecode)|Возвращает значение [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) для объекта.|
|[Тип::Метод Торринга](#tostring)|Возвращает имя типа, указанное в его метаданных.|

## <a name="public-properties"></a>Открытые свойства

|||
|-|-|
|[Тип:FullName](#fullname)|Возвращает [Класс Platform::String](../cppcx/platform-string-class.md)^, который представляет полное имя типа и использует . (точка) в качестве сепаратора, а не :: `MyNamespace.MyClass`(двойная толстая кишка)- например, .|

## <a name="conversion-operators"></a>Операторы преобразования

|||
|-|-|
|[Оператор Типз](../cppcx/operator-type-hat.md)|Обеспечивает преобразование `Windows::UI::Xaml::Interop::TypeName` в `Platform::Type`.|
|[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)|Обеспечивает преобразование `Platform::Type` в `Windows::UI::Xaml::Interop::TypeName`.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="typefullname-property"></a><a name="fullname"></a> Свойство Type::FullName

Получает полностью квалифицированное название текущего `Namespace.Type`типа в форме.

### <a name="syntax"></a>Синтаксис

```cpp
String^ FullName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа данных.

### <a name="example"></a>Пример

```cpp
//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="typegettypecode-method"></a><a name="gettypecode"></a> Метод Type::GetTypeCode

Возвращает числовой тип категории встроенных типов.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления Platform::TypeCode.

### <a name="remarks"></a>Remarks

Эквивалентом метода-члена GetTypeCode() является свойство `typeid`.

## <a name="typetostring-method"></a><a name="tostring"></a>Тип::Метод Торринга

Извлекает имя типа.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа, указанное в метаданных.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
