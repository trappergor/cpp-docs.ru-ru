---
title: Класс Platform::Collections::BackInsertIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: fcb680c8f43a50801d081762bb5b546cb110c52d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354770"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Класс Platform::Collections::BackInsertIterator

Представляет итератор, который вставляет, а не перезаписывает элементы в конец упорядоченной коллекции.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип элемента в текущей коллекции.

### <a name="remarks"></a>Remarks

Класс BackInsertIterator реализует правила, необходимые для [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[BackInsertIterator::BackInsertIterator](#ctor)|Инициализирует новый экземпляр класса BackInsertIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор BackInsertIterator::operator*](#operator-dereference)|Получает ссылку на текущий объект BackInsertIterator.|
|[BackInsertIterator::Оператор](#operator-increment)|Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.|
|[BackInsertIterator::Оператор](#operator-assign)|Добавляет указанный объект в конец текущей упорядоченной коллекции.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BackInsertIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="backinsertiteratorbackinsertiterator-constructor"></a><a name="ctor"></a>BackInsertIterator::BackInsertIterator Конструктор

Инициализирует новый экземпляр класса `BackInsertIterator`.

## <a name="syntax"></a>Синтаксис

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Параметры

*V*<br/>
Объект IVector\<T>.

### <a name="remarks"></a>Remarks

`BackInsertIterator` вставляет элементы после последнего элемента объекта, указанного параметром `v`.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-assign"></a>BackInsertIterator::Оператор

Добавляет указанный объект в конец текущей упорядоченной коллекции.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Объект, добавляемый к текущей коллекции.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-dereference"></a>BackInsertIterator::Оператор

Получает ссылку на текущий объект BackInsertIterator.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Remarks

Этот оператор возвращает ссылку на текущий BackInsertIterator, а не на любой элемент в текущей коллекции.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-increment"></a>BackInsertIterator::Оператор

Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Remarks

Выражение в первом примере синтаксиса увеличивает значение текущего элемента BackInsertIterator перед его использованием, а во втором — после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

Впрочем, этот оператор не изменяет объект BackInsertIterator. Вместо этого он возвращает ссылку на текущий итератор, остающийся неизменным. Это то же самое поведение, что и [оператор.](#operator-dereference)

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)
