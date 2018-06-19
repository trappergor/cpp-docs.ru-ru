---
title: Карта (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cda679ed01e5266f0605639df45940d8f17e506d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137794"
---
# <a name="map-stlclr"></a>map (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с двунаправленный доступ. Используйте контейнер `map` для управления последовательностью элементов как упорядоченный (почти) сбалансированного дерева узлов, каждый хранения одного элемента. Элемент состоит из ключа, для упорядочения последовательности и сопоставленные значение, которое происходит расстояния.  
  
 В следующем описании `GValue` совпадает со значением:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Здесь:  
  
 `GKey` совпадает со значением `Key` Если последний является типом ссылки, в этом случае он является `Key^`  
  
 `GMapped` совпадает со значением `Mapped` Если последний является типом ссылки, в этом случае он является `Mapped^`  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Ключ  
 Тип ключевым компонентом любого элемента в управляемой последовательности.  
  
 Сопоставить  
 Тип дополнительного компонента для элемента в управляемой последовательности.  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[map::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[map::const_reverse_iterator (STL/CLR)](../dotnet/map-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[map::difference_type (STL/CLR)](../dotnet/map-difference-type-stl-clr.md)|Тип расстояния между двумя элементами (возможно, со знаком).|  
|[map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[map::generic_value (STL/CLR)](../dotnet/map-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)|Делегат упорядочения для двух ключей.|  
|[map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[map::mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)|Тип сопоставленного значения, связанного с каждым ключом.|  
|[map::reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[map::reverse_iterator (STL/CLR)](../dotnet/map-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[map::size_type (STL/CLR)](../dotnet/map-size-type-stl-clr.md)|Тип расстояния (неотрицательным) между двумя элементами.|  
|[map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)|Делегат упорядочения для значения двух элементов.|  
|[map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[map::clear (STL/CLR)](../dotnet/map-clear-stl-clr.md)|Удаляет все элементы.|  
|[map::count (STL/CLR)](../dotnet/map-count-stl-clr.md)|Подсчитывает число элементов, соответствующих заданному ключу.|  
|[map::empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[map::find (STL/CLR)](../dotnet/map-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)|Добавляет элементы.|  
|[map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)|Копирует делегат упорядочения для двух ключей.|  
|[map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)|Начало находит диапазон, соответствующий указанному ключу.|  
|[map::make_value (STL/CLR)](../dotnet/map-make-value-stl-clr.md)|Создает объект значения.|  
|[map::map (STL/CLR)](../dotnet/map-map-stl-clr.md)|Создает объект контейнера.|  
|[map::rbegin (STL/CLR)](../dotnet/map-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[map::swap (STL/CLR)](../dotnet/map-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[map::to_array (STL/CLR)](../dotnet/map-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)|Конец находит диапазон, соответствующий указанному ключу.|  
|[map::value_comp (STL/CLR)](../dotnet/map-value-comp-stl-clr.md)|Копирует делегат упорядочения для значения двух элементов.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[map::operator= (STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[map::operator (STL/CLR)](../dotnet/map-operator-stl-clr.md)|Сопоставляет сопоставленных связанное с ним значение ключа.|  
|[operator!= (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)|Определяет, если `map` объект не равен другому `map` объекта.|  
|[operator< (map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)|Определяет, если `map` объект меньше другого `map` объекта.|  
|[operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Определяет, если `map` объекта меньше или равно другому `map` объекта.|  
|[operator== (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)|Определяет, если `map` объект равен другому `map` объекта.|  
|[operator> (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)|Определяет, если `map` объект больше другого `map` объекта.|  
|[operator>= (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Определяет, если `map` объекта больше или равно другому `map` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IDictionary%602>|Ведение группы {ключ, значение} пары.|  
|ITree < ключ, значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для последовательность, в которой он управляет, как отдельные узлы. Он добавляет элементы в (почти) дерева, которое сохраняет упорядоченную путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы оставшиеся элементы.  
  
 Объект Упорядочивает управляемую последовательность путем вызова хранимых делегат типа [map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md). Объект хранимых делегата можно указать при создании карты; Если указан объект делегата не значение по умолчанию является сравнение `operator<(key_type, key_type)`. Доступ к этому сохраненному объекту путем вызова функции-члена [map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`.  
  
 Объект делегата должен применить строгого слабое упорядочение на ключах типа [map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `key_comp()(X, Y)` Возвращает значение того же типа Boolean привести при каждом вызове.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `key_comp()(Y, X)` должен иметь значение false.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `X` называется располагаются перед `Y`.  
  
 Если `!key_comp()(X, Y) && !key_comp()(Y, X)` имеет значение true, затем `X` и `Y` говорят, что имеют соответствующий порядок.  
  
 Для любого элемента `X` , предшествующий `Y` в управляемой последовательности `key_comp()(Y, X)` имеет значение false. (По умолчанию объекта делегата, ключи никогда не уменьшаются.) В отличие от шаблона класса [карты](../dotnet/map-stl-clr.md), объект класса шаблона `map` не требуется, ключи для всех элементов являются уникальными. (Две или более клавиш могут быть соответствующим образом.)  
  
 Каждый элемент содержит отдельный ключ и сопоставленного значения. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента с количеством операций пропорционально логарифму числа элементов в последовательности (логарифмическом времени). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
 Карта поддерживает Двунаправленные итераторы, это означает, что при переходе на соседние элементы, учитывая итератор, указывающий на элемент управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Можно уменьшить этот итератор для достижения последнего элемента в управляемой последовательности, при его наличии. Можно увеличивать итератор карты для доступа к головному узлу, и затем сравнивает равно `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент карты, непосредственно заданным его порядкового номера--, требующий итератора произвольного доступа.  
  
 Итератор карты хранит дескриптор его связанный карты узла, который в свою очередь хранит дескриптор связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор карты остается допустимым до тех пор, пока его связанный карты узла связан с некоторыми карты. Кроме того, допустимым итератором dereferencable — используется для доступа или изменить значение элемента, он обозначает--до тех пор, пока не равно `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [карты](../dotnet/map-stl-clr.md)   
 [мультинабор (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)