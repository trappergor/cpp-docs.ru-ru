---
title: "hash_map (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map
dev_langs: C++
helpviewer_keywords:
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
- hash_map class [STL/CLR]
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aae2ca596a04a6502fc50bc7ac2cb6344463f739
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hashmap-stlclr"></a>hash_map (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с двунаправленный доступ. Используйте контейнер `hash_map` для управления последовательностью элементов хэш-таблицы, каждая запись в таблице хранения двунаправленный связанный список узлов и каждый узел хранения одного элемента. Элемент состоит из ключа, для упорядочения последовательности и сопоставленные значение, которое происходит расстояния.  
  
 В следующем описании `GValue` совпадает со значением:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 где:  
  
 `GKey`совпадает со значением `Key` Если последний является типом ссылки, в этом случае он является`Key^`  
  
 `GMapped`совпадает со значением `Mapped` Если последний является типом ссылки, в этом случае он является`Mapped^`  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Ключ  
 Тип ключевым компонентом любого элемента в управляемой последовательности.  
  
 Сопоставить  
 Тип дополнительного компонента для элемента в управляемой последовательности.  
  
## <a name="members"></a>Члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[hash_map::const_iterator (STL/CLR)](../dotnet/hash-map-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[hash_map::const_reference (STL/CLR)](../dotnet/hash-map-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[hash_map::const_reverse_iterator (STL/CLR)](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[hash_map::difference_type (STL/CLR)](../dotnet/hash-map-difference-type-stl-clr.md)|Тип расстояния между двумя элементами (возможно, со знаком).|  
|[hash_map::generic_container (STL/CLR)](../dotnet/hash-map-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[hash_map::generic_iterator (STL/CLR)](../dotnet/hash-map-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[hash_map::generic_reverse_iterator (STL/CLR)](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[hash_map::generic_value (STL/CLR)](../dotnet/hash-map-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[hash_map::hasher (STL/CLR)](../dotnet/hash-map-hasher-stl-clr.md)|Делегат хэширования для ключа.|  
|[hash_map::iterator (STL/CLR)](../dotnet/hash-map-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[hash_map::key_compare (STL/CLR)](../dotnet/hash-map-key-compare-stl-clr.md)|Делегат упорядочения для двух ключей.|  
|[hash_map::key_type (STL/CLR)](../dotnet/hash-map-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[hash_map::mapped_type (STL/CLR)](../dotnet/hash-map-mapped-type-stl-clr.md)|Тип сопоставленного значения, связанного с каждым ключом.|  
|[hash_map::reference (STL/CLR)](../dotnet/hash-map-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[hash_map::reverse_iterator (STL/CLR)](../dotnet/hash-map-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[hash_map::size_type (STL/CLR)](../dotnet/hash-map-size-type-stl-clr.md)|Тип расстояния (неотрицательным) между двумя элементами.|  
|[hash_map::value_compare (STL/CLR)](../dotnet/hash-map-value-compare-stl-clr.md)|Делегат упорядочения для значения двух элементов.|  
|[hash_map::value_type (STL/CLR)](../dotnet/hash-map-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[hash_map::begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[hash_map::bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)|Подсчитывает количество сегментов.|  
|[hash_map::clear (STL/CLR)](../dotnet/hash-map-clear-stl-clr.md)|Удаляет все элементы.|  
|[hash_map::count (STL/CLR)](../dotnet/hash-map-count-stl-clr.md)|Подсчитывает число элементов, соответствующих заданному ключу.|  
|[hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[hash_map::equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[hash_map::erase (STL/CLR)](../dotnet/hash-map-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[hash_map::find (STL/CLR)](../dotnet/hash-map-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[hash_map::hash_delegate (STL/CLR)](../dotnet/hash-map-hash-delegate-stl-clr.md)|Копирует делегат хэширования для ключа.|  
|[hash_map::hash_map (STL/CLR)](../dotnet/hash-map-hash-map-stl-clr.md)|Создает объект контейнера.|  
|[hash_map::insert (STL/CLR)](../dotnet/hash-map-insert-stl-clr.md)|Добавляет элементы.|  
|[hash_map::key_comp (STL/CLR)](../dotnet/hash-map-key-comp-stl-clr.md)|Копирует делегат упорядочения для двух ключей.|  
|[hash_map::load_factor (STL/CLR)](../dotnet/hash-map-load-factor-stl-clr.md)|Подсчитывает среднее число элементов в блоке.|  
|[hash_map::lower_bound (STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)|Начало находит диапазон, соответствующий указанному ключу.|  
|[hash_map::make_value (STL/CLR)](../dotnet/hash-map-make-value-stl-clr.md)|Создает объект значения.|  
|[hash_map::max_load_factor (STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[hash_map::rbegin (STL/CLR)](../dotnet/hash-map-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[hash_map::rehash (STL/CLR)](../dotnet/hash-map-rehash-stl-clr.md)|Повторно создает хэш-таблицу.|  
|[hash_map::rend (STL/CLR)](../dotnet/hash-map-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[hash_map::size (STL/CLR)](../dotnet/hash-map-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[hash_map::swap (STL/CLR)](../dotnet/hash-map-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[hash_map::to_array (STL/CLR)](../dotnet/hash-map-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[hash_map::upper_bound (STL/CLR)](../dotnet/hash-map-upper-bound-stl-clr.md)|Конец находит диапазон, соответствующий указанному ключу.|  
|[hash_map::value_comp (STL/CLR)](../dotnet/hash-map-value-comp-stl-clr.md)|Копирует делегат упорядочения для значения двух элементов.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[hash_map::operator= (STL/CLR)](../dotnet/hash-map-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
|[hash_map::operator (STL/CLR)](../dotnet/hash-map-operator-stl-clr.md)|Сопоставляет сопоставленных связанное с ним значение ключа.|  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IDictionary%602>|Ведение группы {ключ, значение} пары.|  
|IHash < ключ, значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для последовательность, в которой он управляет, как отдельные узлы в двунаправленного связанного списка. Для ускорения доступа, объект также хранит переменной длины массива указателей в списке (хэш-таблица), эффективное управление весь список как последовательность подсписков, или контейнеров. Он добавляет элементы в контейнер, который хранит упорядоченную путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы оставшиеся элементы.  
  
 Объект заказов на каждый контейнер им элементы путем вызова хранимых делегат типа [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Объект хранимых делегата можно указать при создании объекта hash_set; Если указан объект делегата не значение по умолчанию является сравнение `operator<=(key_type, key_type)`.  
  
 Доступ к объекту хранимых делегата, путем вызова функции-члена [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Объект делегата необходимо определить соответствующий порядок ключей типа [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `key_comp()(X, Y)`Возвращает значение того же типа Boolean привести при каждом вызове.  
  
 Если `key_comp()(X, Y) && key_comp()(Y, X)` имеет значение true, затем `X` и `Y` говорят, что имеют соответствующий порядок.  
  
 Любое правило порядка сортировки, который ведет себя как `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет порядок eqivalent.  
  
 Обратите внимание, что контейнера обеспечивает только элементы, ключи которых имеют соответствующий порядок (и хэш-значению целое число со знаком) рядом в сегменте. В отличие от шаблона класса [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md), объект класса шаблона `hash_map` гарантирует уникальность ключей для всех элементов. (Ключи не двух имеют соответствующий порядок).  
  
 Объект определяет в каком сегменте должен содержать указанного ключа сортировки, вызвав хранимую делегат типа [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Доступ к этому сохраненному объекту путем вызова функции-члена [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` получить целое значение, которое зависит от значения ключа. Объект хранимых делегата можно указать при создании объекта hash_set; При указании объект делегата отсутствует значение по умолчанию — функция `System::Object::hash_value(key_type)`. Это означает, что для любых ключей `X` и `Y`:  
  
 `hash_delegate()(X)`Возвращает один и тот же целочисленный результат при каждом вызове.  
  
 Если `X` и `Y` имеют соответствующий порядок, затем `hash_delegate()(X)` должна возвращать целочисленный аналогична `hash_delegate()(Y)`.  
  
 Каждый элемент содержит отдельный ключ и сопоставленного значения. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента с количеством операций, не зависит от числа элементов в последовательности (постоянное время) — по крайней мере в наиболее вариантов. Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
 Если хэшированных значений не распределяются равномерно, однако можно вырожденных хэш-таблицу. В любых--для хэш-функции, которая всегда возвращает то же значение--поиска, вставки и удаления пропорционально количеству элементов в последовательности (линейное время). Контейнер написана выберите разумного хэш-функции, размер среднего сегмента, а размер хэш таблицы (общее количество сегментов), но можно переопределить любые или все из этих вариантов. Просмотреть, например, функции [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) и [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Hash_map поддерживают Двунаправленные итераторы, это означает, что при переходе на соседние элементы, учитывая итератор, указывающий на элемент управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`. Можно уменьшить этот итератор для достижения последнего элемента в управляемой последовательности, при его наличии. Можно увеличивать итератор hash_map, чтобы достичь головного узла, и затем сравнивает равно `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент hash_map, непосредственно заданным его порядкового номера--, требующий итератора произвольного доступа.  
  
 Итератор hash_map сохраняет дескриптор к узлу связанный hash_map, который в свою очередь хранит дескриптор связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор hash_map остается допустимым до тех пор, пока его связанный hash_map узел связан с некоторыми hash_map. Кроме того, допустимым итератором dereferencable — используется для доступа или изменить значение элемента, он обозначает--до тех пор, пока не равно `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [несколько карт (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [мультинабор (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)