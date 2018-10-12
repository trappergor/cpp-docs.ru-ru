---
title: Класс concurrent_priority_queue | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
dev_langs:
- C++
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de97557025929c394039b1a786fe12a7035381e1
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163157"
---
# <a name="concurrentpriorityqueue-class"></a>Класс concurrent_priority_queue

Класс `concurrent_priority_queue` — это контейнер, который позволяет нескольким потокам параллельно помещать и извлекать элементы. Элементы извлекаются в порядке приоритета, определяемого функтором, предоставленным в качестве аргумента шаблона.

## <a name="syntax"></a>Синтаксис

```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранимых в очереди с приоритетом.

*_Сравнить*<br/>
Тип объекта функции, который может сравнивать значения двух элементов в качестве ключей сортировки для определения их относительного порядка в очереди с приоритетом. Этот аргумент является необязательным, и в качестве значения по умолчанию используется бинарный предикат `less<T>`.

*_Ax*<br/>
Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельной очереди с приоритетом. Этот аргумент является необязательным, и значением по умолчанию является `allocator<T>`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди с приоритетом.|
|`const_reference`|Тип, представляющий константную ссылку на элемент типа, хранящийся в параллельной очереди с приоритетом.|
|`reference`|Тип, представляющий ссылку на элемент типа, хранящийся в параллельной очереди с приоритетом.|
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди с приоритетом.|
|`value_type`|Тип, представляющий тип данных, хранящихся в параллельной очереди с приоритетом.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|Перегружен. Создает параллельную очередь с приоритетом.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[clear](#clear)|Удаляет все элементы в параллельной очереди с приоритетом. Этот метод не является безопасным в режиме параллелизма.|
|[empty](#empty)|Проверяет, пуста ли параллельная очередь с приоритетом в момент, когда этот метод вызывается. Этот метод безопасен в режиме параллелизма.|
|[get_allocator](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельной очереди с приоритетом. Этот метод безопасен в режиме параллелизма.|
|[push](#push)|Перегружен. Добавляет элемент в параллельную очередь с приоритетом. Этот метод безопасен в режиме параллелизма.|
|[size](#size)|Возвращает число элементов в параллельной очереди с приоритетом. Этот метод безопасен в режиме параллелизма.|
|[swap](#swap)|Меняет местами содержимое двух параллельных очередей с приоритетом. Этот метод не является безопасным в режиме параллелизма.|
|[try_pop](#try_pop)|Удаляет и возвращает элемент наивысшего приоритета из очереди, если очередь не пуста. Этот метод безопасен в режиме параллелизма.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Перегружен. Назначает содержимое другого объекта `concurrent_priority_queue` в данный объект. Этот метод не является безопасным в режиме параллелизма.|

## <a name="remarks"></a>Примечания

Подробные сведения о `concurrent_priority_queue` , представлена в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`concurrent_priority_queue`

## <a name="requirements"></a>Требования

**Заголовок:** concurrent_priority_queue.h

**Пространство имен:** concurrency

##  <a name="clear"></a> Очистить

Удаляет все элементы в параллельной очереди с приоритетом. Этот метод не является безопасным в режиме параллелизма.

```
void clear();
```

### <a name="remarks"></a>Примечания

`clear` не является безопасным в режиме параллелизма. Убедитесь, что нет других потоков, вызывающих методов в параллельной очереди с приоритетом, при вызове этого метода. `clear` не освобождает память.

##  <a name="ctor"></a> concurrent_priority_queue

Создает параллельную очередь с приоритетом.

```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```

### <a name="parameters"></a>Параметры

*_InputIterator*<br/>
Тип итератора ввода.

*_Al*<br/>
Класс распределителя для использования с данным объектом.

*_Init_capacity*<br/>
Начальная производительность объекта `concurrent_priority_queue`.

*Н_ачать*<br/>
Положение первого элемента в диапазоне копируемых элементов.

*_Окончания*<br/>
Положение первого элемента после диапазона копируемых элементов.

*_Src*<br/>
Исходный объект `concurrent_priority_queue` для копирования или перемещения элементов.

### <a name="remarks"></a>Примечания

Все конструкторы хранят объект распределителя `_Al` и инициализировать очереди с приоритетом.

Первый конструктор задает пустой начальный приоритет очереди и при необходимости определяет распределитель.

Второй конструктор определяет очередь приоритетов с начальной емкостью `_Init_capacity` и при необходимости указывает распределителя.

Третий конструктор задает значения, передаваемые диапазоном итератора [ `_Begin`, `_End`) и при необходимости указывает распределителя.

Четвертый и пятый конструкторы указывают копию очереди с приоритетом `_Src`.

Шестой и седьмой конструкторы укажите перемещение очереди с приоритетом `_Src`.

##  <a name="empty"></a> пустой

Проверяет, пуста ли параллельная очередь с приоритетом в момент, когда этот метод вызывается. Этот метод безопасен в режиме параллелизма.

```
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если очереди с приоритетом был пуст, в данный момент, что функция была вызвана, **false** в противном случае.

##  <a name="get_allocator"></a> get_allocator

Возвращает копию распределителя, используемого для создания параллельной очереди с приоритетом. Этот метод безопасен в режиме параллелизма.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Копию распределителя, использованного для создания `concurrent_priority_queue` объекта.

##  <a name="operator_eq"></a> оператор =

Назначает содержимое другого объекта `concurrent_priority_queue` в данный объект. Этот метод не является безопасным в режиме параллелизма.

```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Исходный объект `concurrent_priority_queue`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `concurrent_priority_queue` объекта.

##  <a name="push"></a> Push-уведомлений

Добавляет элемент в параллельную очередь с приоритетом. Этот метод безопасен в режиме параллелизма.

```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>Параметры

*_Elem*<br/>
Элемент для добавления параллельной очереди с приоритетом.

##  <a name="size"></a> Размер

Возвращает число элементов в параллельной очереди с приоритетом. Этот метод безопасен в режиме параллелизма.

```
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в этом `concurrent_priority_queue` объекта.

### <a name="remarks"></a>Примечания

Возвращаемый размер гарантированно включить все элементы, добавленные к функции `push`. Тем не менее он может не отражать результаты одновременных операций в очереди.

##  <a name="swap"></a> Swap

Меняет местами содержимое двух параллельных очередей с приоритетом. Этот метод не является безопасным в режиме параллелизма.

```
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>Параметры

*_Queue*<br/>
`concurrent_priority_queue` Объект для обмена содержимым.

##  <a name="try_pop"></a> try_pop

Удаляет и возвращает элемент наивысшего приоритета из очереди, если очередь не пуста. Этот метод безопасен в режиме параллелизма.

```
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>Параметры

*_Elem*<br/>
Ссылка на переменную, которая будет заполняться элемент наивысшего приоритета, если очередь пуста.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если был извлечен на значение, **false** в противном случае.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)

