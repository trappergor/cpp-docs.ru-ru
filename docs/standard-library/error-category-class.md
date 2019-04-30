---
title: Класс error_category
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 55ff55b2026b741a2b7062d815fe43d6d19b078b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413714"
---
# <a name="errorcategory-class"></a>Класс error_category

Представляет абстрактный, общий базовый класс для объектов, который описывает категорию кодов ошибок.

## <a name="syntax"></a>Синтаксис

```cpp
class error_category;
```

## <a name="remarks"></a>Примечания

`error_category` реализуют два стандартных объекта: [generic_category](../standard-library/system-error-functions.md#generic_category) и [system_category](../standard-library/system-error-functions.md#system_category).

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[value_type](#value_type)|Тип, представляющий сохраненное значение кода ошибки.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[default_error_condition](#default_error_condition)|Сохраняет значение кода ошибки для объекта условия ошибки.|
|[equivalent](#equivalent)|Возвращает значение, указывающее, эквивалентны ли объекты ошибок.|
|[message](#message)|Возвращает имя указанного кода ошибки.|
|[name](#name)|Возвращает имя категории.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator==](#op_eq_eq)|Проверяет равенство между объектами `error_category`.|
|[operator!=](#op_neq)|Проверяет неравенство между объектами `error_category`.|
|[оператор<](#op_lt)|Проверяет, меньше ли объект [error_category](../standard-library/error-category-class.md) переданного для сравнения объекта `error_category`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<system_error>

**Пространство имен:** std

## <a name="default_error_condition"></a>  error_category::default_error_condition

Сохраняет значение кода ошибки для объекта условия ошибки.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Errval*|Значение кода ошибки для хранения в [error_condition](../standard-library/error-condition-class.md).|

### <a name="return-value"></a>Возвращаемое значение

Возвращает `error_condition(_Errval, *this)`.

### <a name="remarks"></a>Примечания

## <a name="equivalent"></a>  error_category::equivalent

Возвращает значение, указывающее, эквивалентны ли объекты ошибок.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Errval*|Значение кода ошибки для сравнения.|
|*_Cond*|Объект [error_condition](../standard-library/error-condition-class.md) для сравнения.|
|*_Code*|Объект [error_code](../standard-library/error-code-class.md) для сравнения.|

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если категории и значения равны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает значение `*this == _Cond.category() && _Cond.value() == _Errval`.

Вторая функция-член возвращает значение `*this == _Code.category() && _Code.value() == _Errval`.

## <a name="message"></a>  error_category::message

Возвращает имя указанного кода ошибки.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Val*|Значение кода ошибки для описания.|

### <a name="return-value"></a>Возвращаемое значение

Возвращает описательное имя кода ошибки *val* для категории.

### <a name="remarks"></a>Примечания

## <a name="name"></a>  error_category::name

Возвращает имя категории.

```cpp
virtual const char *name() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя категории как строку байтов, заканчивающуюся нулем.

### <a name="remarks"></a>Примечания

## <a name="op_eq_eq"></a>  error_category::operator==

Проверяет равенство между объектами `error_category`.

```cpp
bool operator==(const error_category& right) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*right*|Объект для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты равны, значение **false**, если объекты не равны.

### <a name="remarks"></a>Примечания

Этот оператор-член возвращает `this == &right`.

## <a name="op_neq"></a>  error_category::operator!=

Проверяет неравенство между объектами `error_category`.

```cpp
bool operator!=(const error_category& right) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*right*|Объект для проверки на неравенство.|

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если `error_category` объект не равным `error_category` переданный объект *правой*; в противном случае **false**.

### <a name="remarks"></a>Примечания

Оператор-член возвращает `(!*this == right)`.

## <a name="op_lt"></a>  error_category::operator&lt;

Проверяет, меньше ли объект [error_category](../standard-library/error-category-class.md) переданного для сравнения объекта `error_category`.

```cpp
bool operator<(const error_category& right) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*right*|Сравниваемый объект `error_category`.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true,** если объект `error_category` меньше, чем объект `error_category`, переданный для сравнения; в противном случае — значение **false**.

### <a name="remarks"></a>Примечания

Оператор-член возвращает `this < &right`.

## <a name="value_type"></a>  error_category::value_type

Тип, представляющий сохраняемое значение кода ошибки.

```cpp
typedef int value_type;
```

### <a name="remarks"></a>Примечания

Это определение типа является синонимом **int**.

## <a name="see-also"></a>См. также

[<system_error>](../standard-library/system-error.md)<br/>
