---
title: Операторы &lt;system_error&gt;
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: d5c8f49c4a38862d62b7fe8212d98c87949fecfc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412128"
---
# <a name="ltsystemerrorgt-operators"></a>Операторы &lt;system_error&gt;

||||
|-|-|-|
|[operator!=](#op_neq)|[оператор&lt;](#op_lt)|[оператор==](#op_eq_eq)|

## <a name="op_eq_eq"></a> operator==

Проверяет равенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*left*|Объект для проверки на равенство.|
|*right*|Объект для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты равны, значение **false**, если объекты не равны.

### <a name="remarks"></a>Примечания

Функция возвращает `left.category() == right.category() && left.value() == right.value()`.

## <a name="op_neq"></a> operator!=

Проверяет неравенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*left*|Объект для проверки на неравенство.|
|*right*|Объект для проверки на неравенство.|

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если переданный объект *левой* неравенство объекта, переданного в *правой*; в противном случае **false**.

### <a name="remarks"></a>Примечания

Функция возвращает `!(left == right)`.

## <a name="op_lt"></a> operator&lt;

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

|Параметр|Описание|
|---------------|-----------------|
|*left*|Сравниваемый объект.|
|*right*|Сравниваемый объект.|

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если переданный объект *левой* меньше, чем объект, передаваемый в *правой*; В противном случае **false**.

### <a name="remarks"></a>Примечания

Эта функция проверяет порядок ошибок.

## <a name="see-also"></a>См. также

[<system_error>](../standard-library/system-error.md)<br/>
