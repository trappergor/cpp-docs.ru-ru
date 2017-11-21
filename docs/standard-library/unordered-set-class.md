---
title: "Класс unordered_set | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_set/std::unordered_set
- unordered_set/std::unordered_set::allocator_type
- unordered_set/std::unordered_set::const_iterator
- unordered_set/std::unordered_set::const_local_iterator
- unordered_set/std::unordered_set::const_pointer
- unordered_set/std::unordered_set::const_reference
- unordered_set/std::unordered_set::difference_type
- unordered_set/std::unordered_set::hasher
- unordered_set/std::unordered_set::iterator
- unordered_set/std::unordered_set::key_equal
- unordered_set/std::unordered_set::key_type
- unordered_set/std::unordered_set::local_iterator
- unordered_set/std::unordered_set::pointer
- unordered_set/std::unordered_set::reference
- unordered_set/std::unordered_set::size_type
- unordered_set/std::unordered_set::value_type
- unordered_set/std::unordered_set::begin
- unordered_set/std::unordered_set::bucket
- unordered_set/std::unordered_set::bucket_count
- unordered_set/std::unordered_set::bucket_size
- unordered_set/std::unordered_set::cbegin
- unordered_set/std::unordered_set::cend
- unordered_set/std::unordered_set::clear
- unordered_set/std::unordered_set::count
- unordered_set/std::unordered_set::emplace
- unordered_set/std::unordered_set::emplace_hint
- unordered_set/std::unordered_set::empty
- unordered_set/std::unordered_set::end
- unordered_set/std::unordered_set::equal_range
- unordered_set/std::unordered_set::erase
- unordered_set/std::unordered_set::find
- unordered_set/std::unordered_set::get_allocator
- unordered_set/std::unordered_set::hash
- unordered_set/std::unordered_set::insert
- unordered_set/std::unordered_set::key_eq
- unordered_set/std::unordered_set::load_factor
- unordered_set/std::unordered_set::max_bucket_count
- unordered_set/std::unordered_set::max_load_factor
- unordered_set/std::unordered_set::max_size
- unordered_set/std::unordered_set::rehash
- unordered_set/std::unordered_set::size
- unordered_set/std::unordered_set::swap
- unordered_set/std::unordered_set::unordered_set
- unordered_set/std::unordered_set::operator=
- unordered_set/std::unordered_set::hash_function
dev_langs: C++
helpviewer_keywords:
- std::unordered_set
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
- std::unordered_set::unordered_set
- std::unordered_set::operator=
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash_function
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dfc07d8cd923b945c04c8fb9a89e7f8ee8af1316
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[allocator_type](#allocator_type)|Тип распределителя для управления хранилищем.|  
|[const_iterator](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|  
|[const_local_iterator](#const_local_iterator)|Тип постоянного итератора блока для управляемой последовательности.|  
|[const_pointer](#const_pointer)|Тип постоянного указателя на элемент.|  
|[const_reference](#const_reference)|Тип постоянной ссылки на элемент.|  
|[difference_type](#difference_type)|Тип расстояния со знаком между двумя элементами.|  
|[hasher](#hasher)|Тип хэш-функции.|  
|[iterator](#iterator)|Тип итератора для управляемой последовательности.|  
|[key_equal](#key_equal)|Тип функции сравнения.|  
|[key_type](#key_type)|Тип ключа упорядочения.|  
|[local_iterator](#local_iterator)|Тип итератора блока для управляемой последовательности.|  
|[pointer](#pointer)|Тип указателя на элемент.|  
|[reference](#reference)|Тип ссылки на элемент.|  
|[size_type](#size_type)|Тип беззнакового расстояния между двумя элементами.|  
|[value_type](#value_type)|Тип элемента.|  
  
|||  
|-|-|  
|Функция-член|Описание|  
|[begin](#begin)|Задает начало управляемой последовательности.|  
|[контейнеров](#bucket)|Получает номер блока для значения ключа.|  
|[bucket_count](#bucket_count)|Получает количество блоков.|  
|[bucket_size](#bucket_size)|Получает размер блока.|  
|[cbegin](#cbegin)|Задает начало управляемой последовательности.|  
|[cend](#cend)|Задает конец управляемой последовательности.|  
|[clear](#clear)|Удаляет все элементы.|  
|[count](#count)|Определяет количество элементов, соответствующих заданному ключу.|  
|[emplace](#emplace)|Добавляет элемент, созданный на месте.|  
|[emplace_hint](#emplace_hint)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[empty](#empty)|Проверяет отсутствие элементов.|  
|[end](#end)|Задает конец управляемой последовательности.|  
|[equal_range](#equal_range)|Находит диапазон, соответствующий указанному ключу.|  
|[erase](#erase)|Удаляет элементы в указанных позициях.|  
|[find](#find)|Определяет элемент, соответствующий указанному ключу.|  
|[get_allocator](#get_allocator)|Возвращает сохраненный объект распределителя.|  
|[hash_function](#hash)|Получает сохраненный объект хэш-функции.|  
|[insert](#insert)|Добавляет элементы.|  
|[key_eq](#key_eq)|Получает сохраненный объект функции сравнения.|  
|[load_factor](#load_factor)|Подсчитывает среднее число элементов в блоке.|  
|[max_bucket_count](#max_bucket_count)|Получает максимальное количество блоков.|  
|[max_load_factor](#max_load_factor)|Возвращает или задает максимальное количество элементов в блоке.|  
|[max_size](#max_size)|Возвращает максимальный размер управляемой последовательности.|  
|[rehash](#rehash)|Повторно создает хэш-таблицу.|  
|[size](#size)|Подсчитывает количество элементов.|  
|[swap](#swap)|Меняет местами содержимое двух контейнеров.|  
|[unordered_set](#unordered_set)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Операторы|Описание|  
|[unordered_set::operator=](#op_eq)|Копирует хэш-таблицу.|  
  
## <a name="remarks"></a>Примечания  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов — объекта функции сравнения типа [unordered_set::key_equal](#key_equal) и объекта хэш-функции типа [unordered_set::hasher](#hasher). Доступ к первому сохраненному объекту можно получить, вызвав функцию-член [unordered_set::key_eq](#key_eq)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции-члена [unordered_set::hash_function](#hash)`()`. В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`. В отличие от шаблона класса[класс unordered_multiset](../standard-library/unordered-multiset-class.md), объект класса шаблона `unordered_set` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов в управляемой последовательности. (Ключи уникальны).  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке. Если вставка элемента приводит к тому, что значение [unordered_set::load_factor](#load_factor)`()` превышает максимальный коэффициент нагрузки, контейнер увеличивает количество блоков и перестраивает хэш-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков. Обычно невозможно предсказать порядок элементов в управляемой последовательности. Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered_set::allocator_type](#allocator_type). Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`. Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<unordered_set>  
  
 **Пространство имен:** std  
  
##  <a name="allocator_type"></a>  unordered_set::allocator_type  
 Тип распределителя для управления хранилищем.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Alloc`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="begin"></a>  unordered_set::begin  
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
  
##  <a name="bucket"></a>  unordered_set::bucket  
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
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="bucket_count"></a>  unordered_set::bucket_count  
 Получает количество блоков.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает текущее число блоков.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="bucket_size"></a>  unordered_set::bucket_size  
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
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="cbegin"></a>  unordered_set::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор прямого доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 isContainer<T>::iterator  
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator  
```  
  
##  <a name="cend"></a>  unordered_set::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор `const` прямого доступа, который указывает на позицию сразу за концом диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `end()` и `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 isContainer<T>::iterator  
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.  
  
##  <a name="clear"></a>  unordered_set::clear  
 Удаляет все элементы.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает [unordered_set::erase](#erase)`(` [unordered_set::begin](#begin)`(),` [unordered_set::end](#end)`())`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_iterator"></a>  unordered_set::const_iterator  
 Тип постоянного итератора для управляемой последовательности.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа `T1`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
    std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="const_local_iterator"></a>  unordered_set::const_local_iterator  
 Тип постоянного итератора блока для управляемой последовательности.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного прямого итератора для блока. Он описан здесь как синоним для типа `T5`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_pointer"></a>  unordered_set::const_pointer  
 Тип постоянного указателя на элемент.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_reference"></a>  unordered_set::const_reference  
 Тип постоянной ссылки на элемент.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="count"></a>  unordered_set::count  
 Определяет количество элементов, соответствующих заданному ключу.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число элементов в диапазоне, ограниченном [unordered_set::equal_range](#equal_range)`(keyval)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="difference_type"></a>  unordered_set::difference_type  
 Тип расстояния со знаком между двумя элементами.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Он описан здесь как синоним для типа `T3`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // compute positive difference  
    Myset::difference_type diff = 0;  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        ++diff;  
    std::cout << "end()-begin() == " << diff << std::endl;  
      
    // compute negative difference  
    diff = 0;  
    for (Myset::const_iterator it = c1.end(); it != c1.begin(); --it)  
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
  
##  <a name="emplace"></a>  unordered_set::emplace  
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
  
 Пример кода см. в разделе [set::emplace](../standard-library/set-class.md#emplace).  
  
##  <a name="emplace_hint"></a>  unordered_set::emplace_hint  
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
  
 Пример кода см. в разделе [set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
##  <a name="empty"></a>  unordered_set::empty  
 Проверяет отсутствие элементов.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="end"></a>  unordered_set::end  
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
 Первые две функции-члены возвращают прямой итератор, указывающий на место сразу за концом последовательности. Последние две функции-члена возвращают прямой итератор, указывающий на место сразу за концом контейнера `nbucket`.  
  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="equal_range"></a>  unordered_set::equal_range  
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
 Функция-член возвращает пару итераторов `X` таким образом, что`[X.first, X.second)` отделяет только те элементы управляемой последовательности, которые имеют эквивалентное упорядочение с `keyval`. Если таких элементов не существует, оба итератора имеют значение `end()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="erase"></a>  unordered_set::erase  
 Удаляет элемент или диапазон элементов в объекте unordered_set с заданных позиций или удаляет элементы, соответствующие заданному ключу.  
  
```  
iterator erase(const_iterator Where);

iterator erase(const_iterator First, const_iterator Last);

size_type erase(const key_type& Key);
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
 Пример кода см. в разделе [set::erase](../standard-library/set-class.md#erase).  
  
##  <a name="find"></a>  unordered_set::find  
 Определяет элемент, соответствующий указанному ключу.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `keyval`  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [unordered_set::equal_range](#equal_range)`(keyval).first`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="get_allocator"></a>  unordered_set::get_allocator  
 Возвращает сохраненный объект распределителя.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект распределителя.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="hash"></a>  unordered_set::hash_function  
 Получает сохраненный объект хэш-функции.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект хэш-функции.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="hasher"></a>  unordered_set::hasher  
 Тип хэш-функции.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Hash`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="insert"></a>  unordered_set::insert  
 Вставляет элемент или диапазон элементов в unordered_set.  
  
```  
// (1) single element  
pair<iterator, bool> insert(const value_type& Val);
  
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool> insert(ValTy&& Val);
 
// (3) single element with hint  
iterator insert(const_iterator Where, const value_type& Val);
 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(const_iterator Where, ValTy&& Val);
 
// (5) range  
template <class InputIterator>  
void insert(InputIterator First, InputIterator Last);
 
// (6) initializer list  
void insert(initializer_list<value_type> IList);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Val`|Значение элемента, вставляемого в unordered_set, если оно уже не содержит элемент, ключ которого эквивалентно упорядочен.|  
|`Where`|Место начала поиска правильной точки вставки.|  
|`ValTy`|Параметр шаблона, определяющий тип аргумента, unordered_set можно использовать для создания элемента[value_type](../standard-library/map-class.md#value_type)и точно пересылает `Val` в качестве аргумента.|  
|`First`|Позиция первого элемента, который следует скопировать.|  
|`Last`|Позиция непосредственно перед последним элементом, который следует скопировать.|  
|`InputIterator`|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).|  
|`IList`|Объект [initializer_list](../standard-library/initializer-list.md), из которого копируются элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функции-члены одноэлементные, (1) и (2) возвращают[пары](../standard-library/pair-structure.md) которого `bool` компонент является значение true, если была осуществлена вставка и значение false, если unordered_set уже содержало элемент, ключ которого эквивалентное значение в упорядочение. Компонент итератора пары возвращаемых значений указывает на вставленный элемент, если значение компонента `bool` равно true, или на существующий элемент, если значение компонента `bool` равно false.  
  
 Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, который указывает на позицию, где новый элемент был вставлен, или, если элемент с эквивалентным ключом уже существует, указывает на существующий элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает никакие итераторы, указатели или ссылки недействительными.  
  
 Если исключение вызывается во время вставки одного элемента, но оно не вызывается в хэш-функции контейнера, состояние контейнера не изменяется. Если исключение вызывается в хэш-функции, результат не определен. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.  
  
 Для доступа к компоненту итератора `pair` `pr` , возвращаемые функциями-членами, используйте `pr.first`; для разыменования итератора в возвращенной паре используйте`*pr.first`, предоставляя элемент. Для доступа к компоненту `bool` используйте `pr.second`. См. пример кода далее в этой статье.  
  
 [Value_type](../standard-library/map-class.md#value_type) контейнер — это определение, к которому относится к контейнеру, а для набора, `unordered_set<V>::value_type` — тип `const V`.  
  
 Функция-член с диапазоном (5) вставляет последовательность значений элементов в unordered_set, соответствующее каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `s.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `s`. Вставляются только элементы с уникальными значениями в диапазоне. Повторяющиеся значения игнорируются. Чтобы увидеть, какие элементы отклонены, используйте одноэлементные версии `insert`.  
  
 Функция — член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в unordered_set.  
  
 Для вставки элемента, созданный на месте — то есть, без копирования или перемещения операций, — в разделе[set::emplace](../standard-library/set-class.md#emplace) и[set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
 Пример кода см. в разделе [set::insert](../standard-library/set-class.md#insert).  
  
##  <a name="iterator"></a>  unordered_set::iterator  
 Тип, предоставляющий [прямой итератор](../standard-library/forward-iterator-tag-struct.md) константы, может считывать элементы в объекте unordered_set.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования **итератора** в разделе [begin](../standard-library/set-class.md#begin).  
  
##  <a name="key_eq"></a>  unordered_set::key_eq  
 Получает сохраненный объект функции сравнения.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает сохраненный объект функции сравнения.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="key_equal"></a>  unordered_set::key_equal  
 Тип функции сравнения.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Pred`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="key_type"></a>  unordered_set::key_type  
 Тип ключа упорядочения.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Key`.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [d] [c] [b] [a]  
```  
  
##  <a name="load_factor"></a>  unordered_set::load_factor  
 Подсчитывает среднее число элементов в блоке.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `(float)`[unordered_set::size](#size)`() / (float)`[unordered_set::bucket_count](#bucket_count)`()`, среднее количество элементов на блок.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="local_iterator"></a>  unordered_set::local_iterator  
 Тип итератора контейнера.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве прямого итератора для контейнера. Он описан здесь как синоним для типа `T4`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_bucket_count"></a>  unordered_set::max_bucket_count  
 Получает максимальное количество блоков.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает максимальное количество блоков, которое разрешено в настоящее время.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_load_factor"></a>  unordered_set::max_load_factor  
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
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_size"></a>  unordered_set::max_size  
 Возвращает максимальный размер управляемой последовательности.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="op_eq"></a>  unordered_set::operator=  
 Копирует хэш-таблицу.  
  
```  
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`right`|[Unordered_set](../standard-library/unordered-set-class.md) копируемый в `unordered_set`.|  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в объекте `unordered_set` `operator=` копирует или перемещает содержимое `right` в объект `unordered_set`.  
  
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
  
##  <a name="pointer"></a>  unordered_set::pointer  
 Тип указателя на элемент.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве указателя на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="reference"></a>  unordered_set::reference  
 Тип ссылки на элемент.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="rehash"></a>  unordered_set::rehash  
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
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="size"></a>  unordered_set::size  
 Подсчитывает количество элементов.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="size_type"></a>  unordered_set::size_type  
 Тип беззнакового расстояния между двумя элементами.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Он описан здесь как синоним для типа `T2`, определяемого реализацией.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="swap"></a>  unordered_set::swap  
 Меняет местами содержимое двух контейнеров.  
  
```  
void swap(unordered_set& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Контейнер для замены.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `*this` и `right`. Если [unordered_set::get_allocator](#get_allocator)`() == right.get_allocator()`, она делает это в константном времени, создает исключение только в результате копирования сохраненного объекта признаков типа `Tr`, и не делает не ссылки, указатели, или итераторы, которые указывают элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    Myset c2;  
      
    c2.insert('d');  
    c2.insert('e');  
    c2.insert('f');  
      
    c1.swap(c2);  
      
    // display contents " [f] [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    swap(c1, c2);  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="unordered_set"></a>  unordered_set::unordered_set  
 Создает объект контейнера.  
  
```  
unordered_set(const unordered_set& Right);

explicit unordered_set(
    size_typebucket_count = N0,  
    const Hash& Hash = Hash(),  
    const Comp& Comp = Comp(),  
    const Allocator& Al = Alloc());

unordered_set(unordered_set&& Right);

unordered_set(initializer_list<Type> IList);

unordered_set(initializer_list<Type> IList, size_typebucket_count);

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
  
 Минимальное число блоков — это аргумент `bucket_count`, если он существует; в противном случае это значение по умолчанию, представленное здесь как значение `N0`, определенное реализацией.  
  
 Объект хэш-функции — это аргумент `Hash`, если он существует; в противном случае это `Hash()`.  
  
 Объект функции сравнения — это аргумент `Comp`, если он существует; в противном случае это `Comp()`.  
  
 Объект функции распределителя — это аргумент `Al`, если он существует; в противном случае это `Alloc()`.  
  
##  <a name="value_type"></a>  unordered_set::value_type  
 Тип элемента.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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

