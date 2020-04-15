---
title: Класс Platform::Collections::InputIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 92f9b15f474a5aa3d063f0ccfb663f56baf8de31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354566"
---
# <a name="platformcollectionsinputiterator-class"></a>Класс Platform::Collections::InputIterator

Обеспечивает стандартный входная библиотека шаблонов для коллекций, полученных из Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Параметры

*X*<br/>
Имя типа класса шаблона InputIterator.

### <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора ввода (:: std::input_iterator_tag).|
|`pointer`|Указатель на `const X`|
|`reference`|Ссылка на объект `const X`|
|`value_type`|Имя типа `X` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Вхотливник:Ввим-итератор](#ctor)|Инициализирует новый экземпляр класса InputIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Вхотливник::Оператор!](#operator-inequality)|Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.|
|[Оператор InputIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором InputIterator.|
|[Вхотливник:Оператор](#operator-increment)|Выполняет приращение текущего итератора InputIterator.|
|[Вхотливник:Оператор](#operator-equality)|Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.|
|[Вхотливщик:Оператор-> Оператор](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор InputIterator.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InputIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>Вхотливник:Конструктор ввода-вклада

Инициализирует новый экземпляр класса InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>Параметры

*Итератор*<br/>
Объект итератора.

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>Вхотливник:Оператор-оператор&gt;

Извлекает адрес элемента, указанного текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
pointer operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес элемента, указанного текущим итератором InputIterator.

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>Вхомитель:Оператор\*

Извлекает ссылку на элемент, указанный текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором InputIterator.

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>Вхотливник:Оператор

Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий входный оборотник равен *другим;* в противном случае, **ложные**.

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>Вхотливник:Оператор

Выполняет приращение текущего итератора InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет приращение текущего итератора InputIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора InputIterator, а затем выполняет приращение текущего итератора InputIterator.

### <a name="remarks"></a>Remarks

Первый синтаксис InputIterator выполняет приращение текущего итератора InputIterator перед его использованием.

Второй синтаксис выполняет приращение текущего итератора InputIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>Вхотливник::Оператор!

Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий вход не равен *другим;* в противном случае, **ложные**.

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)
