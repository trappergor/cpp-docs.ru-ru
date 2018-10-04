---
title: Функции SafeInt | Документация Майкрософт
ms.custom: ''
ms.date: 09/28/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt functions
- SafeAdd
- SafeCast
- SafeDivide
- SafeEquals
- SafeGreaterThan
- SafeGreaterThanEquals
- SafeLessThan
- SafeLessThanEquals
- SafeModulus
- SafeMultiply
- SafeNotEquals
- SafeSubtract
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
- SafeAdd function
- SafeCast function
- SafeDivide function
- SafeEquals function
- SafeGreaterThan function
- SafeGreaterThanEquals function
- SafeLessThan function
- SafeLessThanEquals function
- SafeModulus function
- SafeMultiply function
- SafeNotEquals function
- SafeSubtract function
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 504cfe0780cfb0116f59ae67937ea5f0370dc8b2
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235572"
---
# <a name="safeint-functions"></a>Функции SafeInt

Библиотека SafeInt предоставляет ряд функций, которые можно использовать без создания экземпляра [класс SafeInt](../windows/safeint-class.md). Если вы хотите защитить от переполнения для целочисленного значения одной математической операции, можно использовать эти функции. Если вы хотите защиты множества математических операций, следует создать `SafeInt` объектов. Более эффективно, чтобы создать `SafeInt` объектов, чем для используются эти функции несколько раз.

Эти функции позволяют сравнить или выполняют математические операции над двумя различные типы параметров без преобразования их к одному типу.

Каждая из этих функций имеет два типа шаблонов: `T` и `U`. Каждый из этих типов может быть значение типа Boolean, символ или целочисленный тип. Целочисленные типы могут быть подписанные или не подписанные и любого размера, от 8-битных до 64 бит.

## <a name="in-this-section"></a>В этом разделе

Функция                      | Описание
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | Складывает два числа и обеспечивает защиту от переполнения.
[SafeCast](#safecast)         | Преобразует один тип параметра в другой тип.
[SafeDivide](#safedivide)     | Делит два числа и обеспечивает защиту от деления на ноль.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [ SafeNotEquals](#safenotequals) | Сравнивает два числа. Эти функции предназначены для сравнения двух различных типов чисел без изменения их типы.
[SafeModulus](#safemodulus)   | Выполняет операцию взятия по модулю на двух чисел.
[SafeMultiply](#safemultiply) | Перемножает два числа и обеспечивает защиту от переполнения.
[SafeSubtract](#safesubtract) | Вычитает два числа и обеспечивает защиту от переполнения.

## <a name="related-sections"></a>Связанные разделы

Раздел                                                  | Описание
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../windows/safeint-class.md)                   | класс `SafeInt`;
[SafeIntException](../windows/safeintexception-class.md) | Класс исключений, определенных в библиотеку SafeInt.

## <a name="safeadd"></a>SafeAdd

Складывает два числа способом, который обеспечивает защиту от переполнения.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для добавления. Это должен быть типа T.

*u*<br/>
[in] Второе число для добавления. Это должен быть типа u.

*результат*<br/>
[out] Параметр где `SafeAdd` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.

## <a name="safecast"></a>SafeCast

Приводит одним типом чисел в другой тип.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Параметры

*From*<br/>
[in] Преобразуемое число источника. Это должен быть типа `T`.

*Задача*<br/>
[out] Ссылка на новый числовой тип. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.

## <a name="safedivide"></a>SafeDivide

Делит два числа, способом, который обеспечивает защиту от деления на ноль.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Делитель. Это должен быть типа T.

*u*<br/>
[in] Делимое. Это должен быть типа u.

*результат*<br/>
[out] Параметр где `SafeDivide` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.

## <a name="safeequals"></a>SafeEquals

Сравнивает два числа, чтобы определить, равны ли они.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа T.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа u.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* и *u* равны; в противном случае — значение `false`.

### <a name="remarks"></a>Примечания

Метод улучшает `==` поскольку `SafeEquals` позволяет сравнить две различных типов чисел.

## <a name="safegreaterthan"></a>SafeGreaterThan

Сравнивает два числа.

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* больше, чем *u*; в противном случае `false`.

### <a name="remarks"></a>Примечания

`SafeGreaterThan` оператор сравнения регулярного расширяет, используя для сравнения двух различных типов чисел.

## <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

Сравнивает два числа.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* больше или равно *u*; в противном случае `false`.

### <a name="remarks"></a>Примечания

`SafeGreaterThanEquals` повышает оператор сравнения стандартные, так как он позволяет сравнить две различных типов чисел.

## <a name="safelessthan"></a>SafeLessThan

Определяет, является ли одно число меньше другого.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число. Это должен быть типа `T`.

*u*<br/>
[in] Второй номер. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* — меньше, чем *u*; в противном случае `false`.

### <a name="remarks"></a>Примечания

Этот метод расширяет возможности оператор сравнения стандартные, так как `SafeLessThan` позволяет сравнить две различные виды номер.

## <a name="safelessthanequals"></a>SafeLessThanEquals

Сравнивает два числа.

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* меньше или равно *u*; в противном случае `false`.

### <a name="remarks"></a>Примечания

`SafeLessThanEquals` оператор сравнения регулярного расширяет, используя для сравнения двух различных типов чисел.

## <a name="safemodulus"></a>SafeModulus

Выполняет операцию взятия по модулю на двух чисел.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Делитель. Это должен быть типа `T`.

*u*<br/>
[in] Делимое. Это должен быть типа `U`.

*результат*<br/>
[out] Параметр где `SafeModulus` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.

## <a name="safemultiply"></a>SafeMultiply

Перемножает два числа вместе способом, который обеспечивает защиту от переполнения.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для перемножения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для перемножения. Это должен быть типа `U`.

*результат*<br/>
[out] Параметр где `SafeMultiply` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.

## <a name="safenotequals"></a>SafeNotEquals

Определяет, если числа не равны.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа `U`.

### <a name="return-value"></a>Возвращаемое значение

`true` Если *t* и *u* не равны; в противном случае `false`.

### <a name="remarks"></a>Примечания

Метод улучшает `!=` поскольку `SafeNotEquals` позволяет сравнить две различных типов чисел.

## <a name="safesubtract"></a>SafeSubtract

Вычитает два числа, способом, который обеспечивает защиту от переполнения.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число операции вычитания. Это должен быть типа `T`.

*u*<br/>
[in] Для вычитания из *t*. Это должен быть типа `U`.

*результат*<br/>
[out] Параметр где `SafeSubtract` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

`true` При отсутствии ошибок; `false` при возникновении ошибки.
