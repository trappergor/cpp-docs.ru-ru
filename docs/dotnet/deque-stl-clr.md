---
title: "deque (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9bd847b2641e6670a91d2edf1eb926aca423ad2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="deque-stlclr"></a>deque (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с произвольного доступа. Используйте контейнер `deque` для управления последовательность элементов, выглядит как непрерывный блок памяти, но который можете увеличить или уменьшить конце без необходимости копировать все оставшиеся элементы. Поэтому он может реализовывать эффективно `double-ended queue`. (Поэтому имя.)  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 GValue  
 Универсальный тип элемента в управляемой последовательности.  
  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## <a name="members"></a>Члены  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[deque::const_reference (STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[deque::const_reverse_iterator (STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[deque::difference_type (STL/CLR)](../dotnet/deque-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[deque::generic_iterator (STL/CLR)](../dotnet/deque-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[deque::generic_reverse_iterator (STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[deque::generic_value (STL/CLR)](../dotnet/deque-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[deque::iterator (STL/CLR)](../dotnet/deque-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[deque::reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[deque::reverse_iterator (STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[deque::size_type (STL/CLR)](../dotnet/deque-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[deque::value_type (STL/CLR)](../dotnet/deque-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)|Заменяет все элементы.|  
|[deque::at (STL/CLR)](../dotnet/deque-at-stl-clr.md)|Обращается к элементу в указанной позиции.|  
|[deque::back (STL/CLR)](../dotnet/deque-back-stl-clr.md)|Обращается к последнему элементу.|  
|[deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[deque::clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)|Удаляет все элементы.|  
|[deque::deque (STL/CLR)](../dotnet/deque-deque-stl-clr.md)|Создает объект контейнера.|  
|[deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[deque::front (STL/CLR)](../dotnet/deque-front-stl-clr.md)|Обращается к первому элементу.|  
|[deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)|Добавляет элементы в заданной позиции.|  
|[deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)|Удаляет последний элемент.|  
|[deque::pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)|Удаляет первый элемент.|  
|[deque::push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)|Добавляет новый первый элемент.|  
|[deque::rbegin (STL/CLR)](../dotnet/deque-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[deque::rend (STL/CLR)](../dotnet/deque-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[deque::resize (STL/CLR)](../dotnet/deque-resize-stl-clr.md)|Изменяет количество элементов.|  
|[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[deque::swap (STL/CLR)](../dotnet/deque-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[deque::to_array (STL/CLR)](../dotnet/deque-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
  
|Свойство.|Описание:|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](../dotnet/deque-back-item-stl-clr.md)|Обращается к последнему элементу.|  
|[deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)|Обращается к первому элементу.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)|Определяет, если два `deque` объекты не равны.|  
|[deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)|Обращается к элементу в указанной позиции.|  
|[operator< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)|Определяет, если `deque` объект меньше другого `deque` объекта.|  
|[operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Определяет, если `deque` объекта меньше или равно другому `deque` объекта.|  
|[operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)|Заменяет управляемую последовательность.|  
|[operator== (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)|Определяет, если `deque` объект равен другому `deque` объекта.|  
|[operator> (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)|Определяет, если `deque` объект больше другого `deque` объекта.|  
|[operator>= (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Определяет, если `deque` объекта больше или равно другому `deque` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Ведение упорядоченная группа типизированных элементов.|  
|IDeque < значение\>|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через хранимые массива дескрипторов, которые определяют блоки `Value` элементов. Массив увеличивается по требованию. Увеличение размера происходит таким образом, добавляя или добавления нового элемента обходится в константном времени, что изменяются элементов не осталось. Можно также удалить элемент на концах в константном времени и без нарушения работы оставшиеся элементы. Таким образом, deque является хорошим кандидатом для базового контейнера для шаблона класса [очереди (STL/CLR)](../dotnet/queue-stl-clr.md) или класс шаблона [стека (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Объект `deque` объект поддерживает итераторами произвольного доступа, это означает, что можно ссылаться на элемент, непосредственно заданным его порядкового номера, начиная с нуля для первого элемента (внешнего) для [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() - 1` для последнего элемента (назад). Это также означает, что deque является хорошим кандидатом для базового контейнера для шаблона класса [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Итератор deque сохраняет дескриптор объекта его связанный deque, а также смещение элемента, на которую он обозначает. Вы можете использовать итераторы только с свои объекты связанного контейнера. Смещение элемента deque — `not` обязательно таким же, как его положение. Первый элемент вставлен имеет смещение ноль, далее добавленный элемент имеет смещение 1, но Далее присоединяемый элемент имеет смещение -1.  
  
 Вставки или удаления элементов на концах не `not` изменить значение на элемент, хранящийся в любой допустимый уровень защиты. Вставка или удаление внутренний элемент, однако `can` изменить значение элемента, сохраняются на данный сдвиг, можно также изменить значение, обозначенное итератор. (Контейнер может потребоваться копировать элементы вверх или вниз для создания отверстия перед вставкой или применить после очистки.) Тем не менее итератор deque остается допустимым до тех пор, пока его смещение определяет допустимый элемент. Кроме того, остается dereferencable допустимым итератором, его можно использовать для доступа или изменить значение элемента, он обозначает — при условии, что его смещение не равно смещение для итератора, возвращаемого методом `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)