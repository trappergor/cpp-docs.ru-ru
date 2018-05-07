---
title: hash_multiset (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_multiset class [STL/CLR]
- <hash_set> header [STL/CLR]
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 819dd9835f173c15b23831e32d6c3a207a3d07c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultiset-stlclr"></a>hash_multiset (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с двунаправленный доступ. Используйте контейнер `hash_multiset` для управления последовательностью элементов хэш-таблицы, каждая запись в таблице хранения двунаправленный связанный список узлов и каждый узел хранения одного элемента. Значение каждого элемента используется в качестве ключа для упорядочения последовательности.  
  
 В следующем описании `GValue` совпадает со значением `GKey`, который в свою очередь является таким же, как `Key` Если последний является типом ссылки, в этом случае он является `Key^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Key>  
    ref class hash_multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Ключ  
 Тип ключевым компонентом любого элемента в управляемой последовательности.  
  
## <a name="members"></a>Члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|[hash_multiset::const_iterator (STL/CLR)](../dotnet/hash-multiset-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[hash_multiset::const_reference (STL/CLR)](../dotnet/hash-multiset-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[hash_multiset::const_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[hash_multiset::difference_type (STL/CLR)](../dotnet/hash-multiset-difference-type-stl-clr.md)|Тип расстояния между двумя элементами (возможно, со знаком).|  
|[hash_multiset::generic_container (STL/CLR)](../dotnet/hash-multiset-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[hash_multiset::generic_iterator (STL/CLR)](../dotnet/hash-multiset-generic-iterator-stl-clr.md)|Тип итератора для универсальный интерфейс для контейнера.|  
|[hash_multiset::generic_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
|[hash_multiset::generic_value (STL/CLR)](../dotnet/hash-multiset-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[hash_multiset::hasher (STL/CLR)](../dotnet/hash-multiset-hasher-stl-clr.md)|Делегат хэширования для ключа.|  
|[hash_multiset::iterator (STL/CLR)](../dotnet/hash-multiset-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[hash_multiset::key_compare (STL/CLR)](../dotnet/hash-multiset-key-compare-stl-clr.md)|Делегат упорядочения для двух ключей.|  
|[hash_multiset::key_type (STL/CLR)](../dotnet/hash-multiset-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[hash_multiset::reference (STL/CLR)](../dotnet/hash-multiset-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[hash_multiset::reverse_iterator (STL/CLR)](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)|Тип обратного итератора для управляемой последовательности.|  
|[hash_multiset::size_type (STL/CLR)](../dotnet/hash-multiset-size-type-stl-clr.md)|Тип расстояния (неотрицательным) между двумя элементами.|  
|[hash_multiset::value_compare (STL/CLR)](../dotnet/hash-multiset-value-compare-stl-clr.md)|Делегат упорядочения для значения двух элементов.|  
|[hash_multiset::value_type (STL/CLR)](../dotnet/hash-multiset-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[hash_multiset::begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[hash_multiset::bucket_count (STL/CLR)](../dotnet/hash-multiset-bucket-count-stl-clr.md)|Подсчитывает количество сегментов.|  
|[hash_multiset::clear (STL/CLR)](../dotnet/hash-multiset-clear-stl-clr.md)|Удаляет все элементы.|  
|[hash_multiset::count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)|Подсчитывает число элементов, соответствующих заданному ключу.|  
|[hash_multiset::empty (STL/CLR)](../dotnet/hash-multiset-empty-stl-clr.md)|Проверяет отсутствие элементов.|  
|[hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[hash_multiset::erase (STL/CLR)](../dotnet/hash-multiset-erase-stl-clr.md)|Удаляет элементы в указанных позициях.|  
|[hash_multiset::find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[hash_multiset::hash_delegate (STL/CLR)](../dotnet/hash-multiset-hash-delegate-stl-clr.md)|Копирует делегат хэширования для ключа.|  
|[hash_multiset::hash_multiset (STL/CLR)](../dotnet/hash-multiset-hash-multiset-stl-clr.md)|Создает объект контейнера.|  
|[hash_multiset::insert (STL/CLR)](../dotnet/hash-multiset-insert-stl-clr.md)|Добавляет элементы.|  
|[hash_multiset::key_comp (STL/CLR)](../dotnet/hash-multiset-key-comp-stl-clr.md)|Копирует делегат упорядочения для двух ключей.|  
|[hash_multiset::load_factor (STL/CLR)](../dotnet/hash-multiset-load-factor-stl-clr.md)|Подсчитывает среднее число элементов в блоке.|  
|[hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)|Начало находит диапазон, соответствующий указанному ключу.|  
|[hash_multiset::make_value (STL/CLR)](../dotnet/hash-multiset-make-value-stl-clr.md)|Создает объект значения.|  
|[hash_multiset::max_load_factor (STL/CLR)](../dotnet/hash-multiset-max-load-factor-stl-clr.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[hash_multiset::rbegin (STL/CLR)](../dotnet/hash-multiset-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[hash_multiset::rehash (STL/CLR)](../dotnet/hash-multiset-rehash-stl-clr.md)|Повторно создает хэш-таблицу.|  
|[hash_multiset::rend (STL/CLR)](../dotnet/hash-multiset-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[hash_multiset::swap (STL/CLR)](../dotnet/hash-multiset-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[hash_multiset::to_array (STL/CLR)](../dotnet/hash-multiset-to-array-stl-clr.md)|Копирует управляемой последовательности в новый массив.|  
|[hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)|Конец находит диапазон, соответствующий указанному ключу.|  
|[hash_multiset::value_comp (STL/CLR)](../dotnet/hash-multiset-value-comp-stl-clr.md)|Копирует делегат упорядочения для значения двух элементов.|  
  
|Operator|Описание|  
|--------------|-----------------|  
|[hash_multiset::operator= (STL/CLR)](../dotnet/hash-multiset-operator-assign-stl-clr.md)|Заменяет управляемую последовательность.|  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|IHash\<ключ, значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для последовательность, в которой он управляет, как отдельные узлы в двунаправленного связанного списка. Для ускорения доступа, объект также хранит переменной длины массива указателей в списке (хэш-таблица), эффективное управление весь список как последовательность подсписков, или контейнеров. Он добавляет элементы в контейнер, который хранит упорядоченную путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы оставшиеся элементы.  
  
 Объект заказов на каждый контейнер им элементы путем вызова хранимых делегат типа [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Объект хранимых делегата можно указать при создании объекта hash_set; Если указан объект делегата не значение по умолчанию является сравнение `operator<=(key_type, key_type)`.  
  
 Доступ к объекту хранимых делегата, путем вызова функции-члена [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Объект делегата необходимо определить соответствующий порядок ключей типа [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `key_comp()(X, Y)` Возвращает значение того же типа Boolean привести при каждом вызове.  
  
 Если `key_comp()(X, Y) && key_comp()(Y, X)` имеет значение true, затем `X` и `Y` говорят, что имеют соответствующий порядок.  
  
 Любое правило порядка сортировки, который ведет себя как `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет порядок eqivalent.  
  
 Обратите внимание, что контейнера обеспечивает только элементы, ключи которых имеют соответствующий порядок (и хэш-значению целое число со знаком) рядом в сегменте. В отличие от шаблона класса [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md), объект класса шаблона `hash_multiset` не требуется, ключи для всех элементов являются уникальными. (Две или более клавиш могут быть соответствующим образом.)  
  
 Объект определяет в каком сегменте должен содержать указанного ключа сортировки, вызвав хранимую делегат типа [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Доступ к этому сохраненному объекту путем вызова функции-члена [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` получить целое значение, которое зависит от значения ключа. Объект хранимых делегата можно указать при создании объекта hash_set; При указании объект делегата отсутствует значение по умолчанию — функция `System::Object::hash_value(key_type)`. Это означает, что для любых ключей `X` и `Y`:  
  
 `hash_delegate()(X)` Возвращает один и тот же целочисленный результат при каждом вызове.  
  
 Если `X` и `Y` имеют соответствующий порядок, затем `hash_delegate()(X)` должна возвращать целочисленный аналогична `hash_delegate()(Y)`.  
  
 Каждый элемент используется как ключ и значение. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента с количеством операций, не зависит от числа элементов в последовательности (постоянное время) — по крайней мере в наиболее вариантов. Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
 Если хэшированных значений не распределяются равномерно, однако можно вырожденных хэш-таблицу. В любых--для хэш-функции, которая всегда возвращает то же значение--поиска, вставки и удаления пропорционально количеству элементов в последовательности (линейное время). Контейнер написана выберите разумного хэш-функции, размер среднего сегмента, а размер хэш таблицы (общее количество сегментов), но можно переопределить любые или все из этих вариантов. Просмотреть, например, функции [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) и [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Hash_multiset поддерживают Двунаправленные итераторы, это означает, что при переходе на соседние элементы, учитывая итератор, указывающий на элемент управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`. Можно уменьшить этот итератор для достижения последнего элемента в управляемой последовательности, при его наличии. Можно увеличивать итератор hash_multiset, чтобы достичь головного узла, и затем сравнивает равно `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент hash_multiset, непосредственно заданным его порядкового номера--, требующий итератора произвольного доступа.  
  
 Итератор hash_multiset сохраняет дескриптор к узлу связанный hash_multiset, который в свою очередь хранит дескриптор связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор hash_multiset остается допустимым до тех пор, пока его связанный hash_multiset узел связан с некоторыми hash_multiset. Кроме того, допустимым итератором dereferencable — используется для доступа или изменить значение элемента, он обозначает--до тех пор, пока не равно `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [мультинабор (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [мультинабор (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)