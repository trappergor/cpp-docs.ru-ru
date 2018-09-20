---
title: карты (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map
- cliext::map::begin
- cliext::map::clear
- cliext::map::const_iterator
- cliext::map::const_reference
- cliext::map::const_reverse_iterator
- cliext::map::count
- cliext::map::difference_type
- cliext::map::empty
- cliext::map::end
- cliext::map::equal_range
- cliext::map::erase
- cliext::map::find
- cliext::map::generic_container
- cliext::map::generic_iterator
- cliext::map::generic_reverse_iterator
- cliext::map::generic_value
- cliext::map::insert
- cliext::map::iterator
- cliext::map::key_comp
- cliext::map::key_compare
- cliext::map::key_type
- cliext::map::lower_bound
- cliext::map::make_value
- cliext::map::map
- cliext::map::mapped_type
- cliext::map::operator=
- cliext::map::operator
- cliext::map::rbegin
- cliext::map::reference
- cliext::map::rend
- cliext::map::reverse_iterator
- cliext::map::size
- cliext::map::size_type
- cliext::map::swap
- cliext::map::to_array
- cliext::map::upper_bound
- cliext::map::value_comp
- cliext::map::value_compare
- cliext::map::value_type
- cliext::operator!= (map)
- cliext::operator< (map)
- cliext::operator<= (map)
- cliext::operator== (map)
- cliext::operator> (map)
- cliext::operator>= (map)
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
- begin member [STL/CLR]
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
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
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
- operator!= (map) member [STL/CLR]
- operator< (map) member [STL/CLR]
- operator<= (map) member [STL/CLR]
- operator== (map) member [STL/CLR]
- operator> (map) member [STL/CLR]
- operator>= (map) member [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d1a47c8fe8d1fc00b78a67d3b2f5fdf111fd458
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422978"
---
# <a name="map-stlclr"></a>map (STL/CLR)

Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины, имеющей двунаправленный доступ. Использовать контейнер `map` для управления последовательностью элементов как упорядоченный (почти) сбалансированного дерева узлов, каждый хранения одного элемента. Элемент состоит из ключа, для упорядочения последовательности и сопоставленного значения, который проходит выполнил.

В следующем описании `GValue` совпадает со значением:

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

Здесь:

`GKey` совпадает со значением *ключ* последний ссылочного типа, в противном случае он является `Key^`

`GMapped` совпадает со значением *сопоставлен* последний ссылочного типа, в противном случае он является `Mapped^`

## <a name="syntax"></a>Синтаксис

```cpp
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

### <a name="parameters"></a>Параметры

*Key*<br/>
Тип ключевой компонент элемента в управляемой последовательности.

*сопоставить*<br/>
Тип компонента, дополнительных элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/map >

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[map::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[map::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[map::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[map::difference_type (STL/CLR)](#difference_type)|Тип расстояния (возможно, со знаком) между двумя элементами.|
|[map::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|
|[map::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|
|[map::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для универсального интерфейса для контейнера.|
|[map::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для контейнера.|
|[map::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[map::key_compare (STL/CLR)](#key_compare)|Делегат упорядочения для двух ключей.|
|[map::key_type (STL/CLR)](#key_type)|Тип ключа упорядочения.|
|[map::mapped_type (STL/CLR)](#mapped_type)|Тип сопоставленного значения, связанного с каждым ключом.|
|[map::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[map::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[map::size_type (STL/CLR)](#size_type)|Тип (неотрицательное) расстояние между двумя элементами.|
|[map::value_compare (STL/CLR)](#value_compare)|Делегат упорядочения для значения двух элементов.|
|[map::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[map::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[map::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[map::count (STL/CLR)](#count)|Подсчитывает элементы, соответствующие заданному ключу.|
|[map::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[map::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[map::equal_range (STL/CLR)](#equal_range)|Находит диапазон, соответствующий указанному ключу.|
|[map::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[map::find (STL/CLR)](#find)|Определяет элемент, соответствующий указанному ключу.|
|[map::insert (STL/CLR)](#insert)|Добавляет элементы.|
|[map::key_comp (STL/CLR)](#key_comp)|Копирует делегат упорядочения для двух ключей.|
|[map::lower_bound (STL/CLR)](#lower_bound)|Начало находит диапазон, соответствующий указанному ключу.|
|[map::make_value (STL/CLR)](#make_value)|Создает объект значения.|
|[map::map (STL/CLR)](#map)|Создает объект контейнера.|
|[map::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[map::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[map::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[map::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[map::to_array (STL/CLR)](#to_array)|Копирует управляемой последовательности в новый массив.|
|[map::upper_bound (STL/CLR)](#upper_bound)|Находит конец диапазон, соответствующий указанному ключу.|
|[map::value_comp (STL/CLR)](#value_comp)|Копирует делегат упорядочения для значения двух элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[map::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|
|[map::operator (STL/CLR)](#op)|Сопоставляет ключ сопоставленный ему значение.|
|[operator!= (map) (STL/CLR)](#op_neq)|Определяет, если `map` объект не равным значению другого `map` объекта.|
|[operator< (map) (STL/CLR)](#op_lt)|Определяет, если `map` объект меньше другого `map` объекта.|
|[operator<= (map) (STL/CLR)](#op_lteq)|Определяет, если `map` объекта меньше или равно другому `map` объекта.|
|[operator== (map) (STL/CLR)](#op_eq)|Определяет, если `map` объект равен другому `map` объекта.|
|[operator> (map) (STL/CLR)](#op_gt)|Определяет, если `map` объект больше, чем другой `map` объекта.|
|[operator>= (map) (STL/CLR)](#op_gteq)|Определяет, если `map` объекта больше или равно другому `map` объекта.|

## <a name="interfaces"></a>интерфейсов,

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Создание дубликата объекта.|
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|
|<xref:System.Collections.ICollection>|Сохранить группу элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность типизированных элементов.|
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|
|<xref:System.Collections.Generic.IDictionary%602>|Сохранить группу {ключ-значение пары.|
|ITree < ключ, значение >|Ведение универсального контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для последовательность, в которой он управляет в виде отдельных узлов. Он добавляет элементы в (почти) дерева, которое отслеживает упорядоченный путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы остальных элементов.

Объект Упорядочивает управляемую им последовательность путем вызова объекта хранимых делегат типа [map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md). Объект хранимой делегата можно указать при создании карты; Если указать объект делегата, значение по умолчанию является сравнение `operator<(key_type, key_type)`. Доступ к этот сохраненный объект, вызвав функцию-член [map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`.

Такой объект делегата должна налагать строгое слабое упорядочение на ключах типа [map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:

`key_comp()(X, Y)` Возвращает результат же логическое значение при каждом вызове.

Если `key_comp()(X, Y)` имеет значение true, затем `key_comp()(Y, X)` должно иметь значение false.

Если `key_comp()(X, Y)` имеет значение true, затем `X` говорят, что допускается упорядочение перед `Y`.

Если `!key_comp()(X, Y) && !key_comp()(Y, X)` имеет значение true, затем `X` и `Y` называются имеют эквивалентное упорядочение.

Для любого элемента `X` , предшествующий `Y` в управляемой последовательности, `key_comp()(Y, X)` имеет значение false. (Для объекта делегата по умолчанию, ключи никогда не уменьшаются.) В отличие от шаблона класса [карты](../dotnet/map-stl-clr.md), объект класса шаблона `map` не требует, что ключи для всех элементов являются уникальными. (Два или несколько ключей может иметь соответствующий порядок.)

Каждый элемент содержит отдельный ключ и сопоставленного значения. Последовательность представлена в виде, позволяющем выполнять поиска, вставки и удаления произвольного элемента с количеством операций, пропорционально логарифму числа элементов в последовательности (логарифмическом времени). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

Карты поддерживает Двунаправленные итераторы, это означает, что при переходе на соседние элементы, задаваемые итератор, указывающий элемент в управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Итератор для достижения последнего элемента в управляемой последовательности, можно уменьшить, при его наличии. Можно увеличить итератор с карты, чтобы достичь головного узла, а затем будет считаются равными `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.

Обратите внимание, что нельзя ссылаться на элемент сопоставления, непосредственно заданным его порядкового номера--, требующий итератор произвольного доступа.

Итератор с карты сохраняет дескриптор его связанные карты узла, который в свою очередь, сохраняет дескриптор для связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Итератор с карты остается допустимым до тех пор, пока его связанные карты узла связан с некоторые карты. Кроме того, это допустимый итератор является dereferencable — его можно использовать для доступа к или изменить значение элемента, указываемый ею--до тех пор, пока оно не равно `end()`.

Стирание или удалении элемента вызывает деструктор для сохраненному значению. Уничтожение контейнера стирает все элементы. Таким образом контейнер, тип элементов которого является ссылочным классом, гарантирует, что ни один элемент пережить контейнера. Обратите внимание, что контейнер дескрипторов не *не* уничтожить его элементов.

## <a name="members"></a>Участники

## <a name="begin"></a> MAP::Begin (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, указывающий на первый элемент управляемой последовательности или непосредственно за окончание пустой последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_begin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Mymap::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*++begin() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*begin() = [a 1]
*++begin() = [b 2]
```

## <a name="clear"></a> MAP::Clear (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член эффективно вызывает [map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md) `(` [map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md) `(),` [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md) `())`. Используется, чтобы убедиться, что управляемая последовательность пуста.

### <a name="example"></a>Пример

```cpp
// cliext_map_clear.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2]
size() = 0
```

## <a name="const_iterator"></a> MAP::const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T2` , можно использовать в качестве константы двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_const_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reference"></a> MAP::const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает постоянную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_map_const_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reverse_iterator"></a> MAP::const_reverse_iterator (STL/CLR)

Тип постоянного обратного итератора для управляемой последовательности...

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T4` , можно использовать в качестве постоянного обратного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="count"></a> MAP::Count (STL/CLR)

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
// cliext_map_count.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="difference_type"></a> MAP::difference_type (STL/CLR)

Типы со знаком расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает число возможно отрицательное элемент.

### <a name="example"></a>Пример

```cpp
// cliext_map_difference_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::difference_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymap::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
begin()-end() = -3
```

## <a name="empty"></a> MAP::Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)`() == 0`. Можно использовать для тестирования ли сопоставление является пустым.

### <a name="example"></a>Пример

```cpp
// cliext_map_empty.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="end"></a> MAP::End (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, указывающий на место сразу за концом управляемой последовательности. Используется для получения итератора, который задает конец управляемой последовательности; его состояние не изменяется при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_end.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Mymap::iterator it = c1.end();
    --it;
    --it;
    System::Console::WriteLine("*-- --end() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*--end() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

## <a name="equal_range"></a> MAP::equal_range (STL/CLR)

Находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член возвращает пару итераторов `cliext::pair<iterator, iterator>(` [map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md) `(key),` [map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)`(key))`. Используется для определения диапазона элементов в данный момент в управляемой последовательности, соответствующие заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_map_equal_range.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_iter Pairii;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("[{0} {1}] ",
            pair1.first->first, pair1.first->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
equal_range(L'x') empty = True
[b 2]
```

## <a name="erase"></a> MAP::Erase (STL/CLR)

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

Первая функция-член удаляет элемент управляемой последовательности, на которые указывают *где*и возвращает итератор, указывающий на первый элемент, оставшийся после удаления элемента или [map::end (STL/CLR) ](../dotnet/map-end-stl-clr.md) `()` Если такого элемента не существует. Используется для удаления одного элемента.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`) и возвращает итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или `end()` Если такой элемент отсутствует существует... Используется для удаления ноль или более идущих подряд элементов.

Третья функция-член удаляет любой элемент управляемой последовательности, ключ которого имеет соответствующий порядок для *ключ*и возвращает количество удаленных элементов. Используется для удаления, а также подсчитать все элементы, соответствующие заданному ключу.

Каждый элемент стирания требуется время, пропорционально логарифму числа элементов в управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_erase.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    cliext::map<wchar_t, int> c1;
    c1.insert(cliext::map<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::map<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::map<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase all but end
    it = c1.end();
    it = c1.erase(c1.begin(), --it);
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",
        it->first, it->second);
    System::Console::WriteLine("size() = {0}", c1.size());

    // erase end
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
erase(begin()) = [b 2]
[b 2] [c 3] [d 4] [e 5]
erase(begin(), end()-1) = [e 5]
size() = 1
erase(L'x') = 0
erase(L'e') = 1
```

## <a name="find"></a> MAP::Find (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Если хотя бы один элемент управляемой последовательности, эквивалентное упорядочение с *ключ*, функция-член возвращает итератор, обозначающий один из этих элементов; в противном случае возвращается [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Используется для поиска элемента в данный момент в управляемой последовательности, соответствующий указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_map_find.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Mymap::iterator it = c1.find(L'b');
    System::Console::WriteLine("find {0} = [{1} {2}]",
        L'b', it->first, it->second);

    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
find A = False
find b = [b 2]
find C = False
```

## <a name="generic_container"></a> MAP::generic_container (STL/CLR)

Тип универсального интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Примечания

Этот тип описывает универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_map_generic_container.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Mymap::make_value(L'e', 5));
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3] [d 4] [e 5]
```

## <a name="generic_iterator"></a> MAP::generic_iterator (STL/CLR)

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
// cliext_map_generic_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::Write("[{0} {1}] ", gcval->first, gcval->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="generic_reverse_iterator"></a> MAP::generic_reverse_iterator (STL/CLR)

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
// cliext_map_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_reverse_iterator gcit = gc1->rbegin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="generic_value"></a> MAP::generic_value (STL/CLR)

Тип элемента для использования с универсальный интерфейс для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_map_generic_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="insert"></a> MAP::Insert (STL/CLR)

Добавляет элементы.

### <a name="syntax"></a>Синтаксис

```cpp
cliext::pair<iterator, bool> insert(value_type val);
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

Первая функция-член пытается вставить элемент со значением *val*и возвращает пару значений `X`. Если `X.second` имеет значение true, `X.first` назначает новому вставленному элементу; в противном случае `X.first` обозначает существующему элементу с эквивалентным, уже упорядочением и новый элемент не добавляется. Используется для вставки одного элемента.

Вторая функция-член вставляет элемент со значением *val*, с использованием *где* как подсказку (для повышения производительности) и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки один элемент, который может быть смежными на элемент, который вы знаете.

Третья функция-член вставляет последовательность [`first`, `last`). Используется для вставки ноль или более элементов, копируемых из другой последовательности.

Четвертая функция-член вставляет последовательность, назначенному с помощью *правой*. Используется для вставки описываемого перечислитель последовательности.

Вставка каждого элемента занимает время, пропорционально логарифму числа элементов в управляемой последовательности. Вставка может происходить в амортизированном константном времени, тем не менее, учитывая подсказку, которая выделяет элемент рядом курсор.

### <a name="example"></a>Пример

```cpp
// cliext_map_insert.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_bool Pairib;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
// insert a single value, success and failure
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    pair1 = c1.insert(Mymap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    Mymap::iterator it =
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Mymap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Mymap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Mymap::value_type>^)%c1);
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [[x 24] True]
insert([L'b' 2]) = [[b 2] False]
[a 1] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [c 3] [x 24]
[a 1] [b 2] [c 3] [x 24] [y 25]
```

## <a name="iterator"></a> MAP::iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T1` , можно использовать в качестве двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="key_comp"></a> MAP::key_comp (STL/CLR)

Копирует делегат упорядочения для двух ключей.

### <a name="syntax"></a>Синтаксис

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Используется для сравнения двух ключей.

### <a name="example"></a>Пример

```cpp
// cliext_map_key_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_compare"></a> MAP::key_compare (STL/CLR)

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
// cliext_map_key_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_type"></a> MAP::key_type (STL/CLR)

Тип ключа упорядочения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона *ключ*.

### <a name="example"></a>Пример

```cpp
// cliext_map_key_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="lower_bound"></a> MAP::lower_bound (STL/CLR)

Начало находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет первый элемент `X` в управляемой последовательности с эквивалентным упорядочением для *ключ*. Если такого элемента не существует, она возвращает [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий `X`. Используется для поиска в начало последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_map_lower_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Mymap::iterator it = c1.lower_bound(L'a');
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.lower_bound(L'b');
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
lower_bound(L'x')==end() = True
*lower_bound(L'a') = [a 1]
*lower_bound(L'b') = [b 2]
```

## <a name="make_value"></a> MAP::make_value (STL/CLR)

Создает объект значения.

### <a name="syntax"></a>Синтаксис

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа для использования.

*сопоставить*<br/>
Сопоставленное значение для поиска.

### <a name="remarks"></a>Примечания

Функция-член возвращает `value_type` ключ которого *ключ* и сопоставленные значение *сопоставлены*. Используется для создания объекта, подходящий для использования с несколько других функций-членов.

### <a name="example"></a>Пример

```cpp
// cliext_map_make_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="map"></a> MAP::Map (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
map();
explicit map(key_compare^ pred);
map(map<Key, Mapped>% right);
map(map<Key, Mapped>^ right);
template<typename InIter>
    mapmap(InIter first, InIter last);
template<typename InIter>
    map(InIter first, InIter last,
        key_compare^ pred);
map(System::Collections::Generic::IEnumerable<GValue>^ right);
map(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для вставки.

*последний*<br/>
Конец диапазона для вставки.

*Пред*<br/>
Упорядочение предикат для управляемой последовательности.

*right*<br/>
Объект или диапазон для вставки.

### <a name="remarks"></a>Примечания

Конструктор:

`map();`

Инициализирует управляемую последовательность не содержит элементов, со значением по умолчанию, упорядочение предикат `key_compare()`. Используется для указания пустой начальной управляемой последовательности, со значением по умолчанию, упорядочение предикат.

Конструктор:

`explicit map(key_compare^ pred);`

Инициализирует управляемую последовательность не содержит элементов, с помощью предикат упорядочения *pred*. Используется для указания пустой начальной управляемой последовательности, указанный предикат упорядочения.

Конструктор:

`map(map<Key, Mapped>% right);`

Инициализирует управляемую последовательность последовательностью [`right.begin()`, `right.end()`), с помощью упорядочения предикат по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта map *правой*, со значением по умолчанию, упорядочение предикат.

Конструктор:

`map(map<Key, Mapped>^ right);`

Инициализирует управляемую последовательность последовательностью [`right->begin()`, `right->end()`), с помощью упорядочения предикат по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта map *правой*, со значением по умолчанию, упорядочение предикат.

Конструктор:

`template<typename InIter> map(InIter first, InIter last);`

Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью упорядочения предикат по умолчанию. Используется для создания копии другой последовательности, управляемой последовательности с помощью упорядочения предикат по умолчанию.

Конструктор:

`template<typename InIter> map(InIter first, InIter last, key_compare^ pred);`

Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью предикат упорядочения *pred*. Используется для создания копии другой последовательности, с указанным предикатом упорядочения управляемой последовательности.

Конструктор:

`map(System::Collections::Generic::IEnumerable<Key>^ right);`

Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, со значением по умолчанию, упорядочение предикат. Используется, чтобы сделать управляемую последовательность копией другую последовательность, описываемого перечислитель, с помощью упорядочения предикат по умолчанию.

Конструктор:

`map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, с помощью предикат упорядочения *pred*. Используется для создания копии другой последовательности, описываемого перечислитель, с указанным предикатом упорядочения управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_construct.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
// construct an empty container
    Mymap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymap c3(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3);
    for each (Mymap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying another container
    Mymap c7(c4);
    for each (Mymap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mymap c8(%c3);
    for each (Mymap::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
```

## <a name="mapped_type"></a> MAP::mapped_type (STL/CLR)

Тип сопоставленного значения, связанного с каждым ключом.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона *сопоставлен*.

### <a name="example"></a>Пример

```cpp
// cliext_map_mapped_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Mymap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="op_as"></a> MAP::operator = (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
map<Key, Mapped>% operator=(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Примечания

Копирует оператор член *правой* объекту, затем возвращает `*this`. Оно позволяет заменить управляемую последовательность копией управляемой последовательности в *правой*.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_as.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2 = c1;
    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="op"></a> MAP::operator(STL/CLR)

Сопоставляет ключ сопоставленный ему значение.

### <a name="syntax"></a>Синтаксис

```cpp
mapped_type operator[](key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Проекты, чтобы найти элемент с эквивалентным упорядочением для функции-члены *ключ*. Если таковой найден, он возвращает связанные сопоставленное значение; в противном случае он вставляет `value_type(key, mapped_type())` и возвращает связанный (по умолчанию) сопоставить значение. Используется для поиска сопоставленные значения, заданным связанный с ним ключ или чтобы убедиться, что запись существует для ключа, если он не найден.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_sub.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("c1[{0}] = {1}",
        L'A', c1[L'A']);
    System::Console::WriteLine("c1[{0}] = {1}",
        L'b', c1[L'b']);

    // redisplay altered contents
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // alter mapped values and redisplay
    c1[L'A'] = 10;
    c1[L'c'] = 13;
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
c1[A] = 0
c1[b] = 2
[A 0] [a 1] [b 2] [c 3]
[A 10] [a 1] [b 2] [c 13]
```

## <a name="rbegin"></a> MAP::rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или непосредственно перед началом пустой последовательности. Таким образом, он задает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало отображаемой в обратном порядке управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_rbegin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*rbegin() = [c 3]
*++rbegin() = [b 2]
```

## <a name="reference"></a> MAP::Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_map_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="rend"></a> MAP::rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает Обратный итератор, указывающий непосредственно перед началом управляемой последовательности. Таким образом, он задает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец отображаемой в обратном порядке управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_rend.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rend();
    --rit;
    --rit;
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*--rend() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --rend() = [b 2]
*--rend() = [a 1]
```

## <a name="reverse_iterator"></a> MAP::reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект неопределенного типа `T3` , можно использовать в качестве обратного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_map_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="size"></a> MAP::size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Используется для определения числа элементов в данный момент в управляемой последовательности. Если вас интересуют ли последовательность имеет ненулевой размер, см. в разделе [map::empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)`()`.

### <a name="example"></a>Пример

```cpp
// cliext_map_size.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Mymap::make_value(L'd', 4));
    c1.insert(Mymap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> MAP::size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает элемент неотрицательное число.

### <a name="example"></a>Пример

```cpp
// cliext_map_size_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::size_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="swap"></a> MAP::Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Примечания

Функция-член меняет местами управляемые последовательности между `this` и *правой*. Она делает это в константном времени и не создает исключения. Можно использовать как быстрый способ местами содержимое двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_map_swap.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymap c2;
    c2.insert(Mymap::make_value(L'd', 4));
    c2.insert(Mymap::make_value(L'e', 5));
    c2.insert(Mymap::make_value(L'f', 6));
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[d 4] [e 5] [f 6]
[d 4] [e 5] [f 6]
[a 1] [b 2] [c 3]
```

## <a name="to_array"></a> MAP::to_array (STL/CLR)

Копирует управляемой последовательности в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает массив, содержащий управляемой последовательности. Вы можете использовать его для получения копии управляемой последовательности в форме массива.

### <a name="example"></a>Пример

```cpp
// cliext_map_to_array.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Mymap::value_type>^ a1 = c1.to_array();

    c1.insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Mymap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="upper_bound"></a> MAP::upper_bound (STL/CLR)

Находит конец диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет последний элемент `X` в управляемой последовательности с эквивалентным упорядочением для *ключ*. Если такого элемента не существует или если `X` является последним элементом в управляемой последовательности, он возвращает [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий первый элемент после `X`. Оно позволяет найти конец последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_map_upper_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Mymap::iterator it = c1.upper_bound(L'a');
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.upper_bound(L'b');
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
upper_bound(L'x')==end() = True
*upper_bound(L'a') = [b 2]
*upper_bound(L'b') = [c 3]
```

## <a name="value_comp"></a> MAP::value_comp (STL/CLR)

Копирует делегат упорядочения для значения двух элементов.

### <a name="syntax"></a>Синтаксис

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Оно позволяет сравнить значения двух элементов.

### <a name="example"></a>Пример

```cpp
// cliext_map_value_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_compare"></a> MAP::value_compare (STL/CLR)

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
// cliext_map_value_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_type"></a> MAP::value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `generic_value`.

### <a name="example"></a>Пример

```cpp
// cliext_map_value_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="op_neq"></a> оператор! = (map) (STL/CLR)

Список не равен сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator!=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператор возвращает `!(left == right)`. Можно использовать для тестирования ли *левой* не упорядочен так же, как *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_ne.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="op_lt"></a> оператор&lt; (map) (STL/CLR)

Список меньше, чем сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator<(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Оператор функция возвращает значение true, если, для низшей позиции `i` для которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае возвращается `left->size() < right->size()` можно использовать для тестирования ли *левой* упорядочен до *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_lt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="op_lteq"></a> оператор&lt;= (map) (STL/CLR)

Меньше или равно списка сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator<=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператор возвращает `!(right < left)`. Можно использовать для тестирования ли *левой* не упорядочен после *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_le.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="op_eq"></a> оператор == (map) (STL/CLR)

Сравнение равно списка.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator==(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператор возвращает значение true, только в том случае, если управляются последовательностей *левой* и *правой* имеют одинаковую длину и для каждой позиции `i`, `left[i] ==` `right[i]`. Можно использовать для тестирования ли *левой* упорядочен так же, как *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_eq.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="op_gt"></a> оператор&gt; (map) (STL/CLR)

Список больше, чем сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator>(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли *левой* упорядочен после *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_gt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="op_gteq"></a> оператор&gt;= (map) (STL/CLR)

Список, больше или равно сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    bool operator>=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*left*<br/>
Левый контейнер для сравнения.

*right*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператор возвращает `!(left` `<` `right)`. Можно использовать для тестирования ли *левой* не упорядочен до *правой* при двух сопоставлениях, по сравнению с элементом за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_map_operator_ge.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```