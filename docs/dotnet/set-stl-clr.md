---
title: "Задайте (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set
dev_langs: C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9624f08c54629657e7f52c2c688d2083aa557a56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="set-stlclr"></a>set (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с двунаправленный доступ. Используйте контейнер `set` для управления последовательностью элементов как упорядоченный (почти) сбалансированного дерева узлов, каждый хранения одного элемента.  
  
 В следующем описании `GValue` совпадает со значением `GKey`, который в свою очередь является таким же, как `Key` Если последний является типом ссылки, в этом случае он является `Key^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Key>  
    ref class set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Ключ  
 Тип ключевым компонентом любого элемента в управляемой последовательности.  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[set::const_iterator (STL/CLR)](../dotnet/set-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[set::const_reverse_iterator (STL/CLR)](../dotnet/set-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[set::difference_type (STL/CLR)](../dotnet/set-difference-type-stl-clr.md)|Тип расстояния между двумя элементами (возможно, со знаком).|  
|[set::generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[set::generic_iterator (STL/CLR)](../dotnet/set-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[set::generic_reverse_iterator (STL/CLR)](../dotnet/set-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[set::generic_value (STL/CLR)](../dotnet/set-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[set::iterator (STL/CLR)](../dotnet/set-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)|Делегат упорядочения для двух ключей.|  
|[set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[set::reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[set::reverse_iterator (STL/CLR)](../dotnet/set-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[set::size_type (STL/CLR)](../dotnet/set-size-type-stl-clr.md)|Тип расстояния (неотрицательным) между двумя элементами.|  
|[set::value_compare (STL/CLR)](../dotnet/set-value-compare-stl-clr.md)|Делегат упорядочения для значения двух элементов.|  
|[set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[set::clear (STL/CLR)](../dotnet/set-clear-stl-clr.md)|Удаляет все элементы.|  
|[set::count (STL/CLR)](../dotnet/set-count-stl-clr.md)|Подсчитывает число элементов, соответствующих заданному ключу.|  
|[set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[set::find (STL/CLR)](../dotnet/set-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[set::insert (STL/CLR)](../dotnet/set-insert-stl-clr.md)|Добавляет элементы.|  
|[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)|Копирует делегат упорядочения для двух ключей.|  
|[set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)|Начало находит диапазон, соответствующий указанному ключу.|  
|[set::make_value (STL/CLR)](../dotnet/set-make-value-stl-clr.md)|Создает объект значения.|  
|[set::rbegin (STL/CLR)](../dotnet/set-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[set::set (STL/CLR)](../dotnet/set-set-stl-clr.md)|Создает объект контейнера.|  
|[set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[set::swap (STL/CLR)](../dotnet/set-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[set::to_array (STL/CLR)](../dotnet/set-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)|Конец находит диапазон, соответствующий указанному ключу.|  
|[set::value_comp (STL/CLR)](../dotnet/set-value-comp-stl-clr.md)|Копирует делегат упорядочения для значения двух элементов.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[set::operator= (STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[operator!= (set) (STL/CLR)](../dotnet/operator-inequality-set-stl-clr.md)|Определяет, если `set` объект не равен другому `set` объекта.|  
|[operator< (set) (STL/CLR)](../dotnet/operator-less-than-set-stl-clr.md)|Определяет, если `set` объект меньше другого `set` объекта.|  
|[operator<= (set) (STL/CLR)](../dotnet/operator-less-or-equal-set-stl-clr.md)|Определяет, если `set` объекта меньше или равно другому `set` объекта.|  
|[operator== (set) (STL/CLR)](../dotnet/operator-equality-set-stl-clr.md)|Определяет, если `set` объект равен другому `set` объекта.|  
|[operator> (set) (STL/CLR)](../dotnet/operator-greater-than-set-stl-clr.md)|Определяет, если `set` объект больше другого `set` объекта.|  
|[operator>= (set) (STL/CLR)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|Определяет, если `set` объекта больше или равно другому `set` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|ITree\<ключ, значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для последовательность, в которой он управляет, как отдельные узлы. Он добавляет элементы в (почти) дерева, которое сохраняет упорядоченную путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы оставшиеся элементы.  
  
 Объект Упорядочивает управляемую последовательность путем вызова хранимых делегат типа [set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Объект хранимых делегата можно указать при создании набора. Если указан объект делегата не значение по умолчанию является сравнение `operator<(key_type, key_type)`. Доступ к этому сохраненному объекту путем вызова функции-члена [set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.  
  
 Объект делегата должен применить строгого слабое упорядочение на ключах типа [set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `key_comp()(X, Y)`Возвращает значение того же типа Boolean привести при каждом вызове.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `key_comp()(Y, X)` должен иметь значение false.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `X` называется располагаются перед `Y`.  
  
 Если `!key_comp()(X, Y) && !key_comp()(Y, X)` имеет значение true, затем `X` и `Y` говорят, что имеют соответствующий порядок.  
  
 Для любого элемента `X` , предшествующий `Y` в управляемой последовательности `key_comp()(Y, X)` имеет значение false. (По умолчанию объекта делегата, ключи никогда не уменьшаются.) В отличие от шаблона класса [задать](../dotnet/set-stl-clr.md), объект класса шаблона `set` не требуется, ключи для всех элементов являются уникальными. (Две или более клавиш могут быть соответствующим образом.)  
  
 Каждый элемент служит ли и значение. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента с количеством операций пропорционально логарифму числа элементов в последовательности (логарифмическом времени). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
 Набор поддерживает Двунаправленные итераторы, это означает, что при переходе на соседние элементы, учитывая итератор, указывающий на элемент управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Можно уменьшить этот итератор для достижения последнего элемента в управляемой последовательности, при его наличии. Можно увеличивать итератор набор, чтобы достичь головного узла, и затем сравнивает равно `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент набора, непосредственно заданным его порядкового номера--, требующий итератора произвольного доступа.  
  
 Итератор набор сохраняет дескриптор к узлу связан набор, который в свою очередь хранит дескриптор связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор набор остается допустимым до тех пор, пока его узел связан набор связан с некоторым набором. Кроме того, допустимым итератором dereferencable — используется для доступа или изменить значение элемента, он обозначает--до тех пор, пока не равно `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)