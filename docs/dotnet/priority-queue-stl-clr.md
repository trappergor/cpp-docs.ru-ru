---
title: priority_queue (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63e806603a795a71dc2afb95ae17779d1c6f210b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172544"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
Класс шаблона описывает объект, управляющий переменной длины упорядоченную последовательность элементов с ограниченным доступом. Используйте адаптер контейнера `priority_queue` управление базового контейнера, как очередь с приоритетом.  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`. Аналогичным образом `GContainer` совпадает со значением `Container` Если последний является типом ссылки, в этом случае он является `Container^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
 Контейнер  
 Тип базового контейнера.  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](../dotnet/priority-queue-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)|Тип базового контейнера.|  
|[priority_queue::difference_type (STL/CLR)](../dotnet/priority-queue-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)|Тип универсального интерфейса для адаптера контейнера.|  
|[priority_queue::generic_value (STL/CLR)](../dotnet/priority-queue-generic-value-stl-clr.md)|Тип элемента для универсальный интерфейс для адаптера контейнера.|  
|[priority_queue::reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[priority_queue::size_type (STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)|Делегат упорядочения для двух элементов.|  
|[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)|Заменяет все элементы.|  
|[priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[priority_queue::get_container (STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)|Обращается к базового контейнера.|  
|[priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)|Удаляет элемент hghest приоритета.|  
|[priority_queue::priority_queue (STL/CLR)](../dotnet/priority-queue-priority-queue-stl-clr.md)|Создает объект контейнера.|  
|[priority_queue::push (STL/CLR)](../dotnet/priority-queue-push-stl-clr.md)|Добавляет новый элемент.|  
|[priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[priority_queue::top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)|Обращается к элементу наивысший приоритет.|  
|[priority_queue::to_array (STL/CLR)](../dotnet/priority-queue-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)|Копирует делегат упорядочения для двух элементов.|  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)|Обращается к элементу наивысший приоритет.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|IPriorityQueue\<значение, контейнер >|Ведение адаптера универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через базового контейнера, типа `Container`, в которых хранятся `Value` элементы и увеличивается по требованию. Она хранит последовательности, упорядоченных в виде кучи, с наивысшим приоритетом элементом (верхний элемент) легко доступны и съемных. Объект ограничивает доступ к помещают новые элементы и извлекают только высокий приоритет элемента, реализация очередь с приоритетом.  
  
 Объект Упорядочивает управляемую последовательность путем вызова хранимых делегат типа [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Объект хранимых делегата можно указать при создании priority_queue; Если указан объект делегата не значение по умолчанию является сравнение `operator<(value_type, value_type)`. Доступ к этому сохраненному объекту путем вызова функции-члена [priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Объект делегата должен применить строгого слабое упорядочение к значениям типа [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `value_comp()(X, Y)` Возвращает значение того же типа Boolean привести при каждом вызове.  
  
 Если `value_comp()(X, Y)` имеет значение true, затем `value_comp()(Y, X)` должен иметь значение false.  
  
 Если `value_comp()(X, Y)` имеет значение true, затем `X` называется располагаются перед `Y`.  
  
 Если `!value_comp()(X, Y) && !value_comp()(Y, X)` имеет значение true, затем `X` и `Y` говорят, что имеют соответствующий порядок.  
  
 Для любого элемента `X` , предшествующий `Y` в управляемой последовательности `key_comp()(Y, X)` имеет значение false. (По умолчанию объекта делегата, ключи никогда не уменьшаются.)  
  
 Таким образом элемент наивысшего приоритета является одним из элементов, которые не упорядочен до любого другого элемента.  
  
 Поскольку базового контейнера отслеживает элементов, упорядоченных в виде кучи:  
  
 Контейнер должен поддерживать итераторами произвольного доступа.  
  
 Элементы с соответствующим образом может извлекаться в другом порядке, чем они были размещены. (Порядок не имеет стабильный.)  
  
 Таким образом, базового контейнера могут использоваться [deque (STL/CLR)](../dotnet/deque-stl-clr.md) и [вектор (STL/CLR)](../dotnet/vector-stl-clr.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)