---
title: Класс concurrent_queue | Документы Microsoft
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
ms.openlocfilehash: a9a3ee82b8b81532b4e63f080ad321a93725ce41
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentqueue-class"></a>Класс concurrent_queue
Класс `concurrent_queue` представляет собой класс контейнера последовательности, обеспечивающий доступ к элементам в порядке поступления. Он позволяет использовать ограниченный набор параллельно-безопасных операций, таких как `push` и `try_pop`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранимых в очереди.  
  
 `_Ax`  
 Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для этой параллельной очереди. Этот аргумент является необязательным, и значением по умолчанию является `allocator<T>`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди.|  
|`const_iterator`|Тип, который представляет не потокобезопасный `const` итератор элементы в параллельной очереди.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент, хранящийся в параллельной очереди для чтения и выполнения `const` операций.|  
|`difference_type`|Тип, предоставляющий расстояние со знаком между двумя элементами в параллельной очереди.|  
|`iterator`|Тип, который представляет собой итератор не поточно ориентированного на элементы в параллельной очереди.|  
|`reference`|Тип, предоставляющий ссылку на элемент, хранящийся в параллельной очереди.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди.|  
|`value_type`|Тип, представляющий тип данных, хранящийся в параллельной очереди.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|Перегружен. Создает параллельную очередь.|  
|[~ concurrent_queue деструктор](#dtor)|Уничтожает параллельной очереди.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[clear](#clear)|Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[empty](#empty)|Определяет, верно ли параллельная очередь пуста в данный момент этот метод вызывается. Данный метод безопасен в режиме параллелизма.|  
|[get_allocator](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельной очереди. Данный метод безопасен в режиме параллелизма.|  
|[push](#push)|Перегружен. Помещает элемент в конец параллельной очереди. Данный метод безопасен в режиме параллелизма.|  
|[try_pop](#try_pop)|Удаляет элемент из очереди, если он доступен. Данный метод безопасен в режиме параллелизма.|  
|[unsafe_begin](#unsafe_begin)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` в начале параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[unsafe_end](#unsafe_end)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[unsafe_size](#unsafe_size)|Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `concurrent_queue`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concurrent_queue.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="clear"></a> Снимите флажок 

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
 `_InputIterator`  
 Тип входного итератора, который определяет диапазон значений.  
  
 `_Al`  
 Класс распределителя для использования с данным объектом.  
  
 `_OtherQ`  
 Исходный объект `concurrent_queue` для копирования или перемещения элементов.  
  
 `_Begin`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `_End`  
 Положение первого элемента за пределами диапазона копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя `_Al` и инициализации очереди.  
  
 Первый конструктор задает пустую начальную очередь и явно указывает тип распределителя, который будет использоваться.  
  
 Второй конструктор определяет копию параллельной очереди `_OtherQ`.  
  
 Третий конструктор определяет перемещение параллельной очереди `_OtherQ`.  
  
 Четвертый конструктор задает значения, предоставленные диапазоном итератора [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~concurrent_queue 

 Уничтожает параллельной очереди.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> пустой 

 Определяет, верно ли параллельная очередь пуста в данный момент этот метод вызывается. Данный метод безопасен в режиме параллелизма.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если в данный момент мы уже видели, пусто параллельной очереди `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Хотя данный метод безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`, возвращаемое значение может быть неверный по времени, то оно проверяется вызывающим потоком.  
  
##  <a name="get_allocator"></a> get_allocator 

 Возвращает копию распределителя, используемого для создания параллельной очереди. Данный метод безопасен в режиме параллелизма.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копию распределителя, используемого для создания параллельной очереди.  
  
##  <a name="push"></a> Push-уведомлений 

 Помещает элемент в конец параллельной очереди. Данный метод безопасен в режиме параллелизма.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
 Элемент, добавляемый в очередь.  
  
### <a name="remarks"></a>Примечания  
 `push` безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`.  
  
##  <a name="try_pop"></a> try_pop 

 Удаляет элемент из очереди, если он доступен. Данный метод безопасен в режиме параллелизма.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Ссылка на расположение для хранения элемент удален из очереди.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если элемент был успешно удален из очереди `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если элемент был успешно удален из очереди, параметр `_Dest` получает значение удаления из очереди, исходное значение, содержащееся в очередь удаляется, и эта функция возвращает `true`. Если не было элемента для удаления из очереди, эта функция возвращает `false` без блокировки и содержимое `_Dest` параметра не определены.  
  
 `try_pop` безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Возвращает итератор типа `iterator` или `const_iterator` в начале параллельной очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` начало объекта параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 Итераторы для `concurrent_queue` класса в первую очередь предназначены для отладки, как они выполняются медленно и итерация не является безопасным в режиме параллелизма относительно других операций очереди.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Возвращает итератор типа `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` в конец параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 Итераторы для `concurrent_queue` класса в первую очередь предназначены для отладки, как они выполняются медленно и итерация не является безопасным в режиме параллелизма относительно других операций очереди.  
  
##  <a name="unsafe_size"></a> unsafe_size 

 Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 `unsafe_size` не является безопасным в режиме параллелизма и может выдавать неверные результаты, если вызван параллельно с вызовами методов `push`, `try_pop`, и `empty`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
