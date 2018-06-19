---
title: стек (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack
dev_langs:
- C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 290857b51fea6726ec7e4a836d4afe1b33a8e615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172448"
---
# <a name="stack-stlclr"></a>stack (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с доступом к последней обслужен. Используйте адаптер контейнера `stack` управление базового контейнера, что стек принудительной передачи.  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`. Аналогичным образом `GContainer` совпадает со значением `Container` Если последний является типом ссылки, в этом случае он является `Container^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|Тип базового контейнера.|  
|[stack::difference_type (STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|Тип универсального интерфейса для адаптера контейнера.|  
|[stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|Тип элемента для универсальный интерфейс для адаптера контейнера.|  
|[stack::reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[stack::size_type (STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)|Заменяет все элементы.|  
|[stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[stack::get_container (STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|Обращается к базового контейнера.|  
|[stack::pop (STL/CLR)](../dotnet/stack-pop-stl-clr.md)|Удаляет последний элемент.|  
|[stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)|Добавляет новый последний элемент.|  
|[stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[stack::stack (STL/CLR)](../dotnet/stack-stack-stl-clr.md)|Создает объект контейнера.|  
|[stack::top (STL/CLR)](../dotnet/stack-top-stl-clr.md)|Обращается к последнему элементу.|  
|[stack::to_array (STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|[stack::top_item (STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|Обращается к последнему элементу.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[operator!= (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|Определяет, если `stack` объект не равен другому `stack` объекта.|  
|[operator< (stack) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|Определяет, если `stack` объект меньше другого `stack` объекта.|  
|[operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Определяет, если `stack` объекта меньше или равно другому `stack` объекта.|  
|[operator== (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|Определяет, если `stack` объект равен другому `stack` объекта.|  
|[operator> (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|Определяет, если `stack` объект больше другого `stack` объекта.|  
|[operator>= (stack) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Определяет, если `stack` объекта больше или равно другому `stack` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|IStack\<значение, контейнер >|Ведение адаптера универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через базового контейнера, типа `Container`, в которых хранятся `Value` элементы и увеличивается по требованию. Объект ограничивает доступ к помещают и извлекают только последнего элемента, реализации очереди последнего обслужен (также известный как LIFO очередь или стек).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/stack >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)