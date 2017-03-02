---
title: "Класс concurrent_queue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_queue/concurrency::concurrent_queue
- concurrent_queue/Concurrency::concurrent_queue
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: aac7b15db82fbd2ceb801f45ff1b70c293014080
ms.lasthandoff: 02/24/2017

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
 Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для этой параллельной очереди. Этот аргумент является необязательным, и значением по умолчанию является `allocator<``T``>`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди.|  
|`const_iterator`|Тип, который представляет не потокобезопасный `const` итератор над элементами в параллельной очереди.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент, хранящийся в параллельной очереди для чтения и выполнения `const` операций.|  
|`difference_type`|Тип, предоставляющий расстояние со знаком между двумя элементами в параллельной очереди.|  
|`iterator`|Тип, который представляет не потокобезопасный итератор над элементами в параллельной очереди.|  
|`reference`|Тип, предоставляющий ссылку на элемент, хранящийся в параллельной очереди.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди.|  
|`value_type`|Тип, представляющий тип данных, хранящийся в параллельной очереди.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор concurrent_queue](#ctor)|Перегружен. Создает параллельную очередь.|  
|[~ concurrent_queue деструктор](#dtor)|Уничтожает параллельную очереди.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Clear-метод](#clear)|Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[Empty-метод](#empty)|Проверяет ли параллельная очередь пуста в момент вызывается этот метод. Данный метод безопасен в режиме параллелизма.|  
|[get_allocator метод](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельной очереди. Данный метод безопасен в режиме параллелизма.|  
|[Метод Push](#push)|Перегружен. Добавляет элемент в конец параллельной очереди. Данный метод безопасен в режиме параллелизма.|  
|[try_pop метод](#try_pop)|Удаляет элемент из очереди, если он доступен. Данный метод безопасен в режиме параллелизма.|  
|[unsafe_begin метод](#unsafe_begin)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` для создания параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[unsafe_end метод](#unsafe_end)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.|  
|[unsafe_size метод](#unsafe_size)|Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `concurrent_queue`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concurrent_queue.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Очистка 

 Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
void clear();
```  
  
##  <a name="a-namectora-concurrentqueue"></a><a name="ctor"></a>concurrent_queue 

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
 Тип итератора ввода, который определяет диапазон значений.  
  
 `_Al`  
 Класс распределителя для использования с данным объектом.  
  
 `_OtherQ`  
 Исходный объект `concurrent_queue` для копирования или перемещения элементов.  
  
 `_Begin`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `_End`  
 Положение первого элемента за пределами диапазона копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя `_Al` и инициализировать очереди.  
  
 Первый конструктор задает пустую начальную очередь и явно указывает тип распределителя, который будет использоваться.  
  
 Второй конструктор указывает копию параллельной очереди `_OtherQ`.  
  
 Третий конструктор определяет перемещение параллельной очереди `_OtherQ`.  
  
 Четвертый конструктор задает значения, полученные из итератора диапазона [ `_Begin`, `_End`).  
  
##  <a name="a-namedtora-concurrentqueue"></a><a name="dtor"></a>~ concurrent_queue 

 Уничтожает параллельную очереди.  
  
```
~concurrent_queue();
```  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>пустой 

 Проверяет ли параллельная очередь пуста в момент вызывается этот метод. Данный метод безопасен в режиме параллелизма.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если в данный момент, мы уже видели, пусто параллельной очереди `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Хотя данный метод безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`, возвращаемое значение могут быть неправильными ко времени просмотра вызывающим потоком.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Возвращает копию распределителя, используемого для создания параллельной очереди. Данный метод безопасен в режиме параллелизма.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копию распределителя, используемого для создания параллельной очереди.  
  
##  <a name="a-namepusha-push"></a><a name="push"></a>Push 

 Добавляет элемент в конец параллельной очереди. Данный метод безопасен в режиме параллелизма.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
 Элемент, добавляемый в очередь.  
  
### <a name="remarks"></a>Примечания  
 `push`безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`.  
  
##  <a name="a-nametrypopa-trypop"></a><a name="try_pop"></a>try_pop 

 Удаляет элемент из очереди, если он доступен. Данный метод безопасен в режиме параллелизма.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Ссылка на расположение для хранения элемент удален из очереди.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если элемент был успешно удален из очереди, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если элемент был успешно удален из очереди, параметр `_Dest` получает значение удаления из очереди, исходное значение, содержащееся в очередь удаляется, и эта функция возвращает `true`. Если не было элемента для извлечения из очереди, эта функция возвращает `false` без блокировки и содержимое `_Dest` параметра не определено.  
  
 `try_pop`безопасен в режиме параллелизма относительно вызовы методов `push`, `try_pop`, и `empty`.  
  
##  <a name="a-nameunsafebegina-unsafebegin"></a><a name="unsafe_begin"></a>unsafe_begin 

 Возвращает итератор типа `iterator` или `const_iterator` для создания параллельной очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` в начало объекта параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 Итераторы для `concurrent_queue` класс в основном предназначены для отладки, как они выполняются медленно и итерация не параллельно безопасная относительно других операций очереди.  
  
##  <a name="a-nameunsafeenda-unsafeend"></a><a name="unsafe_end"></a>unsafe_end 

 Возвращает итератор типа `iterator` или `const_iterator` в конец параллельной очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` в конец параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 Итераторы для `concurrent_queue` класс в основном предназначены для отладки, как они выполняются медленно и итерация не параллельно безопасная относительно других операций очереди.  
  
##  <a name="a-nameunsafesizea-unsafesize"></a><a name="unsafe_size"></a>unsafe_size 

 Возвращает количество элементов в очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер параллельной очереди.  
  
### <a name="remarks"></a>Примечания  
 `unsafe_size`не является безопасным в режиме параллелизма и может выдавать неверные результаты, если вызван параллельно с вызовами методов `push`, `try_pop`, и `empty`.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

