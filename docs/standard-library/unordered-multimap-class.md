---
title: Класс unordered_multimap | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- unordered_map/std::unordered_multimap
- unordered_map/std::unordered_multimap::allocator_type
- unordered_map/std::unordered_multimap::const_iterator
- unordered_map/std::unordered_multimap::const_local_iterator
- unordered_map/std::unordered_multimap::const_pointer
- unordered_map/std::unordered_multimap::const_reference
- unordered_map/std::unordered_multimap::difference_type
- unordered_map/std::unordered_multimap::hasher
- unordered_map/std::unordered_multimap::iterator
- unordered_map/std::unordered_multimap::key_equal
- unordered_map/std::unordered_multimap::key_type
- unordered_map/std::unordered_multimap::local_iterator
- unordered_map/std::unordered_multimap::mapped_type
- unordered_map/std::unordered_multimap::pointer
- unordered_map/std::unordered_multimap::reference
- unordered_map/std::unordered_multimap::size_type
- unordered_map/std::unordered_multimap::value_type
- unordered_map/std::unordered_multimap::begin
- unordered_map/std::unordered_multimap::bucket
- unordered_map/std::unordered_multimap::bucket_count
- unordered_map/std::unordered_multimap::bucket_size
- unordered_map/std::unordered_multimap::cbegin
- unordered_map/std::unordered_multimap::cend
- unordered_map/std::unordered_multimap::clear
- unordered_map/std::unordered_multimap::count
- unordered_map/std::unordered_multimap::emplace
- unordered_map/std::unordered_multimap::emplace_hint
- unordered_map/std::unordered_multimap::empty
- unordered_map/std::unordered_multimap::end
- unordered_map/std::unordered_multimap::equal_range
- unordered_map/std::unordered_multimap::erase
- unordered_map/std::unordered_multimap::find
- unordered_map/std::unordered_multimap::get_allocator
- unordered_map/std::unordered_multimap::hash
- unordered_map/std::unordered_multimap::insert
- unordered_map/std::unordered_multimap::key_eq
- unordered_map/std::unordered_multimap::load_factor
- unordered_map/std::unordered_multimap::max_bucket_count
- unordered_map/std::unordered_multimap::max_load_factor
- unordered_map/std::unordered_multimap::max_size
- unordered_map/std::unordered_multimap::rehash
- unordered_map/std::unordered_multimap::size
- unordered_map/std::unordered_multimap::swap
- unordered_map/std::unordered_multimap::unordered_multimap
- unordered_map/std::unordered_multimap::operator=
- unordered_map/std::unordered_multimap::hash_function
dev_langs:
- C++
helpviewer_keywords:
- std::unordered_multimap
- std::unordered_multimap::allocator_type
- std::unordered_multimap::const_iterator
- std::unordered_multimap::const_local_iterator
- std::unordered_multimap::const_pointer
- std::unordered_multimap::const_reference
- std::unordered_multimap::difference_type
- std::unordered_multimap::hasher
- std::unordered_multimap::iterator
- std::unordered_multimap::key_equal
- std::unordered_multimap::key_type
- std::unordered_multimap::local_iterator
- std::unordered_multimap::mapped_type
- std::unordered_multimap::pointer
- std::unordered_multimap::reference
- std::unordered_multimap::size_type
- std::unordered_multimap::value_type
- std::unordered_multimap::begin
- std::unordered_multimap::bucket
- std::unordered_multimap::bucket_count
- std::unordered_multimap::bucket_size
- std::unordered_multimap::cbegin
- std::unordered_multimap::cend
- std::unordered_multimap::clear
- std::unordered_multimap::count
- std::unordered_multimap::emplace
- std::unordered_multimap::emplace_hint
- std::unordered_multimap::empty
- std::unordered_multimap::end
- std::unordered_multimap::equal_range
- std::unordered_multimap::erase
- std::unordered_multimap::find
- std::unordered_multimap::get_allocator
- std::unordered_multimap::hash
- std::unordered_multimap::insert
- std::unordered_multimap::key_eq
- std::unordered_multimap::load_factor
- std::unordered_multimap::max_bucket_count
- std::unordered_multimap::max_load_factor
- std::unordered_multimap::max_size
- std::unordered_multimap::rehash
- std::unordered_multimap::size
- std::unordered_multimap::swap
- std::unordered_multimap::unordered_multimap
- std::unordered_multimap::operator=
- std::unordered_multimap::allocator_type
- std::unordered_multimap::const_iterator
- std::unordered_multimap::const_local_iterator
- std::unordered_multimap::const_pointer
- std::unordered_multimap::const_reference
- std::unordered_multimap::difference_type
- std::unordered_multimap::hasher
- std::unordered_multimap::iterator
- std::unordered_multimap::key_equal
- std::unordered_multimap::key_type
- std::unordered_multimap::local_iterator
- std::unordered_multimap::mapped_type
- std::unordered_multimap::pointer
- std::unordered_multimap::reference
- std::unordered_multimap::size_type
- std::unordered_multimap::value_type
- std::unordered_multimap::begin
- std::unordered_multimap::bucket
- std::unordered_multimap::bucket_count
- std::unordered_multimap::bucket_size
- std::unordered_multimap::cbegin
- std::unordered_multimap::cend
- std::unordered_multimap::clear
- std::unordered_multimap::count
- std::unordered_multimap::emplace
- std::unordered_multimap::emplace_hint
- std::unordered_multimap::empty
- std::unordered_multimap::end
- std::unordered_multimap::equal_range
- std::unordered_multimap::erase
- std::unordered_multimap::find
- std::unordered_multimap::get_allocator
- std::unordered_multimap::hash_function
- std::unordered_multimap::insert
- std::unordered_multimap::key_eq
- std::unordered_multimap::load_factor
- std::unordered_multimap::max_bucket_count
- std::unordered_multimap::max_load_factor
- std::unordered_multimap::max_size
- std::unordered_multimap::rehash
- std::unordered_multimap::size
- std::unordered_multimap::swap
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c69d344276ef584ef20801395c62c8ed55567cb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="unorderedmultimap-class"></a>Класс unordered_multimap

Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `std::pair<const Key, Ty>` переменной длины. Последовательность слабо упорядочена хэш-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками. В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом. Каждый элемент содержит два объекта: ключ и значение сортировки. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности (постоянное время), по крайней мере, когда все блоки имеют примерно одинаковую длину. В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности (линейное время). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Ty,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<Key>>
class unordered_multimap;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`Key`|Тип ключа.|
|`Ty`|Сопоставленный тип.|
|`Hash`|Тип объекта хэш-функции.|
|`Pred`|Тип объекта функции сравнения на предмет равенства.|
|`Alloc`|Класс распределителя.|

## <a name="members"></a>Участники

|Определение типа|Описание|
|-|-|
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
|[mapped_type](#mapped_type)|Тип сопоставленного значения, связанного с каждым ключом.|
|[pointer](#pointer)|Тип указателя на элемент.|
|[reference](#reference)|Тип ссылки на элемент.|
|[size_type](#size_type)|Тип беззнакового расстояния между двумя элементами.|
|[value_type](#value_type)|Тип элемента.|

|Функция-член|Описание|
|-|-|
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
|[unordered_multimap](#unordered_multimap)|Создает объект контейнера.|

|Оператор|Описание|
|-|-|
|[unordered_multimap::operator=](#op_eq)|Копирует хэш-таблицу.|

## <a name="remarks"></a>Примечания

Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов — объекта функции сравнения типа [unordered_multimap::key_equal](#key_equal) и объекта хэш-функции типа [unordered_multimap::hasher](#hasher). Доступ к первому сохраненному объекту можно получить, вызвав функцию-член [unordered_multimap::key_eq](#key_eq)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции-члена [unordered_multimap::hash_function](#hash)`()`. В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`. В отличие от шаблонного класса [unordered_map](../standard-library/unordered-map-class.md) объект шаблонного класса `unordered_multimap` не гарантирует, что `key_eq()(X, Y)` всегда будет иметь значение false для любых двух элементов управляемой последовательности. (Ключи не обязательно должны быть уникальными.)

Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке. Если вставка элемента приводит к тому, что значение [unordered_multimap::load_factor](#load_factor)`()` превышает максимальный коэффициент нагрузки, контейнер увеличивает количество блоков и перестраивает хэш-таблицу по мере необходимости.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков. Обычно невозможно предсказать порядок элементов в управляемой последовательности. Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.

Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя, который имеет тип [unordered_multimap::allocator_type](#allocator_type). Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`. Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.

## <a name="requirements"></a>Требования

**Заголовок:** \<unordered_map>

**Пространство имен:** std

## <a name="allocator_type"></a>  unordered_multimap::allocator_type

Тип распределителя для управления хранилищем.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Alloc`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_allocator_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
    {
    Mymap c1;

    Mymap::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
    }

```

```Output
al == std::allocator() is true
```

## <a name="begin"></a>  unordered_multimap::begin

Задает начало управляемой последовательности или сегмента.

```cpp
iterator begin();

const_iterator begin() const;


local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`nbucket`|Номер сегмента.|

### <a name="remarks"></a>Примечания

Первые две функции-члены возвращают прямой итератор, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности). Последние две функции-члены возвращают прямой итератор, указывающий на первый элемент сегмента `nbucket` (или на место сразу за концом пустого сегмента).

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_begin.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect first two items " [c 3] [b 2]"
    Mymap::iterator it2 = c1.begin();
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    ++it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[c, 3] [b, 2]
[a, 1]
```

## <a name="bucket"></a>  unordered_multimap::bucket

Получает номер блока для значения ключа.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

`keyval` Значение ключа для сопоставления.

### <a name="remarks"></a>Примечания

Функция-член возвращает номер контейнера, который в настоящий момент соответствует значению ключа `keyval`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_bucket.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display buckets for keys
    Mymap::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="bucket_count"></a>  unordered_multimap::bucket_count

Получает количество блоков.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает текущее число блоков.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
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
 [c, 3] [b, 2] [a, 1]
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

## <a name="bucket_size"></a>  unordered_multimap::bucket_size

Получает размер сегмента.

```cpp
size_type bucket_size(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

`nbucket` Номер сегмента.

### <a name="remarks"></a>Примечания

Функции-члены возвращают размер номера сегмента `nbucket`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_bucket_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display buckets for keys
    Mymap::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="cbegin"></a>  unordered_multimap::cbegin

Возвращает итератор `const`, направленный на первый элемент в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор прямого доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).

### <a name="remarks"></a>Примечания

Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере `Container` следует рассматривать как изменяемый (не-`const`) контейнер любого вида, который поддерживает `begin()` и `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  unordered_multimap::cend

Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор `const` прямого доступа, который указывает на позицию сразу за концом диапазона.

### <a name="remarks"></a>Примечания

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере `Container` следует рассматривать как изменяемый (не-`const`) контейнер любого вида, который поддерживает `end()` и `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="clear"></a>  unordered_multimap::clear

Удаляет все элементы.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член вызывает [unordered_multimap::erase](#erase) `(` [unordered_multimap::begin](#begin) `(),` [unordered_multimap::end](#end)`())`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_clear.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="const_iterator"></a>  unordered_multimap::const_iterator

Тип постоянного итератора для управляемой последовательности.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа `T1`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_const_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="const_local_iterator"></a>  unordered_multimap::const_local_iterator

Тип постоянного итератора блока для управляемой последовательности.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который можно использовать в качестве постоянного прямого итератора для блока. Он описан здесь как синоним для типа `T5`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1]
```

## <a name="const_pointer"></a>  unordered_multimap::const_pointer

Тип постоянного указателя на элемент.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_const_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::const_pointer p = &*it;
        std::cout << " [" << p->first << ", " << p->second << "]";
        }
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="const_reference"></a>  unordered_multimap::const_reference

Тип постоянной ссылки на элемент.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_const_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::const_reference ref = *it;
        std::cout << " [" << ref.first << ", " << ref.second << "]";
        }
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="count"></a>  unordered_multimap::count

Определяет количество элементов, соответствующих заданному ключу.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

`keyval` Значение ключа для поиска.

### <a name="remarks"></a>Примечания

Функция-член возвращает число элементов в диапазоне, ограниченном [unordered_multimap::equal_range](#equal_range)`(keyval)`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "count('A') == " << c1.count('A') << std::endl;
    std::cout << "count('b') == " << c1.count('b') << std::endl;
    std::cout << "count('C') == " << c1.count('C') << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
count('A') == 0
count('b') == 1
count('C') == 0
```

## <a name="difference_type"></a>  unordered_multimap::difference_type

Тип расстояния со знаком между двумя элементами.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Примечания

Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Он описан здесь как синоним для типа `T3`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_difference_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// compute positive difference
    Mymap::difference_type diff = 0;
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

// compute negative difference
    diff = 0;
    for (Mymap::const_iterator it = c1.end();
        it != c1.begin(); --it)
        --diff;
    std::cout << "begin()-end() == " << diff << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
end()-begin() == 3
begin()-end() == -3
```

## <a name="emplace"></a>  unordered_multimap::emplace

Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются) с подсказкой размещения.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`args`|Аргументы, передаваемые для создания элемента, который будет вставлен в объект unordered_multimap.|

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Примечания

Эта функция не делает недействительными ссылки на элементы контейнера, но она может сделать недействительными все итераторы контейнера.

Значение [value_type](../standard-library/map-class.md#value_type) элемента — это пара. Таким образом, значение элемента будет упорядоченной парой, в которой первый компонент равен значению ключа, а второй компонент — значению данных элемента.

Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

Пример кода см. в разделе [multimap::emplace](../standard-library/multimap-class.md#emplace).

## <a name="emplace_hint"></a>  unordered_multimap::emplace_hint

Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются) с подсказкой размещения.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`args`|Аргументы, передаваемые для создания элемента, который будет вставлен в объект unordered_multimap.|
|`where`|Подсказка о месте начала поиска правильной точки вставки.|

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Примечания

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

[value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

Пример кода см. в разделе [map::emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="empty"></a>  unordered_multimap::empty

Проверяет отсутствие элементов.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_empty.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="end"></a>  unordered_multimap::end

Задает конец управляемой последовательности.

```cpp
iterator end();

const_iterator end() const;


local_iterator end(size_type nbucket);

const_local_iterator end(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`nbucket`|Номер сегмента.|

### <a name="remarks"></a>Примечания

Первые две функции-члены возвращают прямой итератор, указывающий на место сразу за концом последовательности. Последние две функции-члена возвращают прямой итератор, указывающий на место сразу за концом контейнера `nbucket`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_end.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect last two items " [a 1] [b 2]"
    Mymap::iterator it2 = c1.end();
    --it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    --it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.end(c1.bucket('a'));
    --lit;
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1] [b, 2]
[a, 1]
```

## <a name="equal_range"></a>  unordered_multimap::equal_range

Находит диапазон, соответствующий указанному ключу.

```cpp
std::pair<iterator, iterator>
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>
    equal_range(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

`keyval` Значение ключа для поиска.

### <a name="remarks"></a>Примечания

Функция-член возвращает пару итераторов `X` , таких, что `[X.first, X.second)` отделяет только те элементы управляемой последовательности, которые имеют эквивалентное упорядочение с `keyval`. Если таких элементов не существует, оба итератора имеют значение `end()`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_equal_range.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display results of failed search
    std::pair<Mymap::iterator, Mymap::iterator> pair1 =
        c1.equal_range('x');
    std::cout << "equal_range('x'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << " [" << pair1.first->first
            << ", " << pair1.first->second << "]";
    std::cout << std::endl;

// display results of successful search
    pair1 = c1.equal_range('b');
    std::cout << "equal_range('b'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << " [" << pair1.first->first
            << ", " << pair1.first->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
equal_range('x'):
equal_range('b'): [b, 2]
```

## <a name="erase"></a>  unordered_multimap::erase

Удаляет элемент или диапазон элементов в объекте unordered_multimap с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,
    const_iterator Last);

size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>Параметры

`Where` Положение элемента, который требуется удалить.

`First` Положение первого элемента должны быть удалены.

`Last` Положение после последнего элемента должны быть удалены.

`Key` Значение ключа элементов должны быть удалены.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на последний элемент сопоставления, если такого элемента не существует.

Для третьей функции-члена возвращает число элементов, которые были удалены из объекта unordered_multimap.

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [map::erase](../standard-library/map-class.md#erase).

## <a name="find"></a>  unordered_multimap::find

Определяет элемент, соответствующий указанному ключу.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

`keyval` Значение ключа для поиска.

### <a name="remarks"></a>Примечания

Функция-член возвращает [unordered_multimap::equal_range](#equal_range)`(keyval).first`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_find.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// try to find and fail
    std::cout << "find('A') == "
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;

// try to find and succeed
    Mymap::iterator it = c1.find('b');
    std::cout << "find('b') == "
        << std::boolalpha << (it != c1.end())
        << ": [" << it->first << ", " << it->second << "]" << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
find('A') == false
find('b') == true: [b, 2]
```

## <a name="get_allocator"></a>  unordered_multimap::get_allocator

Возвращает сохраненный объект распределителя.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает сохраненный объект распределителя.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_get_allocator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
    {
    Mymap c1;

    Mymap::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
    }

```

```Output
al == std::allocator() is true
```

## <a name="hash"></a>  unordered_multimap::hash_function

Получает сохраненный объект хэш-функции.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает сохраненный объект хэш-функции.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_hash_function.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
    }

```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="hasher"></a>  unordered_multimap::hasher

Тип хэш-функции.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Hash`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_hasher.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
    }

```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="insert"></a>  unordered_multimap::insert

Вставляет элемент или диапазон элементов в unordered_multimap.

```cpp
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

|Параметр|Описание|
|-|-|
|`Val`|Значение элемента, вставляемого в unordered_multimap.|
|`Where`|Место начала поиска правильной точки вставки.|
|`ValTy`|Параметр шаблона, определяющий тип аргумента, с помощью которого unordered_multimap формирует элемент типа [value_type](../standard-library/map-class.md#value_type) и точно пересылает `Val` как аргумент.|
|`First`|Позиция первого элемента, который следует скопировать.|
|`Last`|Позиция непосредственно перед последним элементом, который следует скопировать.|
|`InputIterator`|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).|
|`IList`|[initializer_list](../standard-library/initializer-list.md), из которого нужно скопировать элементы.|

### <a name="return-value"></a>Возвращаемое значение

Одноэлементные функции-члены (1) и (2) возвращают итератор в позиции, где был вставлен новый элемент.

Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, указывающий на позицию, где был вставлен новый элемент.

### <a name="remarks"></a>Примечания

Эта функция не делает никакие указатели или ссылки недействительными, но она может сделать недействительными все итераторы контейнера.

Если исключение вызывается во время вставки одного элемента, но оно не вызывается в хэш-функции контейнера, состояние контейнера не изменяется. Если исключение вызывается в хэш-функции, результат не определен. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

[value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, который принадлежит контейнеру. Для сопоставления `map<K, V>::value_type` — это `pair<const K, V>`. Значение элемента — это упорядоченная пара, в которой первый компонент эквивалентен значению ключа, а второй компонент — значению данных элемента.

Функция-член с диапазоном (5) вставляет последовательность значений элементов в unordered_multimap, соответствующее каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `m.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `m`.

Функция — член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в unordered_multimap.

Сведения о вставке элемента, созданного на месте (т. е. без выполнения операций копирования или перемещения), см. в описании функций [unordered_multimap::emplace](#emplace) и [unordered_multimap::emplace_hint](#emplace_hint).

Пример кода см. в разделе [multimap::find](../standard-library/multiset-class.md#insert).

## <a name="iterator"></a>  unordered_multimap::iterator

Тип итератора для управляемой последовательности.

```cpp
typedef T0 iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который можно использовать в качестве прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа `T0`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="key_eq"></a>  unordered_multimap::key_eq

Получает сохраненный объект функции сравнения.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает сохраненный объект функции сравнения.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_key_eq.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::key_equal cmpfn = c1.key_eq();
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

## <a name="key_equal"></a>  unordered_multimap::key_equal

Тип функции сравнения.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Pred`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_key_equal.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::key_equal cmpfn = c1.key_eq();
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

## <a name="key_type"></a>  unordered_multimap::key_type

Тип ключа упорядочения.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Key`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_key_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="load_factor"></a>  unordered_multimap::load_factor

Подсчитывает среднее число элементов в блоке.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает `(float)` [unordered_multimap::size](#size)`() / (float)`[unordered_multimap::bucket_count](#bucket_count)`()`, среднее количество элементов на сегмент.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
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

## <a name="local_iterator"></a>  unordered_multimap::local_iterator

Тип итератора контейнера.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который можно использовать в качестве прямого итератора для контейнера. Он описан здесь как синоним для типа `T4`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1]
```

## <a name="mapped_type"></a>  unordered_multimap::mapped_type

Тип сопоставленного значения, связанного с каждым ключом.

```cpp
typedef Ty mapped_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Ty`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_mapped_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="max_bucket_count"></a>  unordered_multimap::max_bucket_count

Получает максимальное количество блоков.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает максимальное количество блоков, которое разрешено в настоящее время.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
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
 [c, 3] [b, 2] [a, 1]
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

## <a name="max_load_factor"></a>  unordered_multimap::max_load_factor

Возвращает или задает максимальное количество элементов в блоке.

```cpp
float max_load_factor() const;


void max_load_factor(float factor);
```

### <a name="parameters"></a>Параметры

`factor` Новый коэффициент максимальной нагрузки.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член заменяет сохраненный коэффициент максимальной нагрузки `factor`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
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
 [c, 3] [b, 2] [a, 1]
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

## <a name="max_size"></a>  unordered_multimap::max_size

Возвращает максимальный размер управляемой последовательности.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_max_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    std::cout << "max_size() == " << c1.max_size() << std::endl;

    return (0);
    }

```

```Output
max_size() == 536870911
```

## <a name="op_eq"></a>  unordered_multimap::operator=

Копирует хэш-таблицу.

```cpp
unordered_multimap& operator=(const unordered_multimap& right);

unordered_multimap& operator=(unordered_multimap&& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`right`|unordered_multimap копируется в unordered_multimap.|

### <a name="remarks"></a>Примечания

После удаления всех существующих элементов из unordered_multimap `operator=` копирует или перемещает содержимое `right` в unordered_multimap.

### <a name="example"></a>Пример

```cpp
// unordered_multimap_operator_as.cpp
// compile with: /EHsc
#include <unordered_multimap>
#include <iostream>

int main( )
   {
   using namespace std;
   unordered_multimap<int, int> v1, v2, v3;
   unordered_multimap<int, int>::iterator iter;

   v1.insert(pair<int, int>(1, 10));

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;
   }
```

## <a name="pointer"></a>  unordered_multimap::pointer

Тип указателя на элемент.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который можно использовать в качестве указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::pointer p = &*it;
        std::cout << " [" << p->first << ", " << p->second << "]";
        }
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="reference"></a>  unordered_multimap::reference

Тип ссылки на элемент.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::reference ref = *it;
        std::cout << " [" << ref.first << ", " << ref.second << "]";
        }
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="rehash"></a>  unordered_multimap::rehash

Повторно создает хэш-таблицу.

```cpp
void rehash(size_type nbuckets);
```

### <a name="parameters"></a>Параметры

`nbuckets` Требуемое число контейнеров.

### <a name="remarks"></a>Примечания

Функция-член устанавливает число сегментов не менее `nbuckets` и при необходимости перестраивает хэш-таблицу.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_rehash.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
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
 [c, 3] [b, 2] [a, 1]
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

## <a name="size"></a>  unordered_multimap::size

Подсчитывает количество элементов.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }

```

```Output
 [c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="size_type"></a>  unordered_multimap::size_type

Тип беззнакового расстояния между двумя элементами.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Примечания

Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Он описан здесь как синоним для типа `T2`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_size_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::size_type sz = c1.size();

    std::cout << "size == " << sz << std::endl;

    return (0);
    }

```

```Output
size == 0
```

## <a name="swap"></a>  unordered_multimap::swap

Меняет местами содержимое двух контейнеров.

```cpp
void swap(unordered_multimap& right);
```

### <a name="parameters"></a>Параметры

`right` Контейнер для замены.

### <a name="remarks"></a>Примечания

Функция-член меняет местами управляемые последовательности между `*this` и `right`. Если используется функция [unordered_multimap::get_allocator](#get_allocator)`() == right.get_allocator()`, она делает это в постоянном времени, создает исключение только в результате копирования сохраненного объекта признаков типа `Tr` и не делает недействительными ссылки, указатели или итераторы, которые указывают на элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

// display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimap"></a>  unordered_multimap::unordered_multimap

Создает объект контейнера.

```cpp
unordered_multimap(
    const unordered_multimap& Right);

explicit unordered_multimap(
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Pred(),
    const Allocator& Al = Alloc());

unordered_multimap(
    unordered_multimap&& Right);

unordered_multimap(
    initializer_list<Type> IList);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key,
    const Allocator& Al);

template <class InputIterator>
unordered_multimap(
 InputIterator first, InputIterator last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Pred(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`InputIterator`|Тип итератора.|
|`Al`|Объект распределителя для сохранения.|
|`Comp`|Объект функции сравнения для сохранения.|
|`Hash`|Объект хэш-функции для сохранения.|
|`Bucket_count`|Минимальное количество блоков.|
|`Right`|Контейнер для копирования.|
|`IList`|Объект initializer_list, из которого копируются элементы.|

### <a name="remarks"></a>Примечания

Первый конструктор определяет копию последовательности, управляемой `Right`. Второй конструктор определяет управляемую пустую последовательность. Третий конструктор. задает копию последовательности путем перемещения `Right`. Четвертый, пятый, шестой, седьмой и восьмой конструкторы используют initializer_list для своих членов. Девятый конструктор добавляет последовательность значений элементов `[First, Last)`.

Все конструкторы также инициализируют ряд сохраненных значений. Для конструктора копии значения извлекаются из элемента `Right`. В противном случае:

Минимальное число блоков — это аргумент `Bucket_count`, если он существует; в противном случае это значение по умолчанию, представленное здесь как значение `N0`, определенное реализацией.

Объект хэш-функции — это аргумент `Hash`, если он существует; в противном случае это `Hash()`.

Объект функции сравнения — это аргумент `Comp`, если он существует; в противном случае это `Pred()`.

Объект функции распределителя — это аргумент `Al`, если он существует; в противном случае это `Alloc()`.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_construct.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

using namespace std;

using  Mymap = unordered_multimap<char, int> ;
int main()
{
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c2(8,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >());

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    // display contents " [f 6] [e 5] [d 4]"
    for (const auto& c : c2) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c3(c1.begin(),
        c1.end(),
        8,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >());

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c3) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c4(move(c3));

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c4) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Construct with an initializer_list
    unordered_multimap<int, char> c5({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } });
    for (const auto& c : c5) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size
    unordered_multimap<int, char> c6({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } }, 4);
    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size and hash
    unordered_multimap<int, char, hash<char>> c7(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size, hash, and key_equal
    unordered_multimap<int, char, hash<char>, equal_to<char>> c8(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>(),
        equal_to<char>()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size, hash, key_equal, and allocator
    unordered_multimap<int, char, hash<char>, equal_to<char>> c9(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;
}

```

```Output
[a, 1] [b, 2] [c, 3] [d, 4] [e, 5] [f, 6] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [5, g] [6, h] [7, i] [8, j] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [c, 3] [b, 2] [a, 1]
 [f, 6] [e, 5] [d, 4]
 [c, 3] [b, 2] [a, 1]
 [c, 3] [b, 2] [a, 1]
```

## <a name="value_type"></a>  unordered_multimap::value_type

Тип элемента.

```cpp
typedef std::pair<const Key, Ty> value_type;
```

### <a name="remarks"></a>Примечания

Тип описывает элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_map__unordered_multimap_value_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="see-also"></a>См. также

[<unordered_map>](../standard-library/unordered-map.md)<br/>
[Контейнеры](../cpp/containers-modern-cpp.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
