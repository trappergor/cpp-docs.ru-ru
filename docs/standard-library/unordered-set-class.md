---
title: "Класс unordered_set | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_set
- std::unordered_set
- unordered_set/std::unordered_set
- std::unordered_set::allocator_type
- unordered_set/std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- unordered_set/std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- unordered_set/std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- unordered_set/std::unordered_set::const_pointer
- std::unordered_set::const_reference
- unordered_set/std::unordered_set::const_reference
- std::unordered_set::difference_type
- unordered_set/std::unordered_set::difference_type
- std::unordered_set::hasher
- unordered_set/std::unordered_set::hasher
- std::unordered_set::iterator
- unordered_set/std::unordered_set::iterator
- std::unordered_set::key_equal
- unordered_set/std::unordered_set::key_equal
- std::unordered_set::key_type
- unordered_set/std::unordered_set::key_type
- std::unordered_set::local_iterator
- unordered_set/std::unordered_set::local_iterator
- std::unordered_set::pointer
- unordered_set/std::unordered_set::pointer
- std::unordered_set::reference
- unordered_set/std::unordered_set::reference
- std::unordered_set::size_type
- unordered_set/std::unordered_set::size_type
- std::unordered_set::value_type
- unordered_set/std::unordered_set::value_type
- std::unordered_set::begin
- unordered_set/std::unordered_set::begin
- std::unordered_set::bucket
- unordered_set/std::unordered_set::bucket
- std::unordered_set::bucket_count
- unordered_set/std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- unordered_set/std::unordered_set::bucket_size
- std::unordered_set::cbegin
- unordered_set/std::unordered_set::cbegin
- std::unordered_set::cend
- unordered_set/std::unordered_set::cend
- std::unordered_set::clear
- unordered_set/std::unordered_set::clear
- std::unordered_set::count
- unordered_set/std::unordered_set::count
- std::unordered_set::emplace
- unordered_set/std::unordered_set::emplace
- std::unordered_set::emplace_hint
- unordered_set/std::unordered_set::emplace_hint
- std::unordered_set::empty
- unordered_set/std::unordered_set::empty
- std::unordered_set::end
- unordered_set/std::unordered_set::end
- std::unordered_set::equal_range
- unordered_set/std::unordered_set::equal_range
- std::unordered_set::erase
- unordered_set/std::unordered_set::erase
- std::unordered_set::find
- unordered_set/std::unordered_set::find
- std::unordered_set::get_allocator
- unordered_set/std::unordered_set::get_allocator
- std::unordered_set::hash_function
- unordered_set/std::unordered_set::hash_function
- std::unordered_set::insert
- unordered_set/std::unordered_set::insert
- std::unordered_set::key_eq
- unordered_set/std::unordered_set::key_eq
- std::unordered_set::load_factor
- unordered_set/std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- unordered_set/std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- unordered_set/std::unordered_set::max_load_factor
- std::unordered_set::max_size
- unordered_set/std::unordered_set::max_size
- std::unordered_set::rehash
- unordered_set/std::unordered_set::rehash
- std::unordered_set::size
- unordered_set/std::unordered_set::size
- std::unordered_set::swap
- unordered_set/std::unordered_set::swap
- std::unordered_set::unordered_set
- unordered_set/std::unordered_set::unordered_set
- std::unordered_set::operator=
- unordered_set/std::unordered_set::operator=
dev_langs:
- C++
helpviewer_keywords:
- unordered_set class
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e41fbf26ba7a2209dac67965ac3a5e045bf93324
ms.lasthandoff: 02/24/2017

---
# <a name="unorderedset-class"></a>Класс unordered_set
Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `const Key` переменной длины. Последовательность слабо упорядочена хэш-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками. В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом. Каждый элемент используется в качестве ключа сортировки и в качестве значения. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности (постоянное время), по крайней мере, когда все блоки имеют примерно одинаковую длину. В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности (линейное время). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <
   class Key,  
   class Hash = std::hash<Key>,  
   class Pred = std::equal_to<Key>,  
   class Alloc = std::allocator<Key>>  
class unordered_set;  
```  
  
#### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Key`|Тип ключа.|  
|`Hash`|Тип объекта хэш-функции.|  
|`Pred`|Тип объекта функции сравнения на предмет равенства.|  
|`Alloc`|Класс распределителя.|  
  
## <a name="members"></a>Члены  
  
