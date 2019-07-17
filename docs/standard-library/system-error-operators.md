---
title: Операторы &lt;system_error&gt;
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 5cf6a455beb5654ef65f7411db4783a32c71d625
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246210"
---
# <a name="ltsystemerrorgt-operators"></a>Операторы &lt;system_error&gt;

## <a name="op_eq_eq"></a> оператор ==

Проверяет равенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Объект для проверки на равенство.

*Правильно*\
Объект для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты равны, значение **false**, если объекты не равны.

### <a name="remarks"></a>Примечания

Функция возвращает `left.category() == right.category() && left.value() == right.value()`.

## <a name="op_neq"></a> оператор! =

Проверяет неравенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Объект для проверки на неравенство.

*Правильно*\
Объект для проверки на неравенство.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если переданный объект *левой* неравенство объекта, переданного в *правой*; в противном случае **false**.

### <a name="remarks"></a>Примечания

Функция возвращает `!(left == right)`.

## <a name="op_lt"></a> Оператор&lt;

Проверяет, меньше ли какой-либо объект переданного для сравнения объекта.

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Сравниваемый объект.

*Правильно*\
Сравниваемый объект.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если переданный объект *левой* меньше, чем объект, передаваемый в *правой*; В противном случае **false**.

### <a name="remarks"></a>Примечания

Эта функция проверяет порядок ошибок.

## <a name="op_ostream"></a> Оператор&lt;&lt;

```cpp
template <class charT, class traits> 
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```
