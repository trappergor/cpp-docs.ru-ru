---
title: вектор (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: de5d09d569933dc06666ed2008081703d59c1564
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="vector-stlclr"></a>vector (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с произвольного доступа. Используйте контейнер `vector` для управления последовательностью элементов как непрерывный блок памяти. Блок реализуется как массив, который увеличивается по требованию.  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## <a name="members"></a>Члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[vector::const_iterator (STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[vector::const_reverse_iterator (STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[vector::difference_type (STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[vector::generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[vector::generic_reverse_iterator (STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[vector::generic_value (STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[vector::reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[vector::reverse_iterator (STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[vector::size_type (STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)|Заменяет все элементы.|  
|[vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)|Обращается к элементу в указанной позиции.|  
|[vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)|Обращается к последнему элементу.|  
|[vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[vector::capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|Показывает размер хранилища, выделенного для контейнера.|  
|[vector::clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)|Удаляет все элементы.|  
|[vector::empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[vector::front (STL/CLR)](../dotnet/vector-front-stl-clr.md)|Обращается к первому элементу.|  
|[vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)|Добавляет элементы в заданной позиции.|  
|[vector::pop_back (STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|Удаляет последний элемент.|  
|[vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[vector::rend (STL/CLR)](../dotnet/vector-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|Обеспечивает минимальное рост емкости для контейнера.|  
|[vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)|Изменяет количество элементов.|  
|[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[vector::swap (STL/CLR)](../dotnet/vector-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[vector::to_array (STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[vector::vector (STL/CLR)](../dotnet/vector-vector-stl-clr.md)|Создает объект контейнера.|  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|Обращается к последнему элементу.|  
|[vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|Обращается к первому элементу.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[vector::operator (STL/CLR)](../dotnet/vector-operator-stl-clr.md)|Обращается к элементу в указанной позиции.|  
|[operator!= (vector) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|Определяет, если `vector` объект не равен другому `vector` объекта.|  
|[operator< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|Определяет, если `vector` объект меньше другого `vector` объекта.|  
|[operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Определяет, если `vector` объекта меньше или равно другому `vector` объекта.|  
|[operator== (vector) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|Определяет, если `vector` объект равен другому `vector` объекта.|  
|[operator> (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|Определяет, если `vector` объект больше другого `vector` объекта.|  
|[operator>= (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Определяет, если `vector` объекта больше или равно другому `vector` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Ведение упорядоченная группа типизированных элементов.|  
|IVector < значение\>|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через хранимые массива `Value` элементы, которые увеличивается по требованию. Увеличение размера происходит таким образом, что добавление нового элемента обходится амортизацию константой времени. Другими словами затраты на добавление элементов в конце не увеличивается, в среднем, как длина больше возвращает управляемой последовательности. Таким образом, вектор является хорошим кандидатом для базового контейнера для шаблона класса [стека (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Объект `vector` итераторами произвольного доступа поддерживает, т. е. можно ссылаться на элемент, непосредственно заданным его порядкового номера, начиная с нуля для первого элемента (на передней панели), для `size() - 1` для последнего элемента (назад). Это также означает, что вектор является хорошим кандидатом для базового контейнера для шаблона класса [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Итератор вектор сохраняет дескриптор объекта его связанного вектор, а также смещение элемента, на которую он обозначает. Вы можете использовать итераторы только с свои объекты связанного контейнера. Смещение элемента вектора является таким же, как его положение.  
  
 Вставка или удаление элементов можно изменить значение элемента, сохраняются в заданной позиции, поэтому можно также изменить значение, обозначенное итератор. (Контейнер может потребоваться копировать элементы вверх или вниз для создания отверстия перед вставкой или применить после очистки.) Тем не менее, итератор вектор действителен до тех пор, пока его смещение находится в диапазоне `[0, size()]`. Кроме того, остается dereferencable допустимым итератором, его можно использовать для доступа или изменить значение элемента, он обозначает--до тех пор, пока его смещение не равно `size()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Обратите внимание, что контейнер дескрипторов уничтожит его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/vector >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)