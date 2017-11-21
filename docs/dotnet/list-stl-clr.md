---
title: "список (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list
dev_langs: C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 991b72b312c8ad1b36a9a401a6452ec36ea25d6e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="list-stlclr"></a>list (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с двунаправленный доступ. Используйте контейнер `list` управления последовательность элементов в качестве двунаправленного связанного списка узлов, в каждой хранения одного элемента.  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## <a name="members"></a>Члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[list::const_iterator (STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[list::const_reference (STL/CLR)](../dotnet/list-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[list::const_reverse_iterator (STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[list::difference_type (STL/CLR)](../dotnet/list-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[list::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[list::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[list::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[list::generic_value (STL/CLR)](../dotnet/list-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[list::iterator (STL/CLR)](../dotnet/list-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[list::reference (STL/CLR)](../dotnet/list-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[list::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[list::size_type (STL/CLR)](../dotnet/list-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[list::value_type (STL/CLR)](../dotnet/list-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)|Заменяет все элементы.|  
|[list::back (STL/CLR)](../dotnet/list-back-stl-clr.md)|Обращается к последнему элементу.|  
|[list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)|Удаляет все элементы.|  
|[list::empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[list::front (STL/CLR)](../dotnet/list-front-stl-clr.md)|Обращается к первому элементу.|  
|[list::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)|Добавляет элементы в заданной позиции.|  
|[list::list (STL/CLR)](../dotnet/list-list-stl-clr.md)|Создает объект контейнера.|  
|[list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)|Объединяет две упорядоченные управляемые последовательности.|  
|[list::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)|Удаляет последний элемент.|  
|[list::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)|Удаляет первый элемент.|  
|[list::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)|Добавляет новый первый элемент.|  
|[list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[list::remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)|Удаляет элемент с указанным значением.|  
|[list::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)|Удаляет элементы, которые прошли заданный тест.|  
|[list::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[list::resize (STL/CLR)](../dotnet/list-resize-stl-clr.md)|Изменяет количество элементов.|  
|[list::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)|Отмена управляемой последовательности.|  
|[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)|Упорядочивает управляемую последовательность.|  
|[list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)|Восстанавливает ссылки между узлами.|  
|[list::swap (STL/CLR)](../dotnet/list-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[list::to_array (STL/CLR)](../dotnet/list-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)|Удаляет смежные элементы, которые прошли заданный тест.|  
  
|Свойство|Описание|  
|--------------|-----------------|  
|[list::back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)|Обращается к последнему элементу.|  
|[list::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)|Обращается к первому элементу.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[operator!= (list) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)|Определяет, если `list` объект не равен другому `list` объекта.|  
|[operator< (list) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)|Определяет, если `list` объект меньше другого `list` объекта.|  
|[operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Определяет, если `list` объекта меньше или равно другому `list` объекта.|  
|[operator== (list) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)|Определяет, если `list` объект равен другому `list` объекта.|  
|[operator> (list) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)|Определяет, если `list` объект больше другого `list` объекта.|  
|[operator>= (list) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Определяет, если `list` объекта больше или равно другому `list` объекта.|  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|IList\<значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для последовательность, в которой он управляет, как отдельные узлы в списке двунаправленных ссылок. Он упорядочение элементов путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы оставшиеся элементы. Таким образом, список является хорошим кандидатом для базового контейнера для шаблона класса [очереди (STL/CLR)](../dotnet/queue-stl-clr.md) или класс шаблона [стека (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Объект `list` объект поддерживает Двунаправленные итераторы, это означает, что переходе на соседние элементы, учитывая итератор, указывающий на элемент управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`. Можно уменьшить этот итератор для достижения последнего элемента в управляемой последовательности, при его наличии. Можно увеличить значение итератора списка, чтобы достичь головного узла, а затем будет считаться равным `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент списка, непосредственно заданным его порядкового номера--, требующий итератора произвольного доступа. Поэтому список `not` использования в качестве базового контейнера для шаблона класса [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Итератор список сохраняет дескриптор его узел связанного списка, который в свою очередь, сохраняет дескриптор связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор список остается допустимым до тех пор, пока его узел связанного списка связан с какого-либо списка. Кроме того, допустимым итератором dereferencable — используется для доступа или изменить значение элемента, он обозначает--до тех пор, пока не равно `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)