---
title: Функции SafeInt
ms.date: 10/22/2018
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
ms.openlocfilehash: e31cf35c903a0e7572ce7d47ada21c4603119cb2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515579"
---
# <a name="safeint-functions"></a>Функции SafeInt

Библиотека SafeInt предоставляет ряд функций, которые можно использовать без создания экземпляра [класса SafeInt](../safeint/safeint-class.md). Если вы хотите защитить отдельную математическую операцию от переполнения целочисленными значениями, вы можете использовать эти функции. Для защиты множества математических операций создайте объекты `SafeInt`. Более эффективно создать объекты `SafeInt`, чем использовать эти функции несколько раз.

Эти функции позволяют сравнить или выполнить математические операции над двумя различными типами параметров без преобразования их к одному типу.

У каждой из этих функций есть два типа шаблонов: `T` и `U`. Каждый из этих типов может быть логическим, символьным или целочисленным типом. Целочисленные типы могут быть со знаком или без него, а также любого размера — от 8 до 64 бит.

> [!NOTE]
> Последняя версия этой библиотеки размещена здесь: [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="in-this-section"></a>В этом разделе

Функция                      | Описание
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | Складывает два числа и обеспечивает защиту от переполнения.
[SafeCast](#safecast)         | Преобразует один тип параметра в другой.
[SafeDivide](#safedivide)     | Делит два числа и обеспечивает защиту от деления на ноль.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [SafeNotEquals](#safenotequals) | Сравнивает два числа. Эти функции предназначены для сравнения двух различных типов чисел без изменения их типов.
[SafeModulus](#safemodulus)   | Выполняет операцию получения модуля для двух чисел.
[SafeMultiply](#safemultiply) | Перемножает одно число на другое и обеспечивает защиту от переполнения.
[SafeSubtract](#safesubtract) | Вычитает одно число из другого и обеспечивает защиту от переполнения.

## <a name="related-sections"></a>Связанные разделы

Раздел                                                  | Описание
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../safeint/safeint-class.md)                   | класс `SafeInt`;
[SafeIntException](../safeint/safeintexception-class.md) | Класс исключений, относящийся к библиотеке SafeInt.

## <a name="safeadd"></a>SafeAdd

Складывает два числа таким образом, чтобы обеспечить защиту от переполнения.

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
[in] Первое число для сложения. Это должен быть тип T.

*u*<br/>
[in] Второе число для сложения. Это должен быть тип U.

*result*<br/>
[out] Параметр, в котором `SafeAdd` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

Значение **true** при отсутствии ошибки; значение **false** при ее возникновении.

## <a name="safecast"></a>SafeCast

Преобразует один тип числа в другой.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Параметры

*From*<br/>
[in] Исходное преобразуемое число. Это должен быть тип `T`.

*Задача*<br/>
[out] Ссылка на новый числовой тип. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true** при отсутствии ошибки; значение **false** при ее возникновении.

## <a name="safedivide"></a>SafeDivide

Делит два числа таким образом, чтобы обеспечить защиту от деления на ноль.

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
[in] Делитель. Это должен быть тип T.

*u*<br/>
[in] Делимое. Это должен быть тип U.

*result*<br/>
[out] Параметр, в котором `SafeDivide` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

Значение **true** при отсутствии ошибки; значение **false** при ее возникновении.

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
[in] Первое число для сравнения. Это должен быть тип T.

*u*<br/>
[in] Второе число для сравнения. Это должен быть тип U.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* и *u* равны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Этот метод расширяет возможности `==`, потому что `SafeEquals` позволяет сравнивать два различных типа чисел.

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
[in] Первое число для сравнения. Это должен быть тип `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* больше *u*; в противном случае — **false**.

### <a name="remarks"></a>Примечания

`SafeGreaterThan` расширяет возможности обычного оператора сравнения, позволяя сравнивать два различных типа чисел.

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
[in] Первое число для сравнения. Это должен быть тип `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* больше или равно *u*; в противном случае — **false**.

### <a name="remarks"></a>Примечания

`SafeGreaterThanEquals` расширяет возможности стандартного оператора сравнения, потому что позволяет сравнивать два различных типа чисел.

## <a name="safelessthan"></a>SafeLessThan

Определяет, меньше ли одно число другого.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число. Это должен быть тип `T`.

*u*<br/>
[in] Второе число. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* меньше *u*; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Этот метод расширяет возможности стандартного оператора сравнения, потому что `SafeLessThan` позволяет сравнивать два различных типа чисел.

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
[in] Первое число для сравнения. Это должен быть тип `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* меньше *u*; в противном случае — **false**.

### <a name="remarks"></a>Примечания

`SafeLessThanEquals` расширяет возможности обычного оператора сравнения, позволяя сравнивать два различных типа чисел.

## <a name="safemodulus"></a>SafeModulus

Выполняет операцию получения модуля для двух чисел.

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
[in] Делитель. Это должен быть тип `T`.

*u*<br/>
[in] Делимое. Это должен быть тип `U`.

*result*<br/>
[out] Параметр, в котором `SafeModulus` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

Значение **true** при отсутствии ошибки; значение **false** при ее возникновении.

## <a name="safemultiply"></a>SafeMultiply

Перемножает одно число на другое таким образом, чтобы обеспечить защиту от переполнения.

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
[in] Первое число для умножения. Это должен быть тип `T`.

*u*<br/>
[in] Второе число для умножения. Это должен быть тип `U`.

*result*<br/>
[out] Параметр, в котором `SafeMultiply` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

Значение `true` при отсутствии ошибки; значение `false` при ее возникновении.

## <a name="safenotequals"></a>SafeNotEquals

Определяет, отличаются ли два числа.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть тип `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть тип `U`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если *t* и *u* не равны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Этот метод расширяет возможности `!=`, потому что `SafeNotEquals` позволяет сравнивать два различных типа чисел.

## <a name="safesubtract"></a>SafeSubtract

Вычитает одно число из другого таким образом, чтобы обеспечить защиту от переполнения.

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
[in] Первое число в вычитании. Это должен быть тип `T`.

*u*<br/>
[in] Число, вычитаемое из *t*. Это должен быть тип `U`.

*result*<br/>
[out] Параметр, в котором `SafeSubtract` сохраняет результат.

### <a name="return-value"></a>Возвращаемое значение

Значение **true** при отсутствии ошибки; значение **false** при ее возникновении.
