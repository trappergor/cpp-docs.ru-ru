---
title: Класс concurrent_queue | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f8f864dcbf412b9dea0d96f6a0ba046792d7827
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162975"
---
# <a name="concurrentqueue-class"></a>Класс concurrent_queue

Класс `concurrent_queue` представляет собой класс контейнера последовательности, обеспечивающий доступ к элементам в порядке поступления. Он позволяет использовать ограниченный набор параллельно-безопасных операций, таких как `push` и `try_pop`.

## <a name="syntax"></a>Синтаксис

```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранимых в очереди.

*_Ax*<br/>
Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для этой параллельной очереди. Этот аргумент является необязательным, и значением по умолчанию является `allocator<T>`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди.|
|`const_iterator`|Тип, представляющий не поточно ориентированной `const` итератор по элементам в параллельной очереди.|
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент, хранящийся в параллельной очереди для чтения и выполнения `const` операций.|
|`difference_type`|Тип, предоставляющий расстояние со знаком между двумя элементами в параллельной очереди.|
|`iterator`|Тип, который представляет собой итератор не поточно ориентированные элементы в параллельной очереди.|
|`reference`|Тип, предоставляющий ссылку на элемент, хранящийся в параллельной очереди.|
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди.|
|`value_type`|Тип, представляющий тип данных, хранящихся в параллельной очереди.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[concurrent_queue](#ctor)|Перегружен. Создает параллельную очередь.|
|[~ concurrent_queue деструктор](#dtor)|Уничтожает параллельной очереди.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[clear](#clear)|Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|
|[empty](#empty)|Проверяет ли параллельная очередь пуста в данный момент этот метод вызывается. Этот метод безопасен в режиме параллелизма.|
|[get_allocator](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельной очереди. Этот метод безопасен в режиме параллелизма.|
|[push](#push)|Перегружен. Ставит в очередь элемент в конец параллельной очереди. Этот метод безопасен в режиме параллелизма.|
|[try_pop](#try_pop)|Удаляет элемент из очереди, если таковой доступен. Этот метод безопасен в режиме параллелизма.|
|[unsafe_begin](#unsafe_begin)|Перегружен. Возвращает итератор, указывающий тип `iterator` или `const_iterator` в начале параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|
|[unsafe_end](#unsafe_end)|Перегружен. Возвращает итератор, указывающий тип `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|
|[unsafe_size](#unsafe_size)|Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`concurrent_queue`

## <a name="requirements"></a>Требования

**Заголовок:** concurrent_queue.h

**Пространство имен:** concurrency

##  <a name="clear"></a> Очистить

Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.

```
void clear();
```

##  <a name="ctor"></a> concurrent_queue

Создает параллельную очередь.

```
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Параметры

*_InputIterator*<br/>
Тип входной итератор, который задает диапазон значений.

*_Al*<br/>
Класс распределителя для использования с данным объектом.

*_OtherQ*<br/>
Исходный объект `concurrent_queue` для копирования или перемещения элементов.

*Н_ачать*<br/>
Положение первого элемента в диапазоне копируемых элементов.

*_Окончания*<br/>
Положение первого элемента за пределами диапазона копируемых элементов.

### <a name="remarks"></a>Примечания

Все конструкторы хранят объект распределителя `_Al` и инициализируют очередь.

Первый конструктор задает пустую начальную очередь и явно указывает тип распределителя, который будет использоваться.

Второй конструктор указывает копию параллельной очереди `_OtherQ`.

Третий конструктор определяет перемещение параллельная очередь `_OtherQ`.

Четвертый конструктор задает значения, передаваемые диапазоном итератора [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~concurrent_queue

Уничтожает параллельной очереди.

```
~concurrent_queue();
```

##  <a name="empty"></a> пустой

Проверяет ли параллельная очередь пуста в данный момент этот метод вызывается. Этот метод безопасен в режиме параллелизма.

```
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если параллельная очередь была пуста, в данный момент, мы уже видели, **false** в противном случае.

### <a name="remarks"></a>Примечания

Хотя этот метод является параллельно безопасно по отношению к вызовы методов `push`, `try_pop`, и `empty`, возвращаемое значение может быть неверный по времени, то оно проверяется вызывающим потоком.

##  <a name="get_allocator"></a> get_allocator

Возвращает копию распределителя, используемого для создания параллельной очереди. Этот метод безопасен в режиме параллелизма.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Копию распределителя, используемого для создания параллельной очереди.

##  <a name="push"></a> Push-уведомлений

Ставит в очередь элемент в конец параллельной очереди. Этот метод безопасен в режиме параллелизма.

```
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Элемент, добавляемый в очередь.

### <a name="remarks"></a>Примечания

`push` параллелизм с точки зрения по отношению к вызовы методов `push`, `try_pop`, и `empty`.

##  <a name="try_pop"></a> try_pop

Удаляет элемент из очереди, если таковой доступен. Этот метод безопасен в режиме параллелизма.

```
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Ссылка на расположение для сохранения элемент удален из очереди.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если элемент был успешно удален из очереди, **false** в противном случае.

### <a name="remarks"></a>Примечания

Если элемент был успешно удален из очереди, параметр `_Dest` получает значение, исключенных из очереди, исходное значение, содержащееся в очереди разрушается, и эта функция возвращает **true**. Если не было элемента для извлечения из очереди, эта функция возвращает `false` без блокировки и содержимое `_Dest` параметра не определены.

`try_pop` параллелизм с точки зрения по отношению к вызовы методов `push`, `try_pop`, и `empty`.

##  <a name="unsafe_begin"></a> unsafe_begin

Возвращает итератор, указывающий тип `iterator` или `const_iterator` в начале параллельной очереди. Этот метод не является безопасным в режиме параллелизма.

```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий тип `iterator` или `const_iterator` в начале параллельной очереди объекта.

### <a name="remarks"></a>Примечания

Итераторы для `concurrent_queue` класс в основном предназначены для отладки, так как они выполняются медленно, и итерации не нарушающих параллельность по отношению к другие операции очереди.

##  <a name="unsafe_end"></a> unsafe_end

Возвращает итератор, указывающий тип `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.

```
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий тип `iterator` или `const_iterator` в конец параллельной очереди.

### <a name="remarks"></a>Примечания

Итераторы для `concurrent_queue` класс в основном предназначены для отладки, так как они выполняются медленно, и итерации не нарушающих параллельность по отношению к другие операции очереди.

##  <a name="unsafe_size"></a> unsafe_size

Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.

```
size_type unsafe_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер параллельной очереди.

### <a name="remarks"></a>Примечания

`unsafe_size` не нарушающих параллельность и может выдавать неверные результаты, если вызван параллельно с вызовами методов `push`, `try_pop`, и `empty`.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
