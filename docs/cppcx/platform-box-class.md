---
title: Класс Platform::Box
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: 7484bcda3f05a8a9e56a33222d0630d4597e1219
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354762"
---
# <a name="platformbox-class"></a>Класс Platform::Box

Позволяет сохранять тип значения, такой как `Windows::Foundation::DateTime` , или скалярный тип, такой как `int` , в типе `Platform::Object` . Как правило, нет необходимости использовать `Box` явным образом, так как процесс упаковки выполняется неявно при приведении значения типа к `Object^`.

### <a name="syntax"></a>Синтаксис

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

### <a name="members"></a>Участники

|Участник|Описание|
|------------|-----------------|
|[Box](#ctor) | Создает объект `Box`, который может инкапсулировать значение указанного типа. |
|[оператор&lt;Box const T&gt;^](#box-const-t) | Позволяет осуществлять преобразования-упаковки класса значений `const``T` или `enum` класса `T` в `Box<T>`. |
|[оператор&lt;Box Const летучих T&gt;^](#box-const-volatile-t) | Позволяет осуществлять преобразования-упаковки из класса значений `const volatile``T` или `enum` типа `T` в `Box<T>`. |
|[оператор&lt;Box T&gt;^](#box-t) | Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`. |
|[оператор&lt;Box летучих T&gt;^](#box-volatile-t) | Позволяет осуществлять преобразования-упаковки из класса значений `volatile``T` или `enum` типа `T` в `Box<T>`. |
|[Коробка:оператор T](#t) | Позволяет осуществлять преобразования-упаковки класса значений `T` или `enum` класса `T` в `Box<T>`. |
|[Свойство значения](#value) | Возвращает значение, которое инкапсулируется в объекте `Box`. |

## <a name="boxbox-constructor"></a><a name="ctor"></a>Коробка:Box конструктор

Создает объект `Box`, который может инкапсулировать значение указанного типа.

### <a name="syntax"></a>Синтаксис

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>Параметры

*valueArg*<br/>
Тип упаковываемого значения — например, `int`, `bool`, `float64`, `DateTime`.

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a>Коробка:Оператор Box&lt;const&gt;T оператор

Позволяет осуществлять преобразования-упаковки класса значений `const``T` или `enum` класса `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой класс значений, структура значений или тип перечисления. Включает встроенные типы в [пространстве имен по умолчанию.](../cppcx/default-namespace.md)

### <a name="return-value"></a>Возвращаемое значение

Экземпляр, `Platform::Box<T>^` представляющий исходное значение, упакованное в классе рефов.

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a>Коробка:Оператор Box&lt;const&gt;летучих T оператор

Позволяет осуществлять преобразования-упаковки из класса значений `const volatile``T` или `enum` типа `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространстве имен по умолчанию.](../cppcx/default-namespace.md)

### <a name="return-value"></a>Возвращаемое значение

Экземпляр, `Platform::Box<T>^` представляющий исходное значение, упакованное в классе рефов.

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a>Коробка:Оператор Box&lt;&gt;T - Оператор

Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространстве имен по умолчанию.](../cppcx/default-namespace.md)

### <a name="return-value"></a>Возвращаемое значение

Экземпляр, `Platform::Box<T>^` представляющий исходное значение, упакованное в классе рефов.

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a>Коробка:оператор Коробка&lt;летучих T&gt;оператор

Позволяет осуществлять преобразования-упаковки из класса значений `volatile``T` или `enum` типа `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространстве имен по умолчанию.](../cppcx/default-namespace.md)

### <a name="return-value"></a>Возвращаемое значение

Экземпляр, `Platform::Box<T>^` представляющий исходное значение, упакованное в классе рефов.

## <a name="boxoperator-t-operator"></a><a name="t"></a>Коробка:Оператор T Оператор

Позволяет осуществлять преобразования-упаковки класса значений `T` или `enum` класса `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространстве имен по умолчанию.](../cppcx/default-namespace.md)

### <a name="return-value"></a>Возвращаемое значение

Экземпляр, `Platform::Box<T>^` представляющий исходное значение, упакованное в классе рефов.

## <a name="boxvalue-property"></a><a name="value"></a>Коробка:Значение свойства

Возвращает значение, которое инкапсулируется в объекте `Box`.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает упакованное значение с тем же типом, который у него был до упаковки.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)<br/>
[Упаковка-преобразование](../cppcx/boxing-c-cx.md)
