---
title: "Класс concurrent_priority_queue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16a9114278cd9559a0a21191faeb87ee34b5a5df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
 `T`  
 Тип данных элементов, хранимых в очереди с приоритетом.  
  
 `_Compare`  
 Тип объекта функции, который может сравнивать значения двух элементов в качестве ключей сортировки для определения их относительного порядка в очереди с приоритетом. Этот аргумент является необязательным, и в качестве значения по умолчанию используется бинарный предикат `less<T>`.  
  
 `_Ax`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельной очереди с приоритетом. Этот аргумент является необязательным, и значением по умолчанию является `allocator<T>`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди с приоритетом.|  
|`const_reference`|Тип, представляющий константную ссылку на элемент типа, хранящийся в параллельной очереди с приоритетом.|  
|`reference`|Тип, представляющий ссылку на элемент типа, хранящийся в параллельной очереди с приоритетом.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди с приоритетом.|  
|`value_type`|Тип, представляющий тип данных, хранящихся в параллельной очереди с приоритетом.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[concurrent_priority_queue](#ctor)|Перегружен. Создает параллельную очередь с приоритетом.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[clear](#clear)|Удаляет все элементы в параллельной очереди с приоритетом. Этот метод не является безопасным в режиме параллелизма.|  
|[empty](#empty)|Проверяет, пуста ли параллельная очередь с приоритетом в момент, когда этот метод вызывается. Данный метод безопасен в режиме параллелизма.|  
|[get_allocator](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельной очереди с приоритетом. Данный метод безопасен в режиме параллелизма.|  
|[push](#push)|Перегружен. Добавляет элемент в параллельную очередь с приоритетом. Данный метод безопасен в режиме параллелизма.|  
|[size](#size)|Возвращает число элементов в параллельной очереди с приоритетом. Данный метод безопасен в режиме параллелизма.|  
|[swap](#swap)|Меняет местами содержимое двух параллельных очередей с приоритетом. Этот метод не является безопасным в режиме параллелизма.|  
|[try_pop](#try_pop)|Удаляет и возвращает элемент наивысшего приоритета из очереди, если очередь не пуста. Данный метод безопасен в режиме параллелизма.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Перегружен. Назначает содержимое другой `concurrent_priority_queue` этого объекта. Этот метод не является безопасным в режиме параллелизма.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о `concurrent_priority_queue` см. в описании [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `concurrent_priority_queue`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concurrent_priority_queue.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="clear"></a> Снимите флажок 

 Удаляет все элементы в параллельной очереди с приоритетом. Этот метод не является безопасным в режиме параллелизма.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Примечания  
 `clear` не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методов в параллельной очереди с приоритетом, при вызове этого метода. `clear` не освобождает память.  
  
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
 `_InputIterator`  
 Тип итератора ввода.  
  
 `_Al`  
 Класс распределителя для использования с данным объектом.  
  
 `_Init_capacity`  
 Начальная производительность объекта `concurrent_priority_queue`.  
  
 `_Begin`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `_End`  
 Положение первого элемента после диапазона копируемых элементов.  
  
 `_Src`  
 Исходный объект `concurrent_priority_queue` для копирования или перемещения элементов.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя `_Al` и инициализировать в очередь с приоритетом.  
  
 Первый конструктор задает пустую начальный приоритет очередь и при необходимости указывает распределителя.  
  
 Второй конструктор определяет очередь с приоритетом с начальной емкостью `_Init_capacity` и при необходимости указывает распределителя.  
  
 Третий конструктор задает значения, предоставленные диапазоном итератора [ `_Begin`, `_End`) и при необходимости указывает распределителя.  
  
 Четвертый и пятый конструкторы определяют копию очереди с приоритетом `_Src`.  
  
 Шестой и седьмой конструкторы укажите перемещения в очередь с приоритетом `_Src`.  
  
##  <a name="empty"></a> пустой 

 Проверяет, пуста ли параллельная очередь с приоритетом в момент, когда этот метод вызывается. Данный метод безопасен в режиме параллелизма.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если очередь с приоритетом был пустым в момент вызова функции, `false` в противном случае.  
  
##  <a name="get_allocator"></a> get_allocator 

 Возвращает копию распределителя, используемого для создания параллельной очереди с приоритетом. Данный метод безопасен в режиме параллелизма.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копию распределителя, используемого для создания `concurrent_priority_queue` объекта.  
  
##  <a name="operator_eq"></a> оператор = 

 Назначает содержимое другой `concurrent_priority_queue` этого объекта. Этот метод не является безопасным в режиме параллелизма.  
  
```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
 Исходный объект `concurrent_priority_queue`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `concurrent_priority_queue` объекта.  
  
##  <a name="push"></a> Push-уведомлений 

 Добавляет элемент в параллельную очередь с приоритетом. Данный метод безопасен в режиме параллелизма.  
  
```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```  
  
### <a name="parameters"></a>Параметры  
 `_Elem`  
 Элемент, который необходимо добавить в параллельной очереди с приоритетом.  
  
##  <a name="size"></a> Размер 

 Возвращает число элементов в параллельной очереди с приоритетом. Данный метод безопасен в режиме параллелизма.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в этом `concurrent_priority_queue` объекта.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный размер обязательно включать все элементы, добавленные с помощью вызовов функции `push`. Тем не менее он может не отражать результаты выполнения параллельных операций в очереди.  
  
##  <a name="swap"></a> swap 

 Меняет местами содержимое двух параллельных очередей с приоритетом. Этот метод не является безопасным в режиме параллелизма.  
  
```
void swap(concurrent_priority_queue& _Queue);
```  
  
### <a name="parameters"></a>Параметры  
 `_Queue`  
 `concurrent_priority_queue` Объекта для обмена содержимым.  
  
##  <a name="try_pop"></a> try_pop 

 Удаляет и возвращает элемент наивысшего приоритета из очереди, если очередь не пуста. Данный метод безопасен в режиме параллелизма.  
  
```
bool try_pop(reference _Elem);
```  
  
### <a name="parameters"></a>Параметры  
 `_Elem`  
 Ссылка на переменную, которая будет заполняться элемент наивысшего приоритета, если очередь не пуста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если значение был извлечен, `false` в противном случае.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)



