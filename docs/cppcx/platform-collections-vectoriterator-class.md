---
title: Класс Platform::Collections::VectorIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: e649027c2ba3f637c42765af691f4d321913fb28
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354369"
---
# <a name="platformcollectionsvectoriterator-class"></a>Класс Platform::Collections::VectorIterator

Обеспечивает стандартный итератор библиотеки шаблонов для объектов, полученных из интерфейса Windows Runtime IVector.

VectorIterator — это прокси-итератор, который\<хранит элементы типа VectorProxy T>. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа класса шаблона VectorIterator.

### <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора произвольного доступа (::std::random_access_iterator_tag).|
|`pointer`|Указатель на внутренний тип, Платформа::Коллекции:::D:Прокси\<T>, что требуется для реализации VectorIterator.|
|`reference`|Ссылка на внутренний тип, Платформа::Коллекции::D:\<VectorProxy T>, что требуется для реализации VectorIterator.|
|`value_type`|Имя типа `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ВекторИтератор:ВекторИтератор](#ctor)|Инициализирует новый экземпляр класса VectorIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ВекторИтератор::Оператор-оператор](#operator-minus)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|
|[Оператор VectorIterator::operator--](#operator-decrement)|Выполняет уменьшение текущего итератора VectorIterator.|
|[Оператор VectorIteror::Оператор!](#operator-inequality)|Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.|
|[ВекторИтератор:Оператор](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором VectorIterator.|
|[ВекторИтератор::оператор\[\]](#operator-at)|Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.|
|[ВекторИтератор::Оператор](#operator-plus)|Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.|
|[Оператор VectorIterator::Оператор](#operator-increment)|Выполняет увеличение текущего итератора VectorIterator.|
|[Оператор VectorIterator::Оператор](#operator-plus-assign)|Увеличивает текущий итератор VectorIterator на указанную величину смещения.|
|[VectorIterator:Оператор< Оператор](#operator-less-than)|Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.|
|[VectorIterator::Оператор\<](#operator-less-than-or-equals)|Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.|
|[Вектор-Итератор::Оператор-оператор](#operator-minus-equals)|Уменьшает текущий итератор VectorIterator на указанную величину смещения.|
|[ВекторИтератор::Оператор оператор](#operator-equality)|Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.|
|[VectorIterator:Оператор> Оператор](#operator-greater-than)|Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.|
|[Векторитератор:Оператор-> Оператор](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.|
|[VectorIterator::Оператор>- Оператор](#operator-greater-than-or-equals)|Указывает, действительно ли текущий объект VectorIterator больше указанного объекта VectorIterator или равен ему.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a>ВекторИтератор::Оператор-оператор&gt;

Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.

### <a name="syntax"></a>Синтаксис

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, на который ссылается текущий итератор VectorIterator.

Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a>ВекторИтератор::Оператор-- Оператор

Выполняет уменьшение текущего итератора VectorIterator.

### <a name="syntax"></a>Синтаксис

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет уменьшение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет уменьшение текущего итератора VectorIterator.

### <a name="remarks"></a>Remarks

Первый синтаксис выполняет уменьшение текущего итератора VectorIterator перед его использованием.

Второй синтаксис выполняет уменьшение текущего итератора VectorIterator после его использования. Тип `int` во втором примере синтаксиса указывает операцию уменьшения после использования, он не является операндом целочисленного типа.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a>ВекторИтератор:Оператор\*

Извлекает адрес элемента, указанного текущим итератором VectorIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a>ВекторИтератор::Оператор оператор

Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator равен *другим;* в противном случае, **ложные**.

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>ВекторИтератор:Оператор&gt;

Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator больше, чем *другие;* в противном случае, **ложные**.

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>VectorIterator::Оператор&gt;

Указывает, является ли текущий объект VectorIterator большим или равным указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator больше или равен *другим;* в противном случае, **ложные**.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a>Оператор VectorIterator::Оператор

Выполняет увеличение текущего итератора VectorIterator.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет увеличение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет увеличение текущего итератора VectorIterator.

### <a name="remarks"></a>Remarks

Первый синтаксис выполняет увеличение текущего итератора VectorIterator перед его использованием.

Второй синтаксис выполняет увеличение текущего итератора VectorIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a>Оператор VectorIteror::Оператор!

Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator не равен *другим;* в противном случае, **ложные**.

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a>ВекторИтератор:Оператор&lt;

Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator меньше, чем *другие;* в противном случае, **ложные**.

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>VectorIterator::Оператор&lt;

Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorIterator меньше, чем или равна *другим;* в противном случае, **ложные**.

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a>ВекторИтератор::Оператор-оператор

Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.

### <a name="syntax"></a>Синтаксис

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Количество элементов.

*Других*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

Синтаксис первого оператора возвращает объект VectorIterator, количество элементов которого меньше, чем у текущего объекта VectorIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorIterator и другим объектом VectorIterator, заданным параметром `other`.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a>Оператор VectorIterator::Оператор

Увеличивает текущий итератор VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a>ВекторИтератор::Оператор

Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.

### <a name="syntax"></a>Синтаксис

```

VectorIterator operator+(difference_type n);

template <typename T>
inline VectorIterator<T> operator+(
  ptrdiff_t n,
  const VectorIterator<T>& i);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Во втором синтаксисе — имя типа объекта VectorIterator.

*n*<br/>
Целочисленная величина смещения.

*Я*<br/>
Во втором синтаксисе — объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

В первом синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от текущего объекта VectorIterator.

Во втором синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от начала параметра `i`.

### <a name="remarks"></a>Remarks

Первый пример синтаксиса

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a>Вектор-Итератор::Оператор-оператор

Уменьшает текущий итератор VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorIterator.

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a>ВекторИтератор::оператор\[\]

Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Элемент, отстоящий от текущего итератора VectorIterator на `n` элементов.

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a>Вектор:Вектор конструктор

Инициализирует новый экземпляр класса VectorIterator.

### <a name="syntax"></a>Синтаксис

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>Параметры

*V*<br/>
Объект IVector\<T>.

### <a name="remarks"></a>Remarks

Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса — это явный конструктор, который используется для\<построения VectorIterator с> объекта IVector T.

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)