|||  
|-|-|  
|Определение типа|Описание|  
|[unordered_set::allocator_type](#unordered_set__allocator_type)|Тип распределителя для управления хранилищем.|  
|[unordered_set::const_iterator](#unordered_set__const_iterator)|Тип постоянного итератора для управляемой последовательности.|  
|[unordered_set::const_local_iterator](#unordered_set__const_local_iterator)|Тип постоянного итератора блока для управляемой последовательности.|  
|[unordered_set::const_pointer](#unordered_set__const_pointer)|Тип постоянного указателя на элемент.|  
|[unordered_set::const_reference](#unordered_set__const_reference)|Тип постоянной ссылки на элемент.|  
|[unordered_set::difference_type](#unordered_set__difference_type)|Тип расстояния со знаком между двумя элементами.|  
|[unordered_set::hasher](#unordered_set__hasher)|Тип хэш-функции.|  
|[unordered_set::iterator](#unordered_set__iterator)|Тип итератора для управляемой последовательности.|  
|[unordered_set::key_equal](#unordered_set__key_equal)|Тип функции сравнения.|  
|[unordered_set::key_type](#unordered_set__key_type)|Тип ключа упорядочения.|  
|[unordered_set::local_iterator](#unordered_set__local_iterator)|Тип итератора блока для управляемой последовательности.|  
|[unordered_set::pointer](#unordered_set__pointer)|Тип указателя на элемент.|  
|[unordered_set::reference](#unordered_set__reference)|Тип ссылки на элемент.|  
|[unordered_set::size_type](#unordered_set__size_type)|Тип беззнакового расстояния между двумя элементами.|  
|[unordered_set::value_type](#unordered_set__value_type)|Тип элемента.|  
  
|||  
|-|-|  
|Функция-член|Описание|  
|[unordered_set::begin](#unordered_set__begin)|Задает начало управляемой последовательности.|  
|[unordered_set::bucket](#unordered_set__bucket)|Получает номер блока для значения ключа.|  
|[unordered_set::bucket_count](#unordered_set__bucket_count)|Получает количество блоков.|  
|[unordered_set::bucket_size](#unordered_set__bucket_size)|Получает размер блока.|  
|[unordered_set::cbegin](#unordered_set__cbegin)|Задает начало управляемой последовательности.|  
|[unordered_set::cend](#unordered_set__cend)|Задает конец управляемой последовательности.|  
|[unordered_set::clear](#unordered_set__clear)|Удаляет все элементы.|  
|[unordered_set::count](#unordered_set__count)|Определяет количество элементов, соответствующих заданному ключу.|  
|[unordered_set::emplace](#unordered_set__emplace)|Добавляет элемент, созданный на месте.|  
|[unordered_set::emplace_hint](#unordered_set__emplace_hint)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[unordered_set::empty](#unordered_set__empty)|Проверяет отсутствие элементов.|  
|[unordered_set::end](#unordered_set__end)|Задает конец управляемой последовательности.|  
|[unordered_set::equal_range](#unordered_set__equal_range)|Находит диапазон, соответствующий указанному ключу.|  
|[unordered_set::erase](#unordered_set__erase)|Удаляет элементы в указанных позициях.|  
|[unordered_set::find](#unordered_set__find)|Определяет элемент, соответствующий указанному ключу.|  
|[unordered_set::get_allocator](#unordered_set__get_allocator)|Возвращает сохраненный объект распределителя.|  
|[unordered_set::hash_function](#unordered_set__hash_function)|Получает сохраненный объект хэш-функции.|  
|[unordered_set::insert](#unordered_set__insert)|Добавляет элементы.|  
|[unordered_set::key_eq](#unordered_set__key_eq)|Получает сохраненный объект функции сравнения.|  
|[unordered_set::load_factor](#unordered_set__load_factor)|Подсчитывает среднее число элементов в блоке.|  
|[unordered_set::max_bucket_count](#unordered_set__max_bucket_count)|Получает максимальное количество блоков.|  
|[unordered_set::max_load_factor](#unordered_set__max_load_factor)|Возвращает или задает максимальное количество элементов в блоке.|  
|[unordered_set::max_size](#unordered_set__max_size)|Возвращает максимальный размер управляемой последовательности.|  
|[unordered_set::rehash](#unordered_set__rehash)|Повторно создает хэш-таблицу.|  
|[unordered_set::size](#unordered_set__size)|Подсчитывает количество элементов.|  
|[unordered_set::swap](#unordered_set__swap)|Меняет местами содержимое двух контейнеров.|  
|[unordered_set::unordered_set](#unordered_set__unordered_set)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Операторы|Описание|  
|[unordered_set::operator=](#unordered_set__operator_eq)|Копирует хэш-таблицу.|  
  
## <a name="remarks"></a>Примечания  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов — объекта функции сравнения типа [unordered_set::key_equal](#unordered_set__key_equal) и объекта хэш-функции типа [unordered_set::hasher](#unordered_set__hasher). Доступ к первому сохраненному объекту можно получить, вызвав функцию-член [unordered_set::key_eq](#unordered_set__key_eq)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции-члена [unordered_set::hash_function](#unordered_set__hash_function)`()`. В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`. В отличие от класса шаблона [unordered_multiset Class](../standard-library/unordered-multiset-class.md) объект класса шаблона `unordered_set` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов управляемой последовательности. (Ключи уникальны).  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке. Если вставка элемента приводит к тому, что значение [unordered_set::load_factor](#unordered_set__load_factor)`()` превышает максимальный коэффициент нагрузки, контейнер увеличивает количество блоков и перестраивает хэш-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков. Обычно невозможно предсказать порядок элементов в управляемой последовательности. Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered_set::allocator_type](#unordered_set__allocator_type). Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`. Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<unordered_set>  
  
 **Пространство имен:** std  
  
##  <a name="a-nameunorderedsetallocatortypea--unorderedsetallocatortype"></a><a name="unordered_set__allocator_type"></a>  unordered_set::allocator_type  
 Тип распределителя для управления хранилищем.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона `Alloc`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_allocator_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
typedef std::allocator<std::pair<const char, int> > Myalloc;  
int main()  
{  
Myset c1;  
  
Myset::allocator_type al = c1.get_allocator();  
std::cout << "al == std::allocator() is "  
<< std::boolalpha << (al == Myalloc()) << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="a-nameunorderedsetbegina--unorderedsetbegin"></a><a name="unordered_set__begin"></a>  unordered_set::begin  
 Задает начало управляемой последовательности или сегмента.  
  
```  
 
iterator begin();

const_iterator begin() const;

 
local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`nbucket`|Номер сегмента.|  
  
### <a name="remarks"></a>Примечания  
 Первые две функции-члены возвращают прямой итератор, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности). Последние две функции-члены возвращают прямой итератор, указывающий на первый элемент сегмента `nbucket` (или на место сразу за концом пустого сегмента).  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_set_begin.cpp  
// compile using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_set>  
#include <iostream>  
  
using namespace std;  
  
typedef unordered_set<char> MySet;  
  
int main()  
{  
MySet c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents using range-based for  
for (auto it : c1) {  
cout << " [" << it << "]";  
}  
  
cout << endl;  
  
// display contents using explicit for  
for (MySet::const_iterator it = c1.begin(); it != c1.end(); ++it) {  
cout << " [" << *it << "]";  
}  
  
cout << std::endl;  
  
// display first two items  
MySet::iterator it2 = c1.begin();  
cout << " [" << *it2 << "]";  
++it2;  
cout << " [" << *it2 << "]";  
cout << endl;  
  
// display bucket containing 'a'  
MySet::const_local_iterator lit = c1.begin(c1.bucket('a'));  
cout << " [" << *lit << "]";  
  
return (0);  
}  
  
```  
  
```Output  
  
[a] [b] [c]                                   
  
[a] [b] [c]                                  
  
[a] [b]                                   
  
[a]  
  
```  
  
##  <a name="a-nameunorderedsetbucketa--unorderedsetbucket"></a><a name="unordered_set__bucket"></a>  unordered_set::bucket  
 Получает номер блока для значения ключа.  
  
```  
size_type bucket(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Значение ключа для сопоставления.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает номер контейнера, который в настоящий момент соответствует значению ключа `keyval`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_bucket.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// display buckets for keys  
Myset::size_type bs = c1.bucket('a');  
std::cout << "bucket('a') == " << bs << std::endl;  
std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)  
<< std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="a-nameunorderedsetbucketcounta--unorderedsetbucketcount"></a><a name="unordered_set__bucket_count"></a>  unordered_set::bucket_count  
 Получает количество блоков.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает текущее число блоков.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_bucket_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect current parameters  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// change max_load_factor and redisplay  
c1.max_load_factor(0.10f);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// rehash and redisplay  
c1.rehash(100);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedsetbucketsizea--unorderedsetbucketsize"></a><a name="unordered_set__bucket_size"></a>  unordered_set::bucket_size  
 Получает размер сегмента.  
  
```  
size_type bucket_size(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nbucket`  
 Номер сегмента.  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают размер номера сегмента `nbucket`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_bucket_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// display buckets for keys  
Myset::size_type bs = c1.bucket('a');  
std::cout << "bucket('a') == " << bs << std::endl;  
std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)  
<< std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="a-nameunorderedsetcbegina--unorderedsetcbegin"></a><a name="unordered_set__cbegin"></a>  unordered_set::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор прямого доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет равно `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 isContainer<T>::iterator  
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator  
```  
  
##  <a name="a-nameunorderedsetcenda--unorderedsetcend"></a><a name="unordered_set__cend"></a>  unordered_set::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор прямого доступа `const`, который указывает на позицию непосредственно за концом диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет равно `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `end()` и `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 isContainer<T>::iterator  
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть разыменовано.  
  
##  <a name="a-nameunorderedsetcleara--unorderedsetclear"></a><a name="unordered_set__clear"></a>  unordered_set::clear  
 Удаляет все элементы.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает [unordered_set::erase](#unordered_set__erase)`(` [unordered_set::begin](#unordered_set__begin)`(),` [unordered_set::end](#unordered_set__end)`())`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_clear.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// clear the container and reinspect  
c1.clear();  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
std::cout << std::endl;  
  
c1.insert('d');  
c1.insert('e');  
  
// display contents " [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
size == 0  
empty() == true  
  
[e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedsetconstiteratora--unorderedsetconstiterator"></a><a name="unordered_set__const_iterator"></a>  unordered_set::const_iterator  
 Тип постоянного итератора для управляемой последовательности.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан как синоним для типа `T1`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_const_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="a-nameunorderedsetconstlocaliteratora--unorderedsetconstlocaliterator"></a><a name="unordered_set__const_local_iterator"></a>  unordered_set::const_local_iterator  
 Тип постоянного итератора блока для управляемой последовательности.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного прямого итератора для блока. Он описан как синоним для типа `T5`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_const_local_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect bucket containing 'a'  
Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));  
std::cout << " [" << *lit << "]";  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[a]  
  
```  
  
##  <a name="a-nameunorderedsetconstpointera--unorderedsetconstpointer"></a><a name="unordered_set__const_pointer"></a>  unordered_set::const_pointer  
 Тип постоянного указателя на элемент.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_const_pointer.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::iterator it = c1.begin();  
it != c1.end(); ++it)  
{  
Myset::const_pointer p = &*it;  
std::cout << " [" << *p << "]";  
}  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="a-nameunorderedsetconstreferencea--unorderedsetconstreference"></a><a name="unordered_set__const_reference"></a>  unordered_set::const_reference  
 Тип постоянной ссылки на элемент.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_const_reference.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::iterator it = c1.begin();  
it != c1.end(); ++it)  
{  
Myset::const_reference ref = *it;  
std::cout << " [" << ref << "]";  
}  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="a-nameunorderedsetcounta--unorderedsetcount"></a><a name="unordered_set__count"></a>  unordered_set::count  
 Определяет количество элементов, соответствующих заданному ключу.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число элементов в диапазоне, ограниченном [unordered_set::equal_range](#unordered_set__equal_range)`(keyval)`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
std::cout << "count('A') == " << c1.count('A') << std::endl;  
std::cout << "count('b') == " << c1.count('b') << std::endl;  
std::cout << "count('C') == " << c1.count('C') << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
count('A') == 0  
count('b') == 1  
count('C') == 0  
```  
  
##  <a name="a-nameunorderedsetdifferencetypea--unorderedsetdifferencetype"></a><a name="unordered_set__difference_type"></a>  unordered_set::difference_type  
 Тип расстояния со знаком между двумя элементами.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Он описан как синоним для типа `T3`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_difference_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// compute positive difference  
Myset::difference_type diff = 0;  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
++diff;  
std::cout << "end()-begin() == " << diff << std::endl;  
  
// compute negative difference  
diff = 0;  
for (Myset::const_iterator it = c1.end();  
it != c1.begin(); --it)  
--diff;  
std::cout << "begin()-end() == " << diff << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
end()-begin() == 3  
begin()-end() == -3  
```  
  
##  <a name="a-nameunorderedsetemplacea--unorderedsetemplace"></a><a name="unordered_set__emplace"></a>  unordered_set::emplace  
 Вставляет созданный элемент на место (операции копирования или перемещения не выполняются).  
  
```  
 
template <class... Args>  
pair<iterator, bool>  
emplace(
Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`args`|Аргументы, которые передаются для создания элемента, который будет вставлен в объект unordered_set, если этот объект еще не содержит элемент, ключ которого упорядочен аналогичным образом.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `pair`, компонент `bool` которого возвращает значение true, если была осуществлена вставка, и false, если `unordered_set` уже содержал элемент, ключ которого имел эквивалентное значение порядка, и компонент итератора которого возвращает адрес нового вставленного элемента или адрес местонахождения элемента, если он уже существовал.  
  
 Для доступа к компоненту итератора пары `pr`, возвращенной этой функцией-членом, используйте `pr.first` и разыменуйте ее с помощью `*(pr.first)`. Для доступа к компоненту `bool` пары `pr`, возвращенной этой функцией-членом, используйте `pr.second`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными итераторы, указатели или ссылки.  
  
 Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.  
  
 Пример кода см. в разделе [set::emplace](../standard-library/set-class.md#set__emplace).  
  
##  <a name="a-nameunorderedsetemplacehinta--unorderedsetemplacehint"></a><a name="unordered_set__emplace_hint"></a>  unordered_set::emplace_hint  
 Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.  
  
```  
 
template <class... Args>  
iterator emplace_hint(
const_iteratorwhere,  
Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`args`|Аргументы, которые передаются для создания элемента, который будет вставлен в объект unordered_set, если объект unordered_set не содержит этого элемента или, в более общем случае, если этот объект еще не содержит элемента, ключ которого упорядочен аналогичным образом.|  
|`where`|Подсказка о месте начала поиска правильной точки вставки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор на вставленный элемент.  
  
 Если не удалось вставить элемент, так как он уже существует, возвращается итератор на существующий элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными итераторы, указатели или ссылки.  
  
 Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.  
  
 Пример кода см. в разделе [set::emplace_hint](../standard-library/set-class.md#set__emplace_hint).  
  
##  <a name="a-nameunorderedsetemptya--unorderedsetempty"></a><a name="unordered_set__empty"></a>  unordered_set::empty  
 Проверяет отсутствие элементов.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_empty.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// clear the container and reinspect  
c1.clear();  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
std::cout << std::endl;  
  
c1.insert('d');  
c1.insert('e');  
  
// display contents " [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
size == 0  
empty() == true  
  
[e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedsetenda--unorderedsetend"></a><a name="unordered_set__end"></a>  unordered_set::end  
 Задает конец управляемой последовательности.  
  
```  
 
iterator end();

const_iterator end() const;

 
local_iterator end(size_type nbucket);

const_local_iterator end(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`nbucket`|Номер сегмента.|  
  
### <a name="remarks"></a>Примечания  
 Первые две функции-члены возвращают прямой итератор, указывающий на место сразу за концом последовательности. Последние две функции-члена возвращают прямой итератор, указывающий на место сразу за концом сегмента `nbucket`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__unordered_set__unordered_set_end.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect last two items " [a] [b]"  
Myset::iterator it2 = c1.end();  
--it2;  
std::cout << " [" << *it2 << "]";  
--it2;  
std::cout << " [" << *it2 << "]";  
std::cout << std::endl;  
  
// inspect bucket containing 'a'  
Myset::const_local_iterator lit = c1.end(c1.bucket('a'));  
--lit;  
std::cout << " [" << *lit << "]";  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[a] [b]  
[a]  
  
```  
  
##  <a name="a-nameunorderedsetequalrangea--unorderedsetequalrange"></a><a name="unordered_set__equal_range"></a>  unordered_set::equal_range  
 Находит диапазон, соответствующий указанному ключу.  
  
```  
 
std::pair<iterator, iterator>  
equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>  
equal_range(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает пару итераторов `X` таких, что `[X.first, X.second)` отделяет только те элементы управляемой последовательности, которые имеют эквивалентное упорядочение с `keyval`. Если таких элементов не существует, оба итератора имеют значение `end()`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_equal_range.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// display results of failed search  
std::pair<Myset::iterator, Myset::iterator> pair1 =  
c1.equal_range('x');  
std::cout << "equal_range('x'):";  
for (; pair1.first != pair1.second; ++pair1.first)  
std::cout << " [" << *pair1.first << "]";  
std::cout << std::endl;  
  
// display results of successful search  
pair1 = c1.equal_range('b');  
std::cout << "equal_range('b'):";  
for (; pair1.first != pair1.second; ++pair1.first)  
std::cout << " [" << *pair1.first << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
equal_range('x'):  
equal_range('b'): [b]  
  
```  
  
##  <a name="a-nameunorderedseterasea--unorderedseterase"></a><a name="unordered_set__erase"></a>  unordered_set::erase  
 Удаляет элемент или диапазон элементов в объекте unordered_set с заданных позиций или удаляет элементы, соответствующие заданному ключу.  
  
```  
 
iterator erase(const_iteratorWhere);

iterator erase(
const_iteratorFirst, const_iteratorLast);

size_type erase(
const key_type& Key);
```  
  
### <a name="parameters"></a>Параметры  
 `Where`  
 Положение удаляемого элемента.  
  
 `First`  
 Положение первого удаляемого элемента.  
  
 `Last`  
 Положение перед последним удаляемым элементом.  
  
 `Key`  
 Значение ключа удаляемых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на последний элемент объекта unordered_set, если такого элемента не существует.  
  
 Для третьей функции-члена возвращает число элементов, которые были удалены из объекта unordered_set.  
  
### <a name="remarks"></a>Примечания  
 Пример кода см. в разделе [set::erase](../standard-library/set-class.md#set__erase).  
  
##  <a name="a-nameunorderedsetfinda--unorderedsetfind"></a><a name="unordered_set__find"></a>  unordered_set::find  
 Определяет элемент, соответствующий указанному ключу.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [unordered_set::equal_range](#unordered_set__equal_range)`(keyval).first`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_find.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// try to find and fail  
std::cout << "find('A') == "  
<< std::boolalpha << (c1.find('A') != c1.end()) << std::endl;  
  
// try to find and succeed  
Myset::iterator it = c1.find('b');  
std::cout << "find('b') == "  
<< std::boolalpha << (it != c1.end())  
<< ": [" << *it << "]" << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
find('A') == false  
find('b') == true: [b]  
  
```  
  
##  <a name="a-nameunorderedsetgetallocatora--unorderedsetgetallocator"></a><a name="unordered_set__get_allocator"></a>  unordered_set::get_allocator  
 Возвращает сохраненный объект распределителя.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект распределителя.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_get_allocator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
typedef std::allocator<std::pair<const char, int> > Myalloc;  
int main()  
{  
Myset c1;  
  
Myset::allocator_type al = c1.get_allocator();  
std::cout << "al == std::allocator() is "  
<< std::boolalpha << (al == Myalloc()) << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="a-nameunorderedsethashfunctiona--unorderedsethashfunction"></a><a name="unordered_set__hash_function"></a>  unordered_set::hash_function  
 Получает сохраненный объект хэш-функции.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект хэш-функции.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_hash_function.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
Myset::hasher hfn = c1.hash_function();  
std::cout << "hfn('a') == " << hfn('a') << std::endl;  
std::cout << "hfn('b') == " << hfn('b') << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="a-nameunorderedsethashera--unorderedsethasher"></a><a name="unordered_set__hasher"></a>  unordered_set::hasher  
 Тип хэш-функции.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона `Hash`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_hasher.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
Myset::hasher hfn = c1.hash_function();  
std::cout << "hfn('a') == " << hfn('a') << std::endl;  
std::cout << "hfn('b') == " << hfn('b') << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="a-nameunorderedsetinserta--unorderedsetinsert"></a><a name="unordered_set__insert"></a>  unordered_set::insert  
 Вставляет элемент или диапазон элементов в unordered_set.  
  
```  
 
// (1) single element  
pair<iterator, bool> insert(
const value_type& Val);

 
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool>  
insert(
ValTy&& Val);

 
// (3) single element with hint  
iterator insert(
const_iterator Where,  
const value_type& Val);

 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(
const_iterator Where,  
ValTy&& Val);

 
// (5) range  
template <class InputIterator>  
void insert(
InputIterator First,  
InputIterator Last);

 
// (6) initializer list  
void insert(
initializer_list<value_type>  
IList);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Val`|Значение элемента, вставляемого в unordered_set, если оно уже не содержит элемент, ключ которого эквивалентно упорядочен.|  
|`Where`|Место начала поиска правильной точки вставки.|  
|`ValTy`|Параметр шаблона, определяющий тип аргумента, с помощью которого unordered_set формирует элемент типа [value_type](../standard-library/map-class.md#map__value_type) и точно пересылает `Val` как аргумент.|  
|`First`|Позиция первого элемента, который следует скопировать.|  
|`Last`|Позиция непосредственно перед последним элементом, который следует скопировать.|  
|`InputIterator`|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#map__value_type).|  
|`IList`|Объект [initializer_list](../standard-library/initializer-list.md), из которого копируются элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одноэлементные функции-члены (1) и (2) возвращают [пару](../standard-library/pair-structure.md), компонент `bool` которой имеет значение true, если была осуществлена вставка, и значение false, если unordered_set уже содержало элемент с эквивалентным порядковым значением ключа. Компонент итератора пары возвращаемых значений указывает на вставленный элемент, если значение компонента `bool` равно true, или на существующий элемент, если значение компонента `bool` равно false.  
  
 Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, который указывает на позицию, где новый элемент был вставлен, или, если элемент с эквивалентным ключом уже существует, указывает на существующий элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает никакие итераторы, указатели или ссылки недействительными.  
  
 Если исключение вызывается во время вставки одного элемента, но оно не вызывается в хэш-функции контейнера, состояние контейнера не изменяется. Если исключение вызывается в хэш-функции, результат не определен. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.  
  
 Для доступа к компоненту итератора `pair``pr`, возвращаемого одноэлементными функциями-членами, используйте `pr.first`. Для разыменования итератора в возвращенной паре используйте `*pr.first`, чтобы получить элемент. Для доступа к компоненту `bool` используйте `pr.second`. См. пример кода далее в этой статье.  
  
 [value_type](../standard-library/map-class.md#map__value_type) контейнера — это определение типа, которое принадлежит контейнеру, а для набора `unordered_set<V>::value_type` — это `const V`.  
  
 Функция-член с диапазоном (5) вставляет последовательность значений элементов в unordered_set, соответствующее каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Поэтому `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `s.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `s`. Вставляются только элементы с уникальными значениями в диапазоне. Повторяющиеся значения игнорируются. Чтобы увидеть, какие элементы отклонены, используйте одноэлементные версии `insert`.  
  
 Функция — член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в unordered_set.  
  
 Сведения о вставке элемента, созданного на месте (т. е. без выполнения операций копирования или перемещения), см. в описании функций [set::emplace](../standard-library/set-class.md#set__emplace) и [set::emplace_hint](../standard-library/set-class.md#set__emplace_hint).  
  
 Пример кода см. в разделе [set::insert](../standard-library/set-class.md#set__insert).  
  
##  <a name="a-nameunorderedsetiteratora--unorderedsetiterator"></a><a name="unordered_set__iterator"></a>  unordered_set::iterator  
 Тип, предоставляющий [прямой итератор](../standard-library/forward-iterator-tag-struct.md) константы, может считывать элементы в объекте unordered_set.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования **итератора** в разделе [begin](../standard-library/set-class.md#set__begin).  
  
##  <a name="a-nameunorderedsetkeyeqa--unorderedsetkeyeq"></a><a name="unordered_set__key_eq"></a>  unordered_set::key_eq  
 Получает сохраненный объект функции сравнения.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект функции сравнения.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_key_eq.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
Myset::key_equal cmpfn = c1.key_eq();  
std::cout << "cmpfn('a', 'a') == "  
<< std::boolalpha << cmpfn('a', 'a') << std::endl;  
std::cout << "cmpfn('a', 'b') == "  
<< std::boolalpha << cmpfn('a', 'b') << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="a-nameunorderedsetkeyequala--unorderedsetkeyequal"></a><a name="unordered_set__key_equal"></a>  unordered_set::key_equal  
 Тип функции сравнения.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона `Pred`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_key_equal.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
Myset::key_equal cmpfn = c1.key_eq();  
std::cout << "cmpfn('a', 'a') == "  
<< std::boolalpha << cmpfn('a', 'a') << std::endl;  
std::cout << "cmpfn('a', 'b') == "  
<< std::boolalpha << cmpfn('a', 'b') << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="a-nameunorderedsetkeytypea--unorderedsetkeytype"></a><a name="unordered_set__key_type"></a>  unordered_set::key_type  
 Тип ключа упорядочения.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона `Key`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_key_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// add a value and reinspect  
Myset::key_type key = 'd';  
Myset::value_type val = key;  
c1.insert(val);  
  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[d] [c] [b] [a]  
  
```  
  
##  <a name="a-nameunorderedsetloadfactora--unorderedsetloadfactor"></a><a name="unordered_set__load_factor"></a>  unordered_set::load_factor  
 Подсчитывает среднее число элементов в блоке.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `(float)`[unordered_set::size](#unordered_set__size)`() / (float)`[unordered_set::bucket_count](#unordered_set__bucket_count)`()`, среднее количество элементов на блок.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_load_factor.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect current parameters  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// change max_load_factor and redisplay  
c1.max_load_factor(0.10f);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// rehash and redisplay  
c1.rehash(100);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedsetlocaliteratora--unorderedsetlocaliterator"></a><a name="unordered_set__local_iterator"></a>  unordered_set::local_iterator  
 Тип итератора контейнера.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве прямого итератора для контейнера. Он описан как синоним для типа `T4`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_local_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect bucket containing 'a'  
Myset::local_iterator lit = c1.begin(c1.bucket('a'));  
std::cout << " [" << *lit << "]";  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[a]  
  
```  
  
##  <a name="a-nameunorderedsetmaxbucketcounta--unorderedsetmaxbucketcount"></a><a name="unordered_set__max_bucket_count"></a>  unordered_set::max_bucket_count  
 Получает максимальное количество блоков.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает максимальное количество блоков, которое разрешено в настоящее время.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_max_bucket_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect current parameters  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// change max_load_factor and redisplay  
c1.max_load_factor(0.10f);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// rehash and redisplay  
c1.rehash(100);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedsetmaxloadfactora--unorderedsetmaxloadfactor"></a><a name="unordered_set__max_load_factor"></a>  unordered_set::max_load_factor  
 Возвращает или задает максимальное количество элементов в блоке.  
  
```  
 
float max_load_factor() const;

 
void max_load_factor(float factor);
```  
  
### <a name="parameters"></a>Параметры  
 `factor`  
 Новый коэффициент максимальной нагрузки.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член заменяет сохраненный коэффициент максимальной нагрузки `factor`.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_max_load_factor.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect current parameters  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// change max_load_factor and redisplay  
c1.max_load_factor(0.10f);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// rehash and redisplay  
c1.rehash(100);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_bucket_count() == "  
<< c1.max_bucket_count() << std::endl;  
std::cout << "max_load_factor() == "  
<< c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedsetmaxsizea--unorderedsetmaxsize"></a><a name="unordered_set__max_size"></a>  unordered_set::max_size  
 Возвращает максимальный размер управляемой последовательности.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_max_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
std::cout << "max_size() == " << c1.max_size() << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
max_size() == 4294967295  
```  
  
##  <a name="a-nameunorderedsetoperatoreqa--unorderedsetoperator"></a><a name="unordered_set__operator_eq"></a>  unordered_set::operator=  
 Копирует хэш-таблицу.  
  
```  
 
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` right`|[unordered_set](../standard-library/unordered-set-class.md) копируется в `unordered_set`.|  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в объекте `unordered_set` `operator=` копирует или перемещает содержимое ` right` в объект `unordered_set`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_set_operator_as.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
unordered_set<int> v1, v2, v3;  
unordered_set<int>::iterator iter;  
  
v1.insert(10);  
  
cout << "v1 = " ;  
for (iter = v1.begin(); iter != v1.end(); iter++)  
cout << *iter << " ";  
cout << endl;  
  
v2 = v1;  
cout << "v2 = ";  
for (iter = v2.begin(); iter != v2.end(); iter++)  
cout << *iter << " ";  
cout << endl;  
  
// move v1 into v2  
v2.clear();  
v2 = move(v1);  
cout << "v2 = ";  
for (iter = v2.begin(); iter != v2.end(); iter++)  
cout << *iter << " ";  
cout << endl;  
}  
  
```  
  
##  <a name="a-nameunorderedsetpointera--unorderedsetpointer"></a><a name="unordered_set__pointer"></a>  unordered_set::pointer  
 Тип указателя на элемент.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве указателя на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_pointer.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::iterator it = c1.begin();  
it != c1.end(); ++it)  
{  
Myset::key_type key = *it;  
Myset::pointer p = &key;  
std::cout << " [" << *p << "]";  
}  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="a-nameunorderedsetreferencea--unorderedsetreference"></a><a name="unordered_set__reference"></a>  unordered_set::reference  
 Тип ссылки на элемент.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_reference.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::iterator it = c1.begin();  
it != c1.end(); ++it)  
{  
Myset::key_type key = *it;  
Myset::reference ref = key;  
std::cout << " [" << ref << "]";  
}  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="a-nameunorderedsetrehasha--unorderedsetrehash"></a><a name="unordered_set__rehash"></a>  unordered_set::rehash  
 Повторно создает хэш-таблицу.  
  
```  
void rehash(size_type nbuckets);
```  
  
### <a name="parameters"></a>Параметры  
 `nbuckets`  
 Требуемое число сегментов.  
  
### <a name="remarks"></a>Примечания  
 Функция-член устанавливает число сегментов не менее `nbuckets` и при необходимости перестраивает хэш-таблицу.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_rehash.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// inspect current parameters  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// change max_load_factor and redisplay  
c1.max_load_factor(0.10f);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
std::cout << std::endl;  
  
// rehash and redisplay  
c1.rehash(100);  
std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedsetsizea--unorderedsetsize"></a><a name="unordered_set__size"></a>  unordered_set::size  
 Подсчитывает количество элементов.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// clear the container and reinspect  
c1.clear();  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
std::cout << std::endl;  
  
c1.insert('d');  
c1.insert('e');  
  
// display contents " [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
std::cout << "size == " << c1.size() << std::endl;  
std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
size == 0  
empty() == true  
  
[e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedsetsizetypea--unorderedsetsizetype"></a><a name="unordered_set__size_type"></a>  unordered_set::size_type  
 Тип беззнакового расстояния между двумя элементами.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Он описан как синоним для типа `T2`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_size_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
Myset::size_type sz = c1.size();  
  
std::cout << "size == " << sz << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
size == 0  
```  
  
##  <a name="a-nameunorderedsetswapa--unorderedsetswap"></a><a name="unordered_set__swap"></a>  unordered_set::swap  
 Меняет местами содержимое двух контейнеров.  
  
```  
void swap(unordered_set& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Контейнер для замены.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности в `*this` и `right`. Если используется функция [unordered_set::get_allocator](#unordered_set__get_allocator)`() == right.get_allocator()`, она делает это в постоянном времени, создает исключение только в результате копирования сохраненного объекта признаков типа `Tr` и не делает недействительными ссылки, указатели или итераторы, которые указывают на элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_swap.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
Myset c2;  
  
c2.insert('d');  
c2.insert('e');  
c2.insert('f');  
  
c1.swap(c2);  
  
// display contents " [f] [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
swap(c1, c2);  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
  
```  
  
##  <a name="a-nameunorderedsetunorderedseta--unorderedsetunorderedset"></a><a name="unordered_set__unordered_set"></a>  unordered_set::unordered_set  
 Создает объект контейнера.  
  
```  
 
unordered_set(
const unordered_set& Right);

explicit unordered_set(
size_typebucket_count = N0,  
const Hash& Hash = Hash(),  
const Comp& Comp = Comp(),  
const Allocator& Al = Alloc());

unordered_set(
unordered_set&& Right);

unordered_set(
initializer_list<Type> IList);

unordered_set(
initializer_list<Type> IList, size_typebucket_count);

unordered_set(
initializer_list<Type> IList,  
size_typebucket_count,  
const Hash& Hash);

unordered_set(
initializer_list<Type> IList,  
size_typebucket_count,  
const Hash& Hash,  
const Comp& Comp);

unordered_set(
initializer_list<Type> IList,  
size_typebucket_count,  
const Hash& Hash,  
const Comp& Comp,  
const Allocator& Al);

template <class InputIterator>  
unordered_set(
InputIteratorfirst,  
InputIteratorlast,  
size_typebucket_count = N0,  
const Hash& Hash = Hash(),  
const Comp& Comp = Comp(),  
const Allocator& Al = Alloc());
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`InputIterator`|Тип итератора.|  
|`Al`|Объект распределителя для сохранения.|  
|`Comp`|Объект функции сравнения для сохранения.|  
|`Hash`|Объект хэш-функции для сохранения.|  
|`bucket_count`|Минимальное количество блоков.|  
|`Right`|Контейнер для копирования.|  
|`IList`|Объект initializer_list, содержащий копируемые элементы.|  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор определяет копию последовательности, управляемой `Right`. Второй конструктор определяет управляемую пустую последовательность. Третий конструктор задает копию последовательности путем перемещения `Right`. Конструкторы с четвертого по восьмой используют initializer_list для указания копируемых элементов. Девятый конструктор добавляет последовательность значений элементов `[first, last)`.  
  
 Все конструкторы также инициализируют ряд сохраненных значений. Для конструктора копии значения извлекаются из элемента `Right`. В противном случае:  
  
 Минимальное число блоков указывается в аргументе `bucket_count`, если он существует; в противном случае это значение по умолчанию, представленное здесь как значение `N0`, определенное реализацией.  
  
 Объект хэш-функции — это аргумент `Hash`, если он существует; в противном случае это `Hash()`.  
  
 Объект функции сравнения — это аргумент `Comp`, если он существует; в противном случае это `Comp()`.  
  
 Объект функции распределителя — это аргумент `Al`, если он существует; в противном случае это `Alloc()`.  
  
##  <a name="a-nameunorderedsetvaluetypea--unorderedsetvaluetype"></a><a name="unordered_set__value_type"></a>  unordered_set::value_type  
 Тип элемента.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  Â  
  
```  
  
// std__unordered_set__unordered_set_value_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
// add a value and reinspect  
Myset::key_type key = 'd';  
Myset::value_type val = key;  
c1.insert(val);  
  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[d] [c] [b] [a]  
  
```  
  
## <a name="see-also"></a>См. также  
 [<unordered_set>](../standard-library/unordered-set.md)   
 [Контейнеры](../cpp/containers-modern-cpp.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


