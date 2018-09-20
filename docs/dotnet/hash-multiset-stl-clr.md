---
title: hash_multiset (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset
- cliext::hash_multiset::begin
- cliext::hash_multiset::bucket_count
- cliext::hash_multiset::clear
- cliext::hash_multiset::const_iterator
- cliext::hash_multiset::const_reference
- cliext::hash_multiset::const_reverse_iterator
- cliext::hash_multiset::count
- cliext::hash_multiset::difference_type
- cliext::hash_multiset::empty
- cliext::hash_multiset::end
- cliext::hash_multiset::equal_range
- cliext::hash_multiset::erase
- cliext::hash_multiset::find
- cliext::hash_multiset::generic_container
- cliext::hash_multiset::generic_iterator
- cliext::hash_multiset::generic_reverse_iterator
- cliext::hash_multiset::generic_value
- cliext::hash_multiset::hash_delegate
- cliext::hash_multiset::hash_multiset
- cliext::hash_multiset::hasher
- cliext::hash_multiset::insert
- cliext::hash_multiset::iterator
- cliext::hash_multiset::key_comp
- cliext::hash_multiset::key_compare
- cliext::hash_multiset::key_type
- cliext::hash_multiset::load_factor
- cliext::hash_multiset::lower_bound
- cliext::hash_multiset::make_value
- cliext::hash_multiset::max_load_factor
- cliext::hash_multiset::operator=
- cliext::hash_multiset::rbegin
- cliext::hash_multiset::reference
- cliext::hash_multiset::rehash
- cliext::hash_multiset::rend
- cliext::hash_multiset::reverse_iterator
- cliext::hash_multiset::size
- cliext::hash_multiset::size_type
- cliext::hash_multiset::swap
- cliext::hash_multiset::to_array
- cliext::hash_multiset::upper_bound
- cliext::hash_multiset::value_comp
- cliext::hash_multiset::value_compare
- cliext::hash_multiset::value_type
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_multiset class [STL/CLR]
- <hash_set> header [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- hash_delegate member [STL/CLR]
- hash_multiset member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: caccf6c96f1bec5fa48eeda23a205c210dec076c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402828"
---
# <a name="hashmultiset-stlclr"></a>hash_multiset (STL/CLR)

Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины, имеющей двунаправленный доступ. Использовать контейнер `hash_multiset` для управления последовательностью элементов хэш-таблицы, каждая запись в таблице хранения двунаправленный связанный список узлов и каждый узел хранения одного элемента. Значение каждого элемента используется в качестве ключа, для упорядочения последовательности.

В следующем описании `GValue` совпадает со значением `GKey`, который в свою очередь является таким же, как *ключ* последний ссылочного типа, в противном случае он является `Key^`.

## <a name="syntax"></a>Синтаксис

```cpp
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

### <a name="parameters"></a>Параметры

*Key*<br/>
Тип ключевой компонент элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/hash_set >

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[hash_multiset::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[hash_multiset::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[hash_multiset::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[hash_multiset::difference_type (STL/CLR)](#difference_type)|Тип расстояния (возможно, со знаком) между двумя элементами.|
|[hash_multiset::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|
|[hash_multiset::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|
|[hash_multiset::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для универсального интерфейса для контейнера.|
|[hash_multiset::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для контейнера.|
|[hash_multiset::hasher (STL/CLR)](#hasher)|Делегат хэширования для ключа.|
|[hash_multiset::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[hash_multiset::key_compare (STL/CLR)](#key_compare)|Делегат упорядочения для двух ключей.|
|[hash_multiset::key_type (STL/CLR)](#key_type)|Тип ключа упорядочения.|
|[hash_multiset::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[hash_multiset::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[hash_multiset::size_type (STL/CLR)](#size_type)|Тип (неотрицательное) расстояние между двумя элементами.|
|[hash_multiset::value_compare (STL/CLR)](#value_compare)|Делегат упорядочения для значения двух элементов.|
|[hash_multiset::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[hash_multiset::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[hash_multiset::bucket_count (STL/CLR)](#bucket_count)|Подсчитывает количество сегментов.|
|[hash_multiset::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[hash_multiset::count (STL/CLR)](#count)|Подсчитывает элементы, соответствующие заданному ключу.|
|[hash_multiset::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[hash_multiset::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[hash_multiset::equal_range (STL/CLR)](#equal_range)|Находит диапазон, соответствующий указанному ключу.|
|[hash_multiset::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[hash_multiset::find (STL/CLR)](#find)|Определяет элемент, соответствующий указанному ключу.|
|[hash_multiset::hash_delegate (STL/CLR)](#hash_delegate)|Копирует делегат хэширования для ключа.|
|[hash_multiset::hash_multiset (STL/CLR)](#hash_multiset)|Создает объект контейнера.|
|[hash_multiset::insert (STL/CLR)](#insert)|Добавляет элементы.|
|[hash_multiset::key_comp (STL/CLR)](#key_comp)|Копирует делегат упорядочения для двух ключей.|
|[hash_multiset::load_factor (STL/CLR)](#load_factor)|Подсчитывает среднее число элементов в блоке.|
|[hash_multiset::lower_bound (STL/CLR)](#lower_bound)|Начало находит диапазон, соответствующий указанному ключу.|
|[hash_multiset::make_value (STL/CLR)](#make_value)|Создает объект значения.|
|[hash_multiset::max_load_factor (STL/CLR)](#max_load_factor)|Возвращает или задает максимальное количество элементов в блоке.|
|[hash_multiset::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[hash_multiset::rehash (STL/CLR)](#rehash)|Повторно создает хэш-таблицу.|
|[hash_multiset::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[hash_multiset::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[hash_multiset::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[hash_multiset::to_array (STL/CLR)](#to_array)|Копирует управляемой последовательности в новый массив.|
|[hash_multiset::upper_bound (STL/CLR)](#upper_bound)|Находит конец диапазон, соответствующий указанному ключу.|
|[hash_multiset::value_comp (STL/CLR)](#value_comp)|Копирует делегат упорядочения для значения двух элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[hash_multiset::operator= (STL/CLR)](#op)|Заменяет управляемую последовательность.|

## <a name="interfaces"></a>интерфейсов,

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Создание дубликата объекта.|
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|
|<xref:System.Collections.ICollection>|Сохранить группу элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность типизированных элементов.|
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|
|IHash\<ключ, значение >|Ведение универсального контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для последовательность, в которой он управляет, как отдельные узлы в двунаправленного связанного списка. Для ускорения доступа, объект также хранит переменной длины массива указателей в списке (хэш-таблица), эффективное управление весь список как последовательность подсписка, или контейнерах. Он добавляет элементы в контейнер, который хранит упорядоченную путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы остальных элементов.

Объект упорядочивает каждый контейнер путем вызова объекта делегата хранимых типа [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Объект хранимой делегата можно указать при создании объекта hash_set; Если указать объект делегата, значение по умолчанию является сравнение `operator<=(key_type, key_type)`.

Доступ к хранимой делегат, вызвав функцию-член [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Такой объект делегата необходимо определить соответствующий порядок между ключей типа [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:

`key_comp()(X, Y)` Возвращает результат же логическое значение при каждом вызове.

Если `key_comp()(X, Y) && key_comp()(Y, X)` имеет значение true, затем `X` и `Y` называются имеют эквивалентное упорядочение.

Любое правило упорядочения, который ведет себя как `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет порядок eqivalent.

Обратите внимание на то, что контейнер обеспечивает только элементы, ключи которых имеют эквивалентное упорядочение (и то же значение в целое число хэш-) рядом в сегменте. В отличие от шаблона класса [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md), объект класса шаблона `hash_multiset` не требует, что ключи для всех элементов являются уникальными. (Два или несколько ключей может иметь соответствующий порядок.)

Объект определяет каком сегменте должен содержать данным ключом сортировки, вызвав хранимую делегат типа [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Доступ к этот сохраненный объект, вызвав функцию-член [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` для получения целочисленное значение, которое зависит от значения ключа. Объект хранимой делегата можно указать при создании объекта hash_set; Если объект делегата не указан, по умолчанию используется функция `System::Object::hash_value(key_type)`. Это означает, что для любых ключей `X` и `Y`:

`hash_delegate()(X)` Возвращает один и тот же результат целое число при каждом вызове.

Если `X` и `Y` имеют эквивалентное упорядочение, затем `hash_delegate()(X)` должен возвращать целое число аналогично `hash_delegate()(Y)`.

Каждый элемент используется как ключ и значение. Последовательность представлена в виде, позволяющем выполнять уточняющий запрос, вставку и удаление произвольного элемента ряд операций, которая не зависит от числа элементов в последовательности (постоянное время) — по крайней мере в лучшие варианты. Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

Если хэшированные значения не распределяются равномерно, однако можно вырожденных хэш-таблицу. В крайнем случае--для хэш-функцией, всегда возвращает то же значение--поиска, вставки и удаления пропорционально количеству элементов в последовательности (линейное время). Контейнер пытается выбрать разумный хэш-функции, размер среднего сегмента, а размер хэш таблицы (общее количество сегментов), но можно переопределить любые или все из этих вариантов. Просмотреть, например, функции [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) и [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).

Hash_multiset поддерживает Двунаправленные итераторы, это означает, что при переходе на соседние элементы, задаваемые итератор, указывающий элемент в управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`. Итератор для достижения последнего элемента в управляемой последовательности, можно уменьшить, при его наличии. Можно увеличить это итератор hash_multiset, чтобы достичь головного узла и затем сравнивает равным `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.

Обратите внимание, что нельзя ссылаться на элемент объекта hash_multiset, непосредственно заданным его порядкового номера--, требующий итератор произвольного доступа.

Итератор hash_multiset сохраняет дескриптор его узел связанного объекта hash_multiset, который в свою очередь, сохраняет дескриптор для связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор hash_multiset остается допустимым до тех пор, пока его hash_multiset связанный узел связан с некоторых hash_multiset. Кроме того, это допустимый итератор является dereferencable — его можно использовать для доступа к или изменить значение элемента, указываемый ею--до тех пор, пока оно не равно `end()`.

Стирание или удалении элемента вызывает деструктор для сохраненному значению. Уничтожение контейнера стирает все элементы. Таким образом контейнер, тип элементов которого является ссылочным классом, гарантирует, что ни один элемент пережить контейнера. Обратите внимание, что контейнер дескрипторов не *не* уничтожить его элементов.

## <a name="members"></a>Участники

## <a name="begin"></a> hash_multiset::Begin (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, указывающий на первый элемент управляемой последовательности или непосредственно за окончание пустой последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_begin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multiset::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="bucket_count"></a> hash_multiset::bucket_count (STL/CLR)

Подсчитывает количество сегментов.

### <a name="syntax"></a>Синтаксис

```cpp
int bucket_count();
```

### <a name="remarks"></a>Примечания

Функции-члены возвращают текущее количество сегментов. Используется для определения размера хэш-таблицы.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="clear"></a> hash_multiset::Clear (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член эффективно вызывает [hash_multiset::erase (STL/CLR)](../dotnet/hash-multiset-erase-stl-clr.md) `(` [hash_multiset::begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md) `(),` [hash_multiset::end (STL/CLR) ](../dotnet/hash-multiset-end-stl-clr.md)`())`. Используется, чтобы убедиться, что управляемая последовательность пуста.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_clear.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="const_iterator"></a> hash_multiset::const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T2` , можно использовать в качестве константы двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_multiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reference"></a> hash_multiset::const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает постоянную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_const_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_multiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_multiset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reverse_iterator"></a> hash_multiset::const_reverse_iterator (STL/CLR)

Тип постоянного обратного итератора для управляемой последовательности...

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T4` , можно использовать в качестве постоянного обратного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_multiset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="count"></a> hash_multiset::Count (STL/CLR)

Определяет количество элементов, соответствующих заданному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член возвращает число элементов в управляемой последовательности, которые имеют эквивалентное упорядочение с *ключ*. Используется для определения количества элементов в данный момент в управляемой последовательности, соответствующие заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="difference_type"></a> hash_multiset::difference_type (STL/CLR)

Типы со знаком расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает число возможно отрицательное элемент.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_difference_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multiset::difference_type diff = 0;
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_multiset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="empty"></a> hash_multiset::Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)`() == 0`. Оно позволяет проверить, является ли объект hash_multiset пустой.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_empty.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="end"></a> hash_multiset::End (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, указывающий на место сразу за концом управляемой последовательности. Используется для получения итератора, который задает конец управляемой последовательности; его состояние не изменяется при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_end.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_multiset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="equal_range"></a> hash_multiset::equal_range (STL/CLR)

Находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член возвращает пару итераторов `cliext::pair<iterator, iterator>(` [hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md) `(key),` [hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)`(key))`. Используется для определения диапазона элементов в данный момент в управляемой последовательности, соответствующие заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_equal_range.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
typedef Myhash_multiset::pair_iter_iter Pairii;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="erase"></a> hash_multiset::Erase (STL/CLR)

Удаляет элементы в указанных позициях.

### <a name="syntax"></a>Синтаксис

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для удаления.

*key*<br/>
Значение ключа для удаления.

*последний*<br/>
Конец диапазона для удаления.

*where*<br/>
Подлежащий удалению элемент.

### <a name="remarks"></a>Примечания

Первая функция-член удаляет элемент управляемой последовательности, на которые указывают *где*и возвращает итератор, указывающий на первый элемент, оставшийся после удаления элемента или [hash_multiset::end () STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md) `()` Если такого элемента не существует. Используется для удаления одного элемента.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`) и возвращает итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или `end()` Если такой элемент отсутствует существует... Используется для удаления ноль или более идущих подряд элементов.

Третья функция-член удаляет любой элемент управляемой последовательности, ключ которого имеет соответствующий порядок для *ключ*и возвращает количество удаленных элементов. Используется для удаления, а также подсчитать все элементы, соответствующие заданному ключу.

Каждый элемент стирания требуется время, пропорционально логарифму числа элементов в управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_erase.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    Myhash_multiset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="find"></a> hash_multiset::Find (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Если хотя бы один элемент управляемой последовательности, эквивалентное упорядочение с *ключ*, функция-член возвращает итератор, обозначающий один из этих элементов; в противном случае возвращается [hash_multiset::end (STL/CLR) ](../dotnet/hash-multiset-end-stl-clr.md)`()`. Используется для поиска элемента в данный момент в управляемой последовательности, соответствующий указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_find.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="generic_container"></a> hash_multiset::generic_container (STL/CLR)

Тип универсального интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Примечания

Этот тип описывает универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_generic_container.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="generic_iterator"></a> hash_multiset::generic_iterator (STL/CLR)

Тип итератора для использования с универсальный интерфейс для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип Описывает универсальные итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_iterator gcit = gc1->begin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="generic_reverse_iterator"></a> hash_multiset::generic_reverse_iterator (STL/CLR)

Тип обратного итератора для использования с универсальный интерфейс для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип Описывает универсальные Обратный итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="generic_value"></a> hash_multiset::generic_value (STL/CLR)

Тип элемента для использования с универсальный интерфейс для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_generic_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_iterator gcit = gc1->begin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_delegate"></a> hash_multiset::hash_delegate (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегат, используемый для преобразования значения ключа в целое число. Используется для хэширования ключа.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multiset"></a> hash_multiset::hash_multiset (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
hash_multiset();
explicit hash_multiset(key_compare^ pred);
hash_multiset(key_compare^ pred, hasher^ hashfn);
hash_multiset(hash_multiset<Key>% right);
hash_multiset(hash_multiset<Key>^ right);
template<typename InIter>
    hash_multiset(InIter first, InIter last);
template<typename InIter>
    hash_multiset(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_multiset(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для вставки.

*hashfn*<br/>
Хэш-функции для сопоставления ключей к количеству сегментов.

*последний*<br/>
Конец диапазона для вставки.

*Пред*<br/>
Упорядочение предикат для управляемой последовательности.

*right*<br/>
Объект или диапазон для вставки.

### <a name="remarks"></a>Примечания

Конструктор:

`hash_multiset();`

Инициализирует управляемую последовательность не содержит элементов, со значением по умолчанию, упорядочение предикат `key_compare()`и значение по умолчанию хэш-функции. Используется для указания пустой начальной управляемой последовательности, со значением по умолчанию, упорядочение предиката и хэш-функции.

Конструктор:

`explicit hash_multiset(key_compare^ pred);`

Инициализирует управляемую последовательность не содержит элементов, с помощью предикат упорядочения *pred*и значение по умолчанию хэш-функции. Используется для указания пустой начальной управляемой последовательности, указанный предикат упорядочения и хэш-функцию по умолчанию.

Конструктор:

`hash_multiset(key_compare^ pred, hasher^ hashfn);`

Инициализирует управляемую последовательность не содержит элементов, с помощью предикат упорядочения *pred*и хэш-функции *hashfn*. Используется для указания пустой начальной управляемой последовательности, с указанным предикатом и хэш-функции упорядочивания.

Конструктор:

`hash_multiset(hash_multiset<Key>% right);`

Инициализирует управляемую последовательность последовательностью [`right.begin()`, `right.end()`) со значением по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объект hash_multiset *правой*с предикат упорядочения по умолчанию и хэш-функции.

Конструктор:

`hash_multiset(hash_multiset<Key>^ right);`

Инициализирует управляемую последовательность последовательностью [`right->begin()`, `right->end()`) со значением по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объект hash_multiset *правой*с предикат упорядочения по умолчанию и хэш-функции.

Конструктор:

`template<typename InIter> hash_multiset(InIter first, InIter last);`

Инициализирует управляемую последовательность последовательностью [`first`, `last`) со значением по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для создания копии другой последовательности, управляемой последовательности с заданным по умолчанию, упорядочение предиката и хэш-функции.

Конструктор:

`template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred);`

Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью предикат упорядочения *pred*и значение по умолчанию хэш-функции. Используется для создания копии другой последовательности, указанный предикат упорядочения и хэш-функцию по умолчанию для управляемой последовательности.

Конструктор:

`template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью предикат упорядочения *pred*и хэш-функции *hashfn*. Используется, чтобы сделать управляемую последовательность копией другую последовательность с указанным предикатом и хэш-функции упорядочивания.

Конструктор:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`

Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*со значением по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для создания копии другой последовательности, описываемого перечислитель, с помощью упорядочения предиката и хэш-функция по умолчанию для управляемой последовательности.

Конструктор:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, с помощью предикат упорядочения *pred*и значение по умолчанию хэш-функции. Используется, чтобы сделать управляемую последовательность копией другую последовательность, описываемого перечислителя, указанный упорядочивания предиката и по умолчанию хэш-функции.

Конструктор:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, с помощью предикат упорядочения *pred*и хэш-функции *hashfn*. Используется, чтобы сделать управляемую последовательность копией другую последовательность, описываемого перечислитель, с указанным предикатом и хэш-функции упорядочивания.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_construct.cpp
// compile with: /clr
#include <cliext/hash_set>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
// construct an empty container
    Myhash_multiset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multiset::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_multiset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_multiset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_multiset c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multiset::hasher(&myfun));
    for each (wchar_t elem in c4h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_multiset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_multiset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_multiset c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>(),
                gcnew Myhash_multiset::hasher(&myfun));
    for each (wchar_t elem in c6h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct from a generic container
    Myhash_multiset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_multiset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
a b c
size() = 0
c b a

a b c
a b c
c b a

a b c
a b c
c b a

a b c
a b c
```

## <a name="hasher"></a> hash_multiset::hasher (STL/CLR)

Делегат хэширования для ключа.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>Примечания

Этот тип описывает делегат, преобразующий значение ключа в целое число.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_hasher.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="insert"></a> hash_multiset::Insert (STL/CLR)

Добавляет элементы.

### <a name="syntax"></a>Синтаксис

```cpp
iterator insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для вставки.

*последний*<br/>
Конец диапазона для вставки.

*right*<br/>
Перечисление для вставки.

*Val*<br/>
Значение ключа для вставки.

*where*<br/>
Место в контейнере для вставки (подсказка).

### <a name="remarks"></a>Примечания

Каждая из функций-членов вставляет последовательности, указываемой аргументом оставшимися операндами.

Первая функция-член вставляет элемент со значением *val*и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки одного элемента.

Вторая функция-член вставляет элемент со значением *val*, с использованием *где* как подсказку (для повышения производительности) и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки один элемент, который может быть смежными на элемент, который вы знаете.

Третья функция-член вставляет последовательность [`first`, `last`). Используется для вставки ноль или более элементов, копируемых из другой последовательности.

Четвертая функция-член вставляет последовательность, назначенному с помощью *правой*. Используется для вставки описываемого перечислитель последовательности.

Вставка каждого элемента занимает время, пропорционально логарифму числа элементов в управляемой последовательности. Вставка может происходить в амортизированном константном времени, тем не менее, учитывая подсказку, которая выделяет элемент рядом курсор.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_insert.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    System::Console::WriteLine("insert(L'x') = {0}",
        *c1.insert(L'x'));

    System::Console::WriteLine("insert(L'b') = {0}",
        *c1.insert(L'b'));

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_multiset c2;
    Myhash_multiset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_multiset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = x
insert(L'b') = b
a b b c x
insert(begin(), L'y') = y
a b b c x y
a b b c x
a b b c x y
```

## <a name="iterator"></a> hash_multiset::iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T1` , можно использовать в качестве двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_multiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="key_comp"></a> hash_multiset::key_comp (STL/CLR)

Копирует делегат упорядочения для двух ключей.

### <a name="syntax"></a>Синтаксис

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Используется для сравнения двух ключей.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_key_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_compare"></a> hash_multiset::key_compare (STL/CLR)

Делегат упорядочения для двух ключей.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для делегата, который определяет порядок его аргументы ключа.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_key_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_type"></a> hash_multiset::key_type (STL/CLR)

Тип ключа упорядочения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона *ключ*.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_key_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_multiset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="load_factor"></a> hash_multiset::load_factor (STL/CLR)

Подсчитывает среднее число элементов в блоке.

### <a name="syntax"></a>Синтаксис

```cpp
float load_factor();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает `(float)` [hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md) `() /` [hash_multiset::bucket_count (STL/CLR)](../dotnet/hash-multiset-bucket-count-stl-clr.md)`()`. Оно позволяет определить размер среднего сегмента.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="lower_bound"></a> hash_multiset::lower_bound (STL/CLR)

Начало находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет первый элемент `X` в управляемой последовательности, хэширует на один и тот же контейнер как *ключ* и порядок, эквивалентный порядку *ключ*. Если такого элемента не существует, она возвращает [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий `X`. Используется для поиска в начало последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="make_value"></a> hash_multiset::make_value (STL/CLR)

Создает объект значения.

### <a name="syntax"></a>Синтаксис

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа для использования.

### <a name="remarks"></a>Примечания

Функция-член возвращает `value_type` ключ которого *ключ*. Используется для создания объекта, подходящий для использования с несколько других функций-членов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_make_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(Myhash_multiset::make_value(L'a'));
    c1.insert(Myhash_multiset::make_value(L'b'));
    c1.insert(Myhash_multiset::make_value(L'c'));

    // display contents " a b c"
    for each (Myhash_multiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="max_load_factor"></a> hash_multiset::max_load_factor (STL/CLR)

Возвращает или задает максимальное количество элементов в блоке.

### <a name="syntax"></a>Синтаксис

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>Параметры

*new_factor*<br/>
Новое значение максимального загрузить коэффициент для хранения.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает текущий сохраненный коэффициент максимальной нагрузки. Используется для определения максимального сегмента среднего размера.

Вторая функция-член заменяет коэффициент максимальной нагрузки хранилище *new_factor*. Нет автоматического проведя пересчет контрольной суммы выполняется до последующие операции вставки.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="op"></a> hash_multiset::operator = (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
hash_multiset<Key>% operator=(hash_multiset<Key>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Примечания

Копирует оператор член *правой* объекту, затем возвращает `*this`. Оно позволяет заменить управляемую последовательность копией управляемой последовательности в *правой*.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_operator_as.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Myhash_multiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_multiset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myhash_multiset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="rbegin"></a> hash_multiset::rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или непосредственно перед началом пустой последовательности. Таким образом, он задает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало отображаемой в обратном порядке управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_rbegin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multiset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="reference"></a> hash_multiset::Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_multiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_multiset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="rehash"></a> hash_multiset::rehash (STL/CLR)

Повторно создает хэш-таблицу.

### <a name="syntax"></a>Синтаксис

```cpp
void rehash();
```

### <a name="remarks"></a>Примечания

Функция-член перестраивает хэш-таблицы, что [hash_multiset::load_factor (STL/CLR)](../dotnet/hash-multiset-load-factor-stl-clr.md) `() <=` [hash_multiset::max_load_factor (STL/CLR)](../dotnet/hash-multiset-max-load-factor-stl-clr.md). В противном случае хэш-таблице увеличивается в размере, только при необходимости после вставки. (Он никогда не автоматически уменьшится размер.) Он понадобится для настройки размера хэш-таблицы.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_rehash.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="rend"></a> hash_multiset::rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает Обратный итератор, указывающий непосредственно перед началом управляемой последовательности. Таким образом, он задает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец отображаемой в обратном порядке управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_rend.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multiset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="reverse_iterator"></a> hash_multiset::reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T3` , можно использовать в качестве обратного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_multiset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="size"></a> hash_multiset::size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Используется для определения числа элементов в данный момент в управляемой последовательности. Если вас интересуют ли последовательность имеет ненулевой размер, см. в разделе [hash_multiset::empty (STL/CLR)](../dotnet/hash-multiset-empty-stl-clr.md)`()`.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_size.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> hash_multiset::size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает элемент неотрицательное число.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_size_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multiset::size_type diff = 0;
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="swap"></a> hash_multiset::Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(hash_multiset<Key>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Примечания

Функция-член меняет местами управляемые последовательности между `this` и *правой*. Она делает это в константном времени и не создает исключения. Можно использовать как быстрый способ местами содержимое двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_swap.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_multiset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
d e f
d e f
a b c
```

## <a name="to_array"></a> hash_multiset::to_array (STL/CLR)

Копирует управляемой последовательности в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает массив, содержащий управляемой последовательности. Вы можете использовать его для получения копии управляемой последовательности в форме массива.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_to_array.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="upper_bound"></a> hash_multiset::upper_bound (STL/CLR)

Находит конец диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет последний элемент `X` в управляемой последовательности, хэширует на один и тот же контейнер как *ключ* и порядок, эквивалентный порядку *ключ*. Если такого элемента не существует или если `X` является последним элементом в управляемой последовательности, он возвращает [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий первый элемент после `X`. Оно позволяет найти конец последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="value_comp"></a> hash_multiset::value_comp (STL/CLR)

Копирует делегат упорядочения для значения двух элементов.

### <a name="syntax"></a>Синтаксис

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Оно позволяет сравнить значения двух элементов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_value_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_compare"></a> hash_multiset::value_compare (STL/CLR)

Делегат упорядочения для значения двух элементов.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для делегата, который определяет порядок аргументов значение.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_value_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_type"></a> hash_multiset::value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `generic_value`.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multiset_value_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_multiset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```