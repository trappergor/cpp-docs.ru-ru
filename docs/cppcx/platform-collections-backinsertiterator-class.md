---
title: Класс Platform::Collections::BackInsertIterator
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: 33397ed7061f14d9aeb9c8b5c3d561865ad91cad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638091"
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

### <a name="remarks"></a>Примечания

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
|[Оператор BackInsertIterator::operator++](#operator-increment)|Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.|
|[Оператор BackInsertIterator::operator=](#operator-assign)|Добавляет указанный объект в конец текущей упорядоченной коллекции.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BackInsertIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

---
## <a name="ctor"></a>  Конструктор BackInsertIterator::BackInsertIterator

Инициализирует новый экземпляр класса `BackInsertIterator`.

## <a name="syntax"></a>Синтаксис

```

explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Параметры

*v*<br/>
IVector\<T > объекта.

### <a name="remarks"></a>Примечания

`BackInsertIterator` вставляет элементы после последнего элемента объекта, указанного параметром `v`.

## <a name="operator-assign"></a>  BackInsertIterator::operator =-оператор

Добавляет указанный объект в конец текущей упорядоченной коллекции.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Параметры

*t*<br/>
Объект, добавляемый к текущей коллекции.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

## <a name="operator-dereference"></a>  Оператор BackInsertIterator::operator *

Получает ссылку на текущий объект BackInsertIterator.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Примечания

Этот оператор возвращает ссылку на текущий BackInsertIterator, а не на любой элемент в текущей коллекции.

## <a name="operator-increment"></a>  Оператор BackInsertIterator::operator ++

Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.

## <a name="syntax"></a>Синтаксис

```

BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Примечания

Выражение в первом примере синтаксиса увеличивает значение текущего элемента BackInsertIterator перед его использованием, а во втором — после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.

Впрочем, этот оператор не изменяет объект BackInsertIterator. Вместо этого он возвращает ссылку на текущий итератор, остающийся неизменным. Это аналогично [оператор *](#dereference-operator).

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)