---
title: Класс Platform::Collections::InputIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 49b131b01fe3d9cad5f8366fd4cc0c110b5d060c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161801"
---
# <a name="platformcollectionsinputiterator-class"></a>Класс Platform::Collections::InputIterator

Предоставляет InputIterator библиотеки стандартных шаблонов для коллекций, производным от среды выполнения Windows.

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

|name|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора ввода (:: std::input_iterator_tag).|
|`pointer`|Указатель на `const X`|
|`reference`|Ссылка на `const X`|
|`value_type`|Имя типа `X` .|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[InputIterator::InputIterator](#ctor)|Инициализирует новый экземпляр класса InputIterator.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Оператор InputIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.|
|[Оператор InputIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором InputIterator.|
|[Оператор InputIterator::operator++](#operator-increment)|Выполняет приращение текущего итератора InputIterator.|
|[Оператор InputIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.|
|[Оператор InputIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор InputIterator.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InputIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="ctor"></a>  Конструктор InputIterator::InputIterator

Инициализирует новый экземпляр класса InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>Параметры

*iterator*<br/>
Объект итератора.

## <a name="operator-arrow"></a>  InputIterator::operator-&gt; Operator

Извлекает адрес элемента, указанного текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
pointer operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес элемента, указанного текущим итератором InputIterator.

## <a name="operator-dereference"></a>  InputIterator::operator\* оператор

Извлекает ссылку на элемент, указанный текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором InputIterator.

## <a name="operator-equality"></a>  InputIterator::operator ==-оператор

Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*other*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если текущий объект InputIterator равен *других*; в противном случае **false**.

## <a name="operator-increment"></a>  Оператор InputIterator::operator ++

Выполняет приращение текущего итератора InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет приращение текущего итератора InputIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора InputIterator, а затем выполняет приращение текущего итератора InputIterator.

### <a name="remarks"></a>Примечания

Первый синтаксис InputIterator выполняет приращение текущего итератора InputIterator перед его использованием.

Второй синтаксис выполняет приращение текущего итератора InputIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

## <a name="operator-inequality"></a>  InputIterator::operator! =-оператор

Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*other*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если текущий объект InputIterator не равен *других*; в противном случае **false**.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)
