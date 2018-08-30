---
title: алгоритм (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
- cliext::adjacent_find
- cliext::binary_search
- cliext::copy
- cliext::copy_backward
- cliext::count
- cliext::count_if
- cliext::equal
- cliext::equal_range
- cliext::fill
- cliext::fill_n
- cliext::find
- cliext::find_end
- cliext::find_first_of
- cliext::find_if
- cliext::for_each
- cliext::generate
- cliext::generate_n
- cliext::includes
- cliext::inplace_merge
- cliext::iter_swap
- cliext::lexicographical_compare
- cliext::lower_bound
- cliext::make_heap
- cliext::max
- cliext::max_element
- cliext::merge
- cliext::min
- cliext::min_element
- cliext::mismatch
- cliext::next_permutation
- cliext::nth_element
- cliext::partial_sort
- cliext::partial_sort_copy
- cliext::partition
- cliext::pop_heap
- cliext::prev_permutation
- cliext::push_heap
- cliext::random_shuffle
- cliext::remove
- cliext::remove_copy
- cliext::remove_copy_if
- cliext::remove_if
- cliext::replace
- cliext::replace_copy
- cliext::replace_copy_if
- cliext::replace_if
- cliext::reverse
- cliext::reverse_copy
- cliext::rotate
- cliext::rotate_copy
- cliext::search
- cliext::search_n
- cliext::set_difference
- cliext::set_intersection
- cliext::set_symmetric_difference
- cliext::set_union
- cliext::sort
- cliext::sort_heap
- cliext::stable_partition
- cliext::stable_sort
- cliext::swap
- cliext::swap_ranges
- cliext::transform
- cliext::unique
- cliext::unique_copy
- cliext::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
- adjacent_find function
- binary_search function [STL/CLR]
- copy function [STL/CLR]
- copy_backward function [STL/CLR]
- count function [STL/CLR]
- count_if function [STL/CLR]
- equal function [STL/CLR]
- equal_range function [STL/CLR]
- fill function
- fill_n function
- find function [STL/CLR]
- find_end function [STL/CLR]
- find_first_of function [STL/CLR]
- find_if function [STL/CLR]
- for_each function [STL/CLR]
- generate function [STL/CLR]
- generate_n function [STL/CLR]
- includes function [STL/CLR]
- inplace_merge function [STL/CLR]
- iter_swap function [STL/CLR]
- lexicographical_compare function [STL/CLR]
- lower_bound function [STL/CLR]
- make_heap function [STL/CLR]
- max function [STL/CLR]
- max_element function [STL/CLR]
- merge function [STL/CLR]
- min function [STL/CLR]
- min_element function [STL/CLR]
- mismatch function [STL/CLR]
- next_permutation function [STL/CLR]
- nth_element function [STL/CLR]
- partial_sort function [STL/CLR]
- partial_sort_copy function [STL/CLR]
- partition function [STL/CLR]
- pop_heap function [STL/CLR]
- prev_permutation function [STL/CLR]
- push_heap function [STL/CLR]
- random_shuffle function [STL/CLR]
- remove function [STL/CLR]
- remove_copy function [STL/CLR]
- remove_copy_if function [STL/CLR]
- remove_if function [STL/CLR]
- replace function [STL/CLR]
- replace_copy function [STL/CLR]
- replace_copy_if function [STL/CLR]
- replace_if function [STL/CLR]
- reverse function [STL/CLR]
- reverse_copy function [STL/CLR]
- rotate function [STL/CLR]
- rotate_copy function [STL/CLR]
- search function [STL/CLR]
- search_n function [STL/CLR]
- set_difference function [STL/CLR]
- set_intersection function [STL/CLR]
- set_symmetric_difference function [STL/CLR]
- set_union function [STL/CLR]
- sort function [STL/CLR]
- sort_heap function [STL/CLR]
- stable_partition function [STL/CLR]
- stable_sort function [STL/CLR]
- swap function [STL/CLR]
- swap_ranges function [STL/CLR]
- transform function [STL/CLR]
- unique function [STL/CLR]
- unique_copy function [STL/CLR]
- upper_bound function [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 93bbc86e32d75e81c342a0a0a71b823b87df62b0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196769"
---
# <a name="algorithm-stlclr"></a>algorithm (STL/CLR)
Определяет шаблонные функции контейнера STL/CLR, которые выполняют алгоритмы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <cliext/algorithm>  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/algorithm >  
  
 **Пространство имен:** cliext  
    
## <a name="declarations"></a>Объявления  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[adjacent_find (STL/CLR)](#adjacent_find)|Выполняет поиск двух соседних элементов, которые равны.|  
|[binary_search (STL/CLR)](#binary_search)|Проверяет, является ли заданное значение содержит упорядоченную последовательность.|  
|[copy (STL/CLR)](#copy)|Копирует значения из исходного диапазона диапазону назначения, выполняя итерации в прямом направлении.|  
|[copy_backward (STL/CLR)](#copy_backward)|Копирует значения из исходного диапазона диапазону назначения, выполняя итерации в обратном направлении.|  
|[count (STL/CLR)](#count)|Возвращает количество элементов в диапазоне, значения которых соответствуют заданному значению.|  
|[count_if (STL/CLR)](#count_if)|Возвращает количество элементов в диапазоне, значения которых соответствуют заданному условию.|  
|[equal (STL/CLR)](#equal)|Сравнивает два диапазона поэлементно.|  
|[equal_range (STL/CLR)](#equal_range)|Выполняет упорядоченная последовательность значений и возвращает две позиции, которые разделяют последовательность значений, которые равны указанному элементу.|  
|[fill (STL/CLR)](#fill)|Присваивает одно и то же новое значение каждому элементу в заданном диапазоне.|  
|[fill_n (STL/CLR)](#fill_n)|Назначает новое значение указанному количеству элементов в диапазоне, начиная с определенного элемента.|  
|[find (STL/CLR)](#find)|Возвращает позицию первого вхождения указанного значения.|  
|[find_end (STL/CLR)](#find_end)|Возвращает последней подпоследовательности в диапазоне, идентичный указанной последовательности.|  
|[find_first_of (STL/CLR)](#find_first_of)|Выполняет поиск в диапазоне для первого вхождения любого из заданного диапазона элементов.|  
|[find_if (STL/CLR)](#find_if)|Возвращает позицию первого элемента в последовательности значений, где элемент удовлетворяет заданному условию.|  
|[for_each (STL/CLR)](#for_each)|Применяет заданный объект функции к каждому элементу в последовательности значений и возвращает объект-функцию.|  
|[generate (STL/CLR)](#generate)|Присваивает значения, создаваемые объектом функции к каждому элементу в последовательности значений.|  
|[generate_n (STL/CLR)](#generate_n)|Присваивает значения, создаваемые объектом функции, чтобы указанное число элементов.|  
|[includes (STL/CLR)](#includes)|Проверяет, является ли один упорядоченный диапазон содержит все элементы в втором отсортированном диапазоне.|  
|[inplace_merge (STL/CLR)](#inplace_merge)|Объединяет элементы из двух последовательных упорядоченных диапазонов в один упорядоченный диапазон.|  
|[iter_swap (STL/CLR)](#iter_swap)|Меняет местами два значения, указанные парой определенных итераторов.|  
|[lexicographical_compare (STL/CLR)](#lexicographical_compare)|Сравнивает две последовательности поэлементно, определяющий, какие последовательности, равно меньшему из двух.|  
|[lower_bound (STL/CLR)](#lower_bound)|Находит позицию первого элемента в упорядоченный набор значений, имеющим значение больше или равно указанному значению.|  
|[make_heap (STL/CLR)](#make_heap)|Преобразует элементы из указанного диапазона в кучу, где первый элемент в куче — самое большое.|  
|[max (STL/CLR)](#max))|Сравнивает два объекта и возвращает больший из двух.|  
|[max_element (STL/CLR)](#max_element)|Находит наибольший элемент в указанной последовательности значений.|  
|[Merge (STL/CLR)](#merge))|Объединяет все элементы из двух упорядоченных исходных диапазонов в один упорядоченный диапазон назначения.|  
|[min (STL/CLR)](#min)|Сравнивает два объекта и возвращает меньшее из двух.|  
|[min_element (STL/CLR)](#min_element)|Находит наименьший элемент в указанной последовательности значений.|  
|[mismatch (STL/CLR)](#mismatch)|Сравнивает два диапазона поэлементно и возвращает первую позицию, где наблюдается разница.|  
|[next_permutation (STL/CLR)](#next_permutation)|Изменяет порядок элементов в диапазоне, чтобы исходный порядок был заменен лексикографически следующая перестановка больше, если он существует.|  
|[nth_element (STL/CLR)](#nth_element)|Разделяет последовательность элементов, правильно находя `n`-й элемент последовательности, чтобы все элементы перед ним были меньше или равно ему, а все элементы, следующие за ней — больше или равны ему.|  
|[partial_sort (STL/CLR)](#partial_sort)|Упорядочивает указанное число меньших элементов в диапазоне в не нисходящем порядке.|  
|[partial_sort_copy (STL/CLR)](#partial_sort_copy)|Копирует элементы из исходного диапазона в диапазон назначения, таким образом, чтобы все элементы из исходного диапазона упорядочены.|  
|[partition (STL/CLR)](#partition)|Упорядочивает элементы в диапазоне, таким образом, чтобы эти элементы, удовлетворяющие унарному предикату перед теми, которые не удовлетворяют добавляемому ограничению.|  
|[pop_heap (STL/CLR)](#pop_heap)|Перемещает наибольший элемент из начала кучи до конца, а затем формирует новую кучу из оставшихся элементов.|  
|[prev_permutation (STL/CLR)](#prev_permutation)|Переупорядочивает последовательность элементов, таким образом, чтобы исходный порядок был заменен лексикографически предыдущая перестановка была больше, если он существует.|  
|[push_heap (STL/CLR)](#push_heap)|Добавляет элемент, находящийся в конце диапазона, в существующую кучу, состоящую из предыдущих элементов диапазона.|  
|[random_shuffle (STL/CLR)](#random_shuffle)|Выполняет переупорядочивание последовательности `N` элементов в диапазоне в одном из `N`! возможных порядков, выбранном случайным образом.|  
|[remove (STL/CLR)](#remove)|Удаляет указанное значение из заданного диапазона, не нарушая порядок остальных элементов и возвращает конец нового диапазона указанного значения.|  
|[remove_copy (STL/CLR)](#remove_copy)|Копирует элементы из исходного диапазона диапазону назначения, за исключением того, что элементы с указанным значением, не копируются, не нарушая порядок остальных элементов.|  
|[remove_copy_if (STL/CLR)](#remove_copy_if)|Копирует элементы из исходного диапазона диапазону назначения, за исключением тех, которые удовлетворяют предикату, не нарушая порядок остальных элементов.|  
|[remove_if (STL/CLR)](#remove_if)|Удаляет элементы, соответствующие предикату, из заданного диапазона, не нарушая порядок остальных элементов. .|  
|[replace (STL/CLR)](#replace)|Заменяет элементы в диапазоне, которые соответствуют заданному значению с новым значением.|  
|[replace_copy (STL/CLR)](#replace_copy)|Копирует элементы из исходного диапазона диапазону назначения, заменив элементы, которые соответствуют заданному значению с новым значением.|  
|[replace_copy_if (STL/CLR)](#replace_copy_if)|Проверяет каждый элемент в исходном диапазоне и заменяет его, если он соответствует заданному предикату, одновременно копируя результат в новый диапазон назначения.|  
|[replace_if (STL/CLR)](#replace_if)|Проверяет каждый элемент в диапазоне и заменяет его, если он соответствует заданному предикату.|  
|[reverse (STL/CLR)](#reverse)|Изменяет порядок элементов в диапазоне на обратный.|  
|[reverse_copy (STL/CLR)](#reverse_copy)|Изменяет порядок элементов в исходном диапазоне, одновременно копируя их в диапазон назначения.|  
|[rotate (STL/CLR)](#rotate)|Меняет местами элементы в двух соседних диапазонах.|  
|[rotate_copy (STL/CLR)](#rotate_copy)|Меняет местами элементы в двух соседних диапазонах в пределах исходного диапазона и копирует результат в диапазон назначения.|  
|[search (STL/CLR)](#search_)|Выполняет поиск первого вхождения последовательности в целевой диапазон, элементы которого равны указанным в заданной последовательности элементов или элементы которого равноценны в смысле, заданным бинарным предикатом, элементам в заданной последовательности.|  
|[search_n (STL/CLR)](#search_n)|Выполняет поиск первой подпоследовательности в диапазоне заданного числа элементов, имеющих определенное значение или связанных с этим значением отношением, указанным бинарным предикатом.|  
|[set_difference (STL/CLR)](#set_difference)|Объединяет все элементы, принадлежащие одному отсортированному исходному диапазону, но не второму отсортированному исходному диапазону, в один отсортированный диапазон назначения, где критерий упорядочивания может быть указан бинарным предикатом.|  
|[set_intersection (STL/CLR)](#set_intersection)|Объединяет все элементы, входящие в оба исходных упорядоченных диапазона, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.|  
|[set_symmetric_difference (STL/CLR)](#set_symmetric_difference)|Объединяет все элементы, входящие в один, но не в оба исходных упорядоченных диапазона, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.|  
|[set_union (STL/CLR)](#set_union))|Объединяет все элементы, входящие в хотя бы один из двух исходных упорядоченных диапазонов, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.|  
|[sort (STL/CLR)](#sort)|Упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом.|  
|[sort_heap (STL/CLR)](#sort_heap)|Преобразует кучу в упорядоченный диапазон.|  
|[stable_partition (STL/CLR)](#stable_partition)|Разделяет элементы диапазона на два непересекающихся множества, при этом элементы, удовлетворяющие унарному предикату, расположены перед теми, которые ему не удовлетворяют, с сохранением относительного порядка равноценных элементов.|  
|[stable_sort (STL/CLR)](#stable_sort)|Упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом, и сохраняет относительный порядок равноценных элементов.|  
|[swap (STL/CLR)](#swap)|Меняет местами значения элементов между двумя типами объектов, присваивая содержимое первого объекта второму объекту, а содержимое второго — первому.|  
|[swap_ranges (STL/CLR)](#swap_ranges)|Меняет местами элементы одного диапазона с элементами другого диапазона такого же размера.|  
|[transform (STL/CLR)](#transform)|Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и копирует возвращаемые значения объекта функции в диапазон назначения.|  
|[unique (STL/CLR)](#unique)|Удаляет повторяющиеся элементы, расположенные в указанном диапазоне рядом друг с другом.|  
|[unique_copy (STL/CLR)](#unique_copy)|Копирует элементы из исходного диапазона в диапазон назначения за исключением повторяющихся элементов, расположенных рядом друг с другом.|  
|[upper_bound (STL/CLR)](#upper_bound)|Находит позицию первого элемента в упорядоченном диапазоне, который имеет значение больше указанного значения, где критерий упорядочивания может быть задан бинарным предикатом.|  
 
## <a name="members"></a>Участники

## <a name="adjacent_find"></a> adjacent_find (STL/CLR)
Поиск двух соседних элементов, которые либо равны, либо удовлетворяют указанному условию.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `adjacent_find`. Дополнительные сведения см. в разделе [adjacent_find](../standard-library/algorithm-functions.md#adjacent_find).

## <a name="binary_search"></a> binary_search (STL/CLR)
Проверяет, есть ли в отсортированном диапазоне элемент, равный указанному значению или эквивалентный ему в смысле, заданном двоичным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `binary_search`. Дополнительные сведения см. в разделе [binary_search](../standard-library/algorithm-functions.md#binary_search).  
  
## <a name="copy"></a> Скопируйте (STL/CLR)
Присваивает значения элементов из исходного диапазона диапазону назначения, выполняя итерации в исходной последовательности элементов и присваивая им новые позиции в прямом направлении.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt> inline  
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `copy`. Дополнительные сведения см. в разделе [копирования](../standard-library/algorithm-functions.md#copy). 

## <a name="copy_backward"></a> copy_backward (STL/CLR)
Присваивает значения элементов из исходного диапазона диапазону назначения, выполняя итерации в исходной последовательности элементов и присваивая им новые позиции в обратном направлении.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt1, class _BidIt2> inline  
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,  
        _BidIt2 _Dest);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `copy_backward`. Дополнительные сведения см. в разделе [copy_backward](../standard-library/algorithm-functions.md#copy_backward).  

## <a name="count"></a> Count (STL/CLR)
Возвращает количество элементов в диапазоне, значения которых соответствуют заданному значению.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _Ty> inline  
    typename iterator_traits<_InIt>::difference_type  
        count(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `count`. Дополнительные сведения см. в разделе [число](../standard-library/algorithm-functions.md#count). 

## <a name="count_if"></a> count_if (STL/CLR)
Возвращает количество элементов в диапазоне, значения которых соответствуют заданному условию.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _Pr> inline  
    typename iterator_traits<_InIt>::difference_type  
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `count_if`. Дополнительные сведения см. в разделе [count_if](../standard-library/algorithm-functions.md#count_if).  
  
## <a name="equal"></a> равно (STL/CLR)
Сравнивает два диапазона поэлементно либо на признак равенства или равноценности в смысле, заданном бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `equal`. Дополнительные сведения см. в разделе [равно](../standard-library/algorithm-functions.md#equal).  

## <a name="equal_range"></a> equal_range (STL/CLR)
Находит пару позиций в упорядоченном диапазоне; первая из них меньше или равна позиции указанного элемента, а вторая — больше позиции элемента, где суть равноценности или порядка, используемая, чтобы установить позиции в последовательности, может быть задана бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `equal_range`. Дополнительные сведения см. в разделе [equal_range](../standard-library/algorithm-functions.md#equal_range).  

## <a name="fill"></a> Fill (STL/CLR)
Присваивает одно и то же новое значение каждому элементу в заданном диапазоне.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `fill`. Дополнительные сведения см. в разделе [заливки](../standard-library/algorithm-functions.md#fill). 

## <a name="fill_n"></a> fill_n (STL/CLR)
Назначает новое значение указанному количеству элементов в диапазоне, начиная с определенного элемента.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _OutIt, class _Diff, class _Ty> inline  
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `fill_n`. Дополнительные сведения см. в разделе [fill_n](../standard-library/algorithm-functions.md#fill_n).  

## <a name="find"></a> найти (STL/CLR)
Находит позицию первого вхождения элемента с заданным значением в диапазон.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _Ty> inline  
    _InIt find(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `find`. Дополнительные сведения см. в разделе [найти](../standard-library/algorithm-functions.md#find). 

## <a name="find_end"></a> find_end (STL/CLR)
Ищет в диапазоне последнюю подпоследовательность, совпадающую с заданной последовательностью, или эквивалентной согласно условию, заданному двоичным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `find_end`. Дополнительные сведения см. в разделе [find_end](../standard-library/algorithm-functions.md#find_end).  

## <a name="find_first_of"></a> find_first_of (STL/CLR)
Выполняет поиск первого вхождения любого из нескольких значений в заданный диапазон или первого вхождения любого из нескольких элементов, равноценных в смысле, заданном бинарным предикатом, в указанный набор элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `find_first_of`. Дополнительные сведения см. в разделе [find_first_of](../standard-library/algorithm-functions.md#find_first_of).  

## <a name="find_if"></a> find_if (STL/CLR)
Находит позицию первого вхождения элемента, удовлетворяющего определенному условию, в диапазон.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _Pr> inline  
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `find_if`. Дополнительные сведения см. в разделе [find_if](../standard-library/algorithm-functions.md#find_if). 

## <a name="for_each"></a> for_each (STL/CLR)
Применяет заданный объект функции к каждому элементу в прямом порядке в пределах диапазона и возвращает объект функции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `for_each`. Дополнительные сведения см. в разделе [for_each](../standard-library/algorithm-functions.md#for_each).  

## <a name="generate"></a> Создать (STL/CLR)
Присваивает значения, создаваемые объектом функции, каждому элементу в диапазоне.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Fn0> inline  
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `generate`. Дополнительные сведения см. в разделе [создания](../standard-library/algorithm-functions.md#generate).  

## <a name="generate_n"></a> generate_n (STL/CLR)
Присваивает значения, создаваемые объектом функции, указанному количеству элементов в диапазон и возвращается на позицию, следующую за последним присвоенным значением.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `generate_n`. Дополнительные сведения см. в разделе [generate_n](../standard-library/algorithm-functions.md#generate_n).  
 
## <a name="includes"></a> включает в себя (STL/CLR)
Проверяет, содержит ли один отсортированный диапазон все элементы, содержащиеся во втором отсортированном диапазоне, где порядок сортировки или критерий эквивалентности элементов можно задать бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `includes`. Дополнительные сведения см. в разделе [включает в себя](../standard-library/algorithm-functions.md#includes).  

## <a name="inplace_merge"></a> inplace_merge (STL/CLR)
Объединяет элементы из двух последовательных упорядоченных диапазонов в один упорядоченный диапазон, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `inplace_merge` Дополнительные сведения см. в разделе [inplace_merge](../standard-library/algorithm-functions.md#inplace_merge).  
  
## <a name="iter_swap"></a> iter_swap (STL/CLR)
Меняет местами два значения, указанные парой определенных итераторов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _FwdIt2> inline  
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `iter_swap`. Дополнительные сведения см. в разделе [iter_swap](../standard-library/algorithm-functions.md#iter_swap).  

## <a name="lexicographical_compare"></a> lexicographical_compare (STL/CLR)
Сравнивает две последовательности поэлементно для определения того, какой элемент из двух меньше.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `lexicographical_compare`. Дополнительные сведения см. в разделе [lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare).  

## <a name="lower_bound"></a> lower_bound (STL/CLR)
Находит позицию первого элемента в упорядоченном диапазоне, который имеет значение меньше или равна указанному значению, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `lower_bound`. Дополнительные сведения см. в разделе [lower_bound](../standard-library/algorithm-functions.md#lower_bound).  

## <a name="make_heap"></a> make_heap (STL/CLR)
Преобразует элементы из указанного диапазона в кучу, в которой первый элемент является наибольшим и для которой критерий сортировки может быть определен бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `make_heap`. Дополнительные сведения см. в разделе [make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="max"></a> max (STL/CLR)
Сравнивает два объекта и возвращает больший из них, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _Ty> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `max`. Дополнительные сведения см. в разделе [max](../standard-library/algorithm-functions.md#max).  

## <a name="max_element"></a> max_element (STL/CLR)
Находит первое вхождение наибольшего элемента в указанном диапазоне, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `max_element`. Дополнительные сведения см. в разделе [max_element](../standard-library/algorithm-functions.md#max_element).  

## <a name="merge"></a> Merge (STL/CLR)
Объединяет все элементы из двух исходных упорядоченных диапазонов в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `merge`. Дополнительные сведения см. в разделе [слияния](../standard-library/algorithm-functions.md#merge).  

## <a name="min"></a> Min (STL/CLR)
Сравнивает два объекта и возвращает меньший из них, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `min`. Дополнительные сведения см. в разделе [min](../standard-library/algorithm-functions.md#min).  

## <a name="min_element"></a> min_element (STL/CLR)
Находит первое вхождение наименьшего элемента в указанном диапазоне, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `min_element`. Дополнительные сведения см. в разделе [min_element](../standard-library/algorithm-functions.md#min_element).  
  
## <a name="mismatch"></a> Несоответствие (STL/CLR)
Сравнивает два диапазона поэлементно либо на равенство или равноценность в смысле, заданном бинарным предикатом, и находит первую позицию, где наблюдается разница.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
            _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `mismatch`. Дополнительные сведения см. в разделе [несоответствие](../standard-library/algorithm-functions.md#mismatch).  

## <a name="next_permutation"></a> next_permutation (STL/CLR)
Изменяет порядок элементов в диапазоне, чтобы исходный порядок был заменен перестановкой "лексикографически следующий больший", если такая существует, где смысл термина "следующий" может быть задан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp 
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `next_permutation`. Дополнительные сведения см. в разделе [next_permutation](../standard-library/algorithm-functions.md#next_permutation).  
  
## <a name="nth_element"></a> nth_element (STL/CLR)
Разделяет диапазон элементов, правильно находя `n`-й элемент последовательности в диапазоне, таким образом, все элементы перед ним были меньше или равны ему, а также все элементы в последовательности, больше или равны ему.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `nth_element`. Дополнительные сведения см. в разделе [nth_element](../standard-library/algorithm-functions.md#nth_element).  

## <a name="partial_sort"></a> partial_sort (STL/CLR)
Упорядочивает указанное число меньших элементов в диапазоне в не нисходящий порядок или согласно критерию упорядочивания, заданному бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `partial_sort`. Дополнительные сведения см. в разделе [partial_sort](../standard-library/algorithm-functions.md#partial_sort). 

## <a name="partial_sort_copy"></a> partial_sort_copy (STL/CLR)
Копирует элементы из исходного диапазона в диапазон назначения, где исходные элементы упорядочены по критерию "меньше либо равно" или согласно другому заданному бинарному предикату.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _RanIt> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2);  
template<class _InIt, class _RanIt, class _Pr> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `partial_sort_copy`. Дополнительные сведения см. в разделе [partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy).  
  
## <a name="partition"></a> секции (STL/CLR)
Разделяет элементы диапазона на два непересекающихся множества, при этом элементы, удовлетворяющие унарному предикату, расположены перед теми, которые ему не удовлетворяют.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt, class _Pr> inline  
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `partition`. Дополнительные сведения см. в разделе [секции](../standard-library/algorithm-functions.md#partition).  

## <a name="pop_heap"></a> pop_heap (STL/CLR)
Удаляет наибольший элемент из начала кучи до позиции, следующей за последней, в диапазоне, а затем формирует новую кучу из оставшихся элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void pop_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `pop_heap`. Дополнительные сведения см. в разделе [pop_heap](../standard-library/algorithm-functions.md#pop_heap).  

## <a name="prev_permutation"></a> prev_permutation (STL/CLR)
Изменяет порядок элементов в диапазоне, чтобы исходный порядок был заменен перестановкой "лексикографически следующий больший", если такая существует, где смысл термина "следующий" может быть задан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `prev_permutation`. Дополнительные сведения см. в разделе [prev_permutation](../standard-library/algorithm-functions.md#prev_permutation).  

## <a name="push_heap"></a> push_heap (STL/CLR)
Добавляет элемент, находящийся в конце диапазона, в существующую кучу, состоящую из предыдущих элементов диапазона.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `push_heap`. Дополнительные сведения см. в разделе [push_heap](../standard-library/algorithm-functions.md#push_heap).  

## <a name="random_shuffle"></a> random_shuffle (STL/CLR)
Выполняет переупорядочивание последовательности `N` элементов в диапазоне в одном из `N`! возможных порядков, выбранном случайным образом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Fn1> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `random_shuffle`. Дополнительные сведения см. в разделе [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle). 

## <a name="remove"></a> удалить (STL/CLR)
Удаляет указанное значение из заданного диапазона без нарушения порядка остальных элементов и возвращает конец нового диапазона после удаления указанного значения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `remove`. Дополнительные сведения см. в разделе [удалить](../standard-library/algorithm-functions.md#remove).  

## <a name="remove_copy"></a> remove_copy (STL/CLR)
Копирует элементы из исходного диапазона в диапазон назначения за исключением того, что элементы с заданным значением не копируются, не нарушая порядок остальных элементов и возвращая конец нового диапазона назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `remove_copy`. Дополнительные сведения см. в разделе [remove_copy](../standard-library/algorithm-functions.md#remove_copy).  

## <a name="remove_copy_if"></a> remove_copy_if (STL/CLR)
Копирует элементы из исходного диапазона в диапазон назначения за исключением того, что элементы, соответствующие предикату, не копируются, не нарушая порядок остальных элементов и возвращая конец нового диапазона назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `remove_copy_if`. Дополнительные сведения см. в разделе [remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if).  
  
## <a name="remove_if"></a> remove_if (STL/CLR)
Удаляет элементы, соответствующие предикату, из заданного диапазона без нарушения порядка остальных элементов и возвращает конец нового диапазона после удаления указанного значения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `remove_if`. Дополнительные сведения см. в разделе [remove_if](../standard-library/algorithm-functions.md#remove_if).  
  
## <a name="replace"></a> REPLACE (STL/CLR)
Проверяет каждый элемент в диапазоне и заменяет его, если он соответствует заданному значению.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    void replace(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `replace`. Дополнительные сведения см. в разделе [замените](../standard-library/algorithm-functions.md#replace).

## <a name="replace_copy"></a> replace_copy (STL/CLR)
Проверяет каждый элемент в исходном диапазоне и заменяет его, если он соответствует заданному значению, одновременно копируя результат в новый диапазон назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `replace_copy`. Дополнительные сведения см. в разделе [replace_copy](../standard-library/algorithm-functions.md#replace_copy).  

## <a name="replace_copy_if"></a> replace_copy_if (STL/CLR)
Проверяет каждый элемент в исходном диапазоне и заменяет его, если он соответствует заданному предикату, одновременно копируя результат в новый диапазон назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline  
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `replace_copy_if`. Дополнительные сведения см. в разделе [replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if).  
  
## <a name="replace_if"></a> replace_if (STL/CLR)
Проверяет каждый элемент в диапазоне и заменяет его, если он соответствует заданному предикату.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Pr, class _Ty> inline  
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,  
        const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `replace_if`. Дополнительные сведения см. в разделе [replace_if](../standard-library/algorithm-functions.md#replace_if).  

## <a name="reverse"></a> reverse (STL/CLR)
Изменяет порядок элементов в диапазоне на обратный.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt> inline  
    void reverse(_BidIt _First, _BidIt _Last);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `reverse`. Дополнительные сведения см. в разделе [обратного](../standard-library/algorithm-functions.md#reverse).  

## <a name="reverse_copy"></a> reverse_copy (STL/CLR)
Изменяет порядок элементов в исходном диапазоне, одновременно копируя их в диапазон назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt, class _OutIt> inline  
    _OutIt reverse_copy(_BidIt _First, _BidIt _Last, _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `reverse_copy`. Дополнительные сведения см. в разделе [reverse_copy](../standard-library/algorithm-functions.md#reverse_copy).  
  
## <a name="rotate"></a> Поворот (STL/CLR)
Меняет местами элементы в двух соседних диапазонах.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt> inline  
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `rotate`. Дополнительные сведения см. в разделе [повернуть](../standard-library/algorithm-functions.md#rotate).  

## <a name="rotate_copy"></a> rotate_copy (STL/CLR)
Меняет местами элементы в двух соседних диапазонах в пределах исходного диапазона и копирует результат в диапазон назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `rotate_copy`. Дополнительные сведения см. в разделе [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy).  
  
## <a name="search_"></a> Поиск (STL/CLR)
Выполняет поиск первого вхождения последовательности в целевой диапазон, элементы которого равны указанным в заданной последовательности элементов или элементы которого равноценны в смысле, заданным бинарным предикатом, элементам в заданной последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `search`. Дополнительные сведения см. в разделе [поиска](../standard-library/algorithm-functions.md#search).  

## <a name="search_n"></a> search_n (STL/CLR)
Выполняет поиск первой подпоследовательности в диапазоне заданного числа элементов, имеющих определенное значение или связанных с этим значением отношением, указанным бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _Diff2, class _Ty> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val);  
template<class _FwdIt1, class _Diff2, class _Ty, class _Pr> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `search_n`. Дополнительные сведения см. в разделе [search_n](../standard-library/algorithm-functions.md#search_n).  

## <a name="set_difference"></a> set_difference (STL/CLR)
Объединяет все элементы, принадлежащие одному отсортированному исходному диапазону, но не второму отсортированному исходному диапазону, в один отсортированный диапазон назначения, где критерий упорядочивания может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `set_difference`. Дополнительные сведения см. в разделе [set_difference](../standard-library/algorithm-functions.md#set_difference).

## <a name="set_intersection"></a> set_intersection (STL/CLR)
Объединяет все элементы, входящие в оба исходных упорядоченных диапазона, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `set_intersection`. Дополнительные сведения см. в разделе [set_intersection](../standard-library/algorithm-functions.md#set_intersection). 

## <a name="set_symmetric_difference"></a> set_symmetric_difference (STL/CLR)
Объединяет все элементы, входящие в один, но не в оба исходных упорядоченных диапазона, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `set_symmetric_difference`. Дополнительные сведения см. в разделе [set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference).  

## <a name="set_union"></a> set_union (STL/CLR)
Объединяет все элементы, входящие в хотя бы один из двух исходных упорядоченных диапазонов, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `set_union`. Дополнительные сведения см. в разделе [set_union](../standard-library/algorithm-functions.md#set_union).  

## <a name="sort"></a> Сортировка (STL/CLR)
Упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void sort(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `sort`. Дополнительные сведения см. в разделе [сортировки](../mfc/reference/cmfclistctrl-class.md#sort).  

## <a name="sort_heap"></a> sort_heap (STL/CLR)
Преобразует кучу в упорядоченный диапазон.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _RanIt> inline  
    void sort_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `sort_heap`. Дополнительные сведения см. в разделе [sort_heap](../standard-library/algorithm-functions.md#sort_heap).  

## <a name="stable_partition"></a> stable_partition (STL/CLR)
Разделяет элементы диапазона на два непересекающихся множества, при этом элементы, удовлетворяющие унарному предикату, расположены перед теми, которые ему не удовлетворяют, с сохранением относительного порядка равноценных элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `stable_partition`. Дополнительные сведения см. в разделе [stable_partition](../standard-library/algorithm-functions.md#stable_partition).  

## <a name="stable_sort"></a> stable_sort (STL/CLR)
Упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом, и сохраняет относительный порядок равноценных элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _BidIt> inline  
    void stable_sort(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `stable_sort`. Дополнительные сведения см. в разделе [stable_sort](../standard-library/algorithm-functions.md#stable_sort).  
  
## <a name="swap"></a> Swap (STL/CLR)
Меняет местами значения элементов между двумя типами объектов, присваивая содержимое первого объекта второму объекту, а содержимое второго — первому.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
<class _Ty> inline  
    void swap(_Ty% _Left, _Ty% _Right);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `swap`. Дополнительные сведения см. в разделе [замены](../standard-library/algorithm-functions.md#swap).  

## <a name="swap_ranges"></a> swap_ranges (STL/CLR)
Меняет местами элементы одного диапазона с элементами другого диапазона такого же размера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `swap_ranges`. Дополнительные сведения см. в разделе [swap_ranges](../standard-library/algorithm-functions.md#swap_ranges).  

## <a name="transform"></a> преобразование (STL/CLR)
Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и копирует возвращаемые значения объекта функции в диапазон назначения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `transform`. Дополнительные сведения см. в разделе [преобразование](../standard-library/algorithm-functions.md#transform).  

## <a name="unique"></a> Уникальный (STL/CLR)
Удаляет повторяющиеся элементы, расположенные в указанном диапазоне рядом друг с другом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `unique`. Дополнительные сведения см. в разделе [уникальный](../standard-library/algorithm-functions.md#unique).  
  
## <a name="unique_copy"></a> unique_copy (STL/CLR)
Копирует элементы из исходного диапазона в диапазон назначения за исключением повторяющихся элементов, расположенных рядом друг с другом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _InIt, class _OutIt> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `unique_copy`. Дополнительные сведения см. в разделе [unique_copy](../standard-library/algorithm-functions.md#unique_copy).  

## <a name="upper_bound"></a> upper_bound (STL/CLR)
Находит позицию первого элемента в упорядоченном диапазоне, который имеет значение больше указанного значения, где критерий упорядочивания может быть задан бинарным предикатом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция ведет себя так же, как функция стандартной библиотеки C++ `upper_bound`. Дополнительные сведения см. в разделе [upper_bound](../standard-library/algorithm-functions.md#upper_bound). 