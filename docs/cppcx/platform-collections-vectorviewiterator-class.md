---
title: Класс Platform::Collections::VectorViewIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: 01ae4286e996db9819cb697360f6de9c344edd21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363696"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Класс Platform::Collections::VectorViewIterator

Обеспечивает итератор стандартной библиотеки шаблонов для объектов, полученных из интерфейса Windows Runtime.`IVectorView`

`ViewVectorIterator` — это итератор прокси-сервера, который хранит элементы типа `VectorProxy<T>`. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа класса шаблона VectorViewIterator.

### <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора произвольного доступа (::std::random_access_iterator_tag).|
|`pointer`|Указатель на внутренний тип, необходимый для реализации итератора VectorViewIterator.|
|`reference`|Ссылка на внутренний тип, необходимый для реализации итератора VectorViewIterator.|
|`value_type`|Имя типа `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[VectorViewIteror::VectorViewIter](#ctor)|Инициализирует новый экземпляр класса VectorViewIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[VectorViewIteror::Оператор-](#operator-minus)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|
|[VectorViewIteror::Оператор-- Оператор](#operator-decrement)|Выполняет уменьшение текущего итератора VectorViewIterator.|
|[Оператор VectorViewIter::Оператор!](#operator-inequality)|Указывает, отличен ли текущий объект VectorViewIterator от указанного объекта VectorViewIterator.|
|[Оператор VectorViewIter::Оператор](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором VectorViewIterator.|
|[VectorViewIteror:оператор\[\]](#operator-at)|Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.|
|[Оператор VectorViewIter::Оператор](#operator-plus)|Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.|
|[Оператор VectorViewIter::Оператор](#operator-increment)|Выполняет приращение текущего итератора VectorViewIterator.|
|[Оператор VectorViewIterator::operator+=](#operator-plus-equals)|Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.|
|[VectorViewIteror:Оператор< Оператор](#operator-less-than)|Указывает, действительно ли текущий объект VectorViewIterator меньше, чем указанный объект VectorViewIterator.|
|[VectorViewIteror::Оператор\<](#operator-less-than-or-equals)|Указывает, действительно ли текущий объект VectorViewIterator меньше указанного объекта VectorViewIterator или равен ему.|
|[Оператор VectorViewIter::Оператор-оператор](#operator-minus-assign)|Уменьшает текущий итератор VectorViewIterator на указанную величину смещения.|
|[Оператор VectorViewIter::Оператор](#operator-equality)|Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.|
|[VectorViewIteror:Оператор> Оператор](#operator-greater-than)|Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.|
|[VectorViewIteror:Оператор-> Оператор](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.|
|[VectorViewIteror::Оператор>- Оператор](#operator-greater-than-or-equals)|Указывает, действительно ли текущий объект VectorViewIterator больше указанного объекта VectorViewIterator или равен ему.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorViewIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectorviewiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>VectorViewIteror::Оператор-&gt;

Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, на который ссылается текущий итератор VectorViewIterator.

Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.

## <a name="vectorviewiteratoroperator---operator"></a><a name="operator-decrement"></a>VectorViewIteror::Оператор-- Оператор

Выполняет уменьшение текущего итератора VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет уменьшение текущего итератора VectorViewIterator.

### <a name="remarks"></a>Remarks

Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator перед его использованием.

Второй синтаксис выполняет уменьшение текущего итератора VectorViewIterator после его использования. Тип `int` во втором примере синтаксиса указывает операцию уменьшения после использования, он не является операндом целочисленного типа.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-dereference"></a>VectorViewIteror:Оператор\*

Извлекает ссылку на элемент, указанный текущим итератором VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором VectorIterator.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-equality"></a>Оператор VectorViewIter::Оператор

Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `VectorViewIterator` ток равен *другим;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>VectorViewIteror:Оператор&gt;

Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если текущий VectorViewIterator больше, чем *другие;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>VectorViewIteror::Оператор&gt;

Указывает, является `VectorViewIterator` ли ток больше `VectorViewIterator`или равен указанному.

### <a name="syntax"></a>Синтаксис

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `VectorViewIterator` ток больше или равен *другим;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-increment"></a>Оператор VectorViewIter::Оператор

Выполняет приращение текущего итератора VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет приращение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет приращение текущего итератора VectorViewIterator.

### <a name="remarks"></a>Remarks

Первый синтаксис выполняет приращение текущего итератора VectorViewIterator перед его использованием.

Второй синтаксис выполняет приращение текущего итератора VectorViewIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-inequality"></a>Оператор VectorViewIter::Оператор!

Указывает, отличен ли текущий объект VectorViewIterator от указанного объекта VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `VectorViewIterator` ток не равен *другим;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than"></a>VectorViewIteror:Оператор&lt;

Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект `VectorIterator`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `VectorIterator` ток меньше, чем *другие;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>VectorViewIteror::Оператор&lt;

Указывает, является `VectorIterator` ли ток меньше `VectorIterator`или равен указанному.

### <a name="syntax"></a>Синтаксис

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Другой объект `VectorIterator`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `VectorIterator` ток меньше или равен *другим;* в противном случае, **ложные**.

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus"></a>VectorViewIteror::Оператор-

Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.

### <a name="syntax"></a>Синтаксис

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Количество элементов.

*Других*<br/>
Другой объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

Синтаксис первого оператора возвращает объект VectorViewIterator, количество элементов которого меньше, чем у текущего объекта VectorViewIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorViewIterator и другим объектом VectorViewIterator, заданным параметром `other`.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus-equals"></a>Оператор VectorViewIter::Оператор

Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorViewIterator.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus"></a>Оператор VectorViewIter::Оператор

Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```

VectorViewIterator operator+(difference_type n) const;

template <typename T>
inline VectorViewIterator<T> operator+
   (ptrdiff_t n,
   const VectorViewIterator<T>& i);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Во втором синтаксисе — имя типа объекта VectorViewIterator.

*n*<br/>
Целочисленная величина смещения.

*Я*<br/>
Во втором синтаксисе — объект VectorViewIterator.

### <a name="return-value"></a>Возвращаемое значение

В первом синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от текущего объекта VectorViewIterator.

Во втором синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от начала `i` параметра.

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus-assign"></a>Оператор VectorViewIter::Оператор-оператор

Уменьшает текущий итератор VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorIterator.

## <a name="vectorviewiteratoroperator"></a><a name="operator-at"></a>VectorViewIteror:оператор\[\]

Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Элемент, удаленный от текущего итератора VectorViewIterator на `n`.

## <a name="vectorviewiteratorvectorviewiterator-constructor"></a><a name="ctor"></a>VectorViewIteror::VectorViewIteror Конструктор

Инициализирует новый экземпляр класса VectorViewIterator.

### <a name="syntax"></a>Синтаксис

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>Параметры

*V*<br/>
Объект IVectorView\<T>.

### <a name="remarks"></a>Remarks

Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса — это явный конструктор, который используется для построения VectorViewIteror с> объекта IVectorView\<T.

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)
