---
title: очереди (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e65d5a364f5886df2bad976e3c34dc57266b70f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172748"
---
# <a name="queue-stlclr"></a>queue (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с доступом к очереди. Используйте адаптер контейнера `queue` управление базового контейнера, как очередь.  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`. Аналогичным образом `GContainer` совпадает со значением `Container` Если последний является типом ссылки, в этом случае он является `Container^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)|Тип базового контейнера.|  
|[queue::difference_type (STL/CLR)](../dotnet/queue-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)|Тип универсального интерфейса для адаптера контейнера.|  
|[queue::generic_value (STL/CLR)](../dotnet/queue-generic-value-stl-clr.md)|Тип элемента для универсальный интерфейс для адаптера контейнера.|  
|[queue::reference (STL/CLR)](../dotnet/queue-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[queue::size_type (STL/CLR)](../dotnet/queue-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)|Заменяет все элементы.|  
|[queue::back (STL/CLR)](../dotnet/queue-back-stl-clr.md)|Обращается к последнему элементу.|  
|[queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)|Обращается к первому элементу.|  
|[queue::get_container (STL/CLR)](../dotnet/queue-get-container-stl-clr.md)|Обращается к базового контейнера.|  
|[queue::pop (STL/CLR)](../dotnet/queue-pop-stl-clr.md)|Удаляет первый элемент.|  
|[queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)|Добавляет новый последний элемент.|  
|[queue::queue (STL/CLR)](../dotnet/queue-queue-stl-clr.md)|Создает объект контейнера.|  
|[queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[queue::to_array (STL/CLR)](../dotnet/queue-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|[queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)|Обращается к последнему элементу.|  
|[queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)|Обращается к первому элементу.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[operator!= (queue) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)|Определяет, если `queue` объект не равен другому `queue` объекта.|  
|[operator< (queue) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)|Определяет, если `queue` объект меньше другого `queue` объекта.|  
|[operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Определяет, если `queue` объекта меньше или равно другому `queue` объекта.|  
|[operator== (queue) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)|Определяет, если `queue` объект равен другому `queue` объекта.|  
|[operator> (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)|Определяет, если `queue` объект больше другого `queue` объекта.|  
|[operator>= (queue) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Определяет, если `queue` объекта больше или равно другому `queue` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|IQueue\<значение, контейнер >|Ведение адаптера универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через базового контейнера, типа `Container`, в которых хранятся `Value` элементы и увеличивается по требованию. Объект ограничивает доступ к только что принудительной отправки первого элемента и выталкивания за последним элементом, реализация первым обслужен очередь (также известный как очередь FIFO или просто очереди).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)