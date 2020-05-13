---
title: set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::set::begin
- cliext::set::clear
- cliext::set::const_iterator
- cliext::set::const_reference
- cliext::set::const_reverse_iterator
- cliext::set::count
- cliext::set::difference_type
- cliext::set::empty
- cliext::set::end
- cliext::set::equal_range
- cliext::set::erase
- cliext::set::find
- cliext::set::generic_container
- cliext::set::generic_iterator
- cliext::set::generic_reverse_iterator
- cliext::set::generic_value
- cliext::set::insert
- cliext::set::iterator
- cliext::set::key_comp
- cliext::set::key_compare
- cliext::set::key_type
- cliext::set::lower_bound
- cliext::set::make_value
- cliext::set::operator=
- cliext::set::rbegin
- cliext::set::reference
- cliext::set::rend
- cliext::set::reverse_iterator
- cliext::set::set
- cliext::set::size
- cliext::set::size_type
- cliext::set::swap
- cliext::set::to_array
- cliext::set::upper_bound
- cliext::set::value_comp
- cliext::set::value_compare
- cliext::set::value_type
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
- operator!= (set) member [STL/CLR]
- operator< (set) member [STL/CLR]
- operator<= (set) member [STL/CLR]
- operator== (set) member [STL/CLR]
- operator> (set) member [STL/CLR]
- operator>= (set) member [STL/CLR]
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
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- set member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
ms.openlocfilehash: 38b0a3278efd10ef5cc989a5fc900bf82d377eae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320310"
---
# <a name="set-stlclr"></a>set (STL/CLR)

Класс шаблона описывает объект, который управляет последовательностью элементов различной длины, которая имеет двунаправленный доступ. Контейнер используется `set` для управления последовательностью элементов в качестве (почти) сбалансированного упорядоченного дерева узлов, каждый из которых хранения одного элемента.

В описании `GValue` ниже, `GKey`так же, как , который, в свою очередь, так же, `Key^`как *ключ,* если последний тип реф, и в этом случае это .

## <a name="syntax"></a>Синтаксис

```cpp
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

### <a name="parameters"></a>Параметры

*Клавиша*<br/>
Тип ключа для элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/set>

**Название:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[set::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[set::difference_type (STL/CLR)](#difference_type)|Тип (возможно подписанного) расстояния между двумя элементами.|
|[set::generic_container (STL/CLR)](#generic_container)|Тип общего интерфейса для контейнера.|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для общего интерфейса для контейнера.|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для общего интерфейса для контейнера.|
|[set::generic_value (STL/CLR)](#generic_value)|Тип элемента для общего интерфейса для контейнера.|
|[set::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[set::key_compare (STL/CLR)](#key_compare)|Делегат заказа на два ключа.|
|[set::key_type (STL/CLR)](#key_type)|Тип ключа упорядочения.|
|[set::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[set::size_type (STL/CLR)](#size_type)|Тип (неотрицательного) расстояния между двумя элементами.|
|[set::value_compare (STL/CLR)](#value_compare)|Делегат заказа для двух значений элементов.|
|[set::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[set::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[set::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[set::count (STL/CLR)](#count)|Подсчитывает элементы, соответствующие указанному ключу.|
|[set::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[set::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[set::equal_range (STL/CLR)](#equal_range)|Находит диапазон, соответствующий указанному ключу.|
|[set::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[set::find (STL/CLR)](#find)|Определяет элемент, соответствующий указанному ключу.|
|[set::insert (STL/CLR)](#insert)|Добавляет элементы.|
|[set::key_comp (STL/CLR)](#key_comp)|Копирует делегата-заказа на два ключа.|
|[set::lower_bound (STL/CLR)](#lower_bound)|Находит начало диапазона, который соответствует указанному ключу.|
|[set::make_value (STL/CLR)](#make_value)|Строит объект значения.|
|[set::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[set::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[set::set (STL/CLR)](#set)|Создает объект контейнера.|
|[set::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[set::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[set::to_array (STL/CLR)](#to_array)|Копирует контролируемую последовательность в новый массив.|
|[set::upper_bound (STL/CLR)](#upper_bound)|Находит конец диапазона, который соответствует указанному ключу.|
|[set::value_comp (STL/CLR)](#value_comp)|Копирует делегата заказа для двух значений элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|
|[оператор! (набор) (STL/CLR)](#op_neq)|Определяет, не `set` равен ли `set` объект другому объекту.|
|[оператор< (набор) (STL/CLR)](#op_lt)|Определяет, является `set` ли объект `set` меньше, чем другой объект.|
|[оператор<(набор) (STL/CLR)](#op_lteq)|Определяет, является `set` ли объект меньше или `set` равен другому объекту.|
|[operator== (set) (STL/CLR)](#op_eq)|Определяет, приравнивается `set` ли `set` объект к другому объекту.|
|[оператор> (набор) (STL/CLR)](#op_gt)|Определяет, является `set` ли объект `set` больше другого объекта.|
|[оператор>(набор) (STL/CLR)](#op_gteq)|Определяет, является `set` ли объект больше или `set` равен другому объекту.|

## <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Дублирование объекта.|
|<xref:System.Collections.IEnumerable>|Последовательность через элементы.|
|<xref:System.Collections.ICollection>|Поддержание группы элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность через набранные элементы.|
|<xref:System.Collections.Generic.ICollection%601>|Поддержание группы набранных элементов.|
|ITree\<ключ, значение>|Поддержание общего контейнера.|

## <a name="remarks"></a>Remarks

Объект выделяет и освобождает хранилище для последовательности, которая контролируется в виде отдельных узлов. Он вставляет элементы в (почти) сбалансированное дерево, которое он держит в порядке, изменяя связи между узлами, никогда не копируя содержимое одного узла другому. Это означает, что вы можете вставить и удалить элементы свободно, не нарушая оставшиеся элементы.

Объект заказывает последовательность, которую он контролирует, вызывая сохраненный объект делегата [набора типа::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Можно указать сохраненный объект делегата при построении набора; если вы указываете объект делегата, `operator<(key_type, key_type)`по умолчанию является сравнение . Вы получаете доступ к этому сохраненному объекту, вызывая набор функций [участника::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.

Такой объект делегата должен наложить строгий слабый порядок на клавишах [набора типов::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Это означает, что `X` для `Y`любых двух ключей и:

`key_comp()(X, Y)`возвращает тот же результат Boolean на каждом вызове.

Если `key_comp()(X, Y)` это правда, то `key_comp()(Y, X)` должно быть ложным.

Если `key_comp()(X, Y)` это правда, то, `X` как `Y`говорят, приказал, прежде чем .

Если `!key_comp()(X, Y) && !key_comp()(Y, X)` это правда, то `X` и, `Y` как говорят, эквивалентный порядок.

Для любого элемента, `X` который предшествует `Y` в контролируемой последовательности, `key_comp()(Y, X)` является ложным. (Для объекта делегата по умолчанию клавиши никогда не уменьшаются в стоимости.) В отличие от [набора](../dotnet/set-stl-clr.md)классов `set` шаблонов, объект класса шаблонов не требует, чтобы ключи для всех элементов были уникальными. (Два или более ключей могут иметь эквивалентный заказ.)

Каждый элемент служит как ey, так и значением. Последовательность представлена таким образом, что позволяет поиск, вставка и удаление произвольного элемента с рядом операций, пропорциональных logarithm числа элементов в последовательности (логарифмическое время). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

Набор поддерживает двунаправленные итераторы, что означает, что вы можете перейти к соседним элементам, учитывая итератор, который обозначает элемент в контролируемой последовательности. Специальный головной узор соответствует итератору, возвращенному [набором::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Вы можете decrement этот итератор для достижения последнего элемента в контролируемой последовательности, если присутствует. Вы можете приравнять набор итератора для достижения головного узла, и он будет сравниваться равным `end()`. Но вы не можете отображение итератора, возвращенного `end()`.

Обратите внимание, что вы не можете ссылаться на набор элементов непосредственно с учетом его численного положения, что требует случайного доступа итератора.

Набор итератора хранит ручку к связанного с ней узлам набора, который, в свою очередь, хранит ручку в связанном с ним контейнере. Итераторы можно использовать только с связанными с ними контейнерными объектами. Набор итератора остается действительным до тех пор, пока связанный с ним узла набора связан с некоторым набором. Кроме того, действительный итератор является уклончивым - его можно использовать для доступа или изменения значения элемента, который он обозначает, - до тех пор, пока он не равен `end()`.

Стирание или удаление элемента вызывает деструктор для его хранимого значения. Уничтожение контейнера стирает все элементы. Таким образом, контейнер, тип элемента которого является классом реф, гарантирует, что никакие элементы не переживут контейнер. Обратите внимание, однако, что контейнер с ручками *не* разрушает его элементы.

## <a name="members"></a>Участники

## <a name="setbegin-stlclr"></a><a name="begin"></a>набор::начало (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает двунаправленный итератор, который обозначает первый элемент контролируемой последовательности, или просто после окончания пустой последовательности. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_set_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::iterator it = c1.begin();
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

## <a name="setclear-stlclr"></a><a name="clear"></a>набор:ясно (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Remarks

Функция участника эффективно вызывает [набор::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [набор::начало (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [набор::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`())`. Вы используете его для обеспечения того, чтобы контролируемая последовательность была пустой.

### <a name="example"></a>Пример

```cpp
// cliext_set_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setconst_iterator-stlclr"></a><a name="const_iterator"></a>набор::const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T2` типа, который может служить постоянным двунаправленным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reference-stlclr"></a><a name="const_reference"></a>набор::const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Remarks

Тип описывает постоянную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_set_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>набор::const_reverse_iterator (STL/CLR)

Тип постоянного обратного итератора для контролируемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T4` типа, который может служить постоянным обратным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setcount-stlclr"></a><a name="count"></a>набор:count (STL/CLR)

Определяет количество элементов, соответствующих заданному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Remarks

Функция участника возвращает количество элементов в контролируемой последовательности, которые имеют эквивалентный заказ с *ключом.* Используется для определения количества элементов в управляемой последовательности, ключ которых в данный момент совпадает с заданным ключом.

### <a name="example"></a>Пример

```cpp
// cliext_set_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setdifference_type-stlclr"></a><a name="difference_type"></a>набор::difference-type (STL/CLR)

Типы подписанного расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Remarks

Тип описывает возможно отрицательное количество элементов.

### <a name="example"></a>Пример

```cpp
// cliext_set_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (Myset::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="setempty-stlclr"></a><a name="empty"></a>набор:пустой (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Remarks

Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [набору::размер (STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0`. Вы используете его, чтобы проверить, является ли набор пустым.

### <a name="example"></a>Пример

```cpp
// cliext_set_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setend-stlclr"></a><a name="end"></a>набор:end (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает двунаправленный итератор, который указывает только за пределами контролируемой последовательности. Вы используете его для получения итератора, который обозначает конец контролируемой последовательности; его статус не изменяется, если изменяется длина контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    Myset::iterator it = c1.end();
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

## <a name="setequal_range-stlclr"></a><a name="equal_range"></a>набор::equal_range (STL/CLR)

Находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Remarks

Функция участника возвращает набор пара `cliext::pair<iterator, iterator>(` итераторов::lower_bound [(STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [набор::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)`(key))`. Вы используете его для определения диапазона элементов, наиболее поданных в настоящее время в контролируемой последовательности, которые соответствуют указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_set_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_iter Pairii;
int main()
    {
    Myset c1;
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

## <a name="seterase-stlclr"></a><a name="erase"></a>набор::erase (STL/CLR)

Удаляет элементы в указанных позициях.

### <a name="syntax"></a>Синтаксис

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для стирания.

*Ключ*<br/>
Ключевое значение для стирания.

*Последний*<br/>
Конец диапазона для стирания.

*Где*<br/>
Элемент для стирания.

### <a name="remarks"></a>Remarks

Функция первого члена удаляет элемент контролируемой последовательности, указанной *куда,* и возвращает итератор, который обозначает первый элемент, оставшийся за пределами удаленного элемента, или [установить::end (STL/CLR),](../dotnet/set-end-stl-clr.md) `()` если такого элемента не существует. Вы используете его для удаления одного элемента.

Функция второго члена удаляет элементы контролируемой последовательности в диапазоне ,`first` `last`и возвращает итератор, который обозначает `end()` первый элемент, оставшийся за пределами удаленных элементов, или если такого элемента не существует. Вы используете его для удаления ноль или более смежных элементов.

Функция третьего члена удаляет любой элемент контролируемой последовательности, ключ которого имеет эквивалентный заказ на *ключ,* и возвращает количество удаленных элементов. Вы используете его для удаления и подсчета всех элементов, которые соответствуют указанному ключу.

Каждое стирание элементов занимает время, пропорциональное logarithm количества элементов в контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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
    Myset::iterator it = c1.end();
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

## <a name="setfind-stlclr"></a><a name="find"></a>набор:find (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Remarks

Если хотя бы один элемент в контролируемой последовательности имеет эквивалентный порядок с *ключом,* функция члена возвращает итератор, обозначающий один из этих элементов; в противном случае он возвращает [набор::конец (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Вы используете его, чтобы найти элемент, наданный в настоящее время в контролируемой последовательности, который соответствует указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_set_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setgeneric_container-stlclr"></a><a name="generic_container"></a>набор::generic_container (STL/CLR)

Тип общего интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Remarks

Тип описывает общий интерфейс для этого класса контейнеров шаблонов.

### <a name="example"></a>Пример

```cpp
// cliext_set_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
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

## <a name="setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>набор::generic_iterator (STL/CLR)

Тип итератора для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает общий итератор, который может быть использован с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>набор::generic_reverse_iterator (STL/CLR)

Тип обратного итератора для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает общий обратный итератор, который может быть использован с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_reverse_iterator gcit = gc1->rbegin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="setgeneric_value-stlclr"></a><a name="generic_value"></a>набор::generic_value (STL/CLR)

Тип элемента для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Remarks

Тип описывает объект типа, `GValue` описывающий значение сохраненного элемента для использования с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_set_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setinsert-stlclr"></a><a name="insert"></a>набор:вставка (STL/CLR)

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

*Последний*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Валь*<br/>
Ключевое значение для вставки.

*Где*<br/>
Где в контейнер вставить (только подсказка).

### <a name="remarks"></a>Remarks

Каждая из функций участника вставляет последовательность, указанную оставшимися операндами.

Функция первого члена стремится вставить *val*элемент с значением val `X`и возвращает пару значений. Если `X.second` это `X.first` так, обозначает вновь вставленный элемент; в `X.first` противном случае обозначает элемент с эквивалентным упорядочением, который уже существует и новый элемент не вставляется. Вы используете его для вставки одного элемента.

Функция второго элемента вставляет элемент с значением *val,* используя *где* в качестве подсказки (для повышения производительности), и возвращает итератор, который обозначает вновь вставленный элемент. Вы используете его для вставки одного элемента, который может быть рядом с элементом вы знаете.

Функция третьего члена вставляет `last`последовательность ,`first`). Вы используете его для вставки ноль или более элементов, скопированных из другой последовательности.

Функция четвертого члена вставляет последовательность, обозначенную *справа.* Вы используете его для вставки последовательности, описанной регистратором.

Каждая вставка элементов занимает время, пропорциональное logarithm количества элементов в контролируемой последовательности. Вставка может произойти в амортизированное постоянное время, однако, учитывая подсказку, которая обозначает элемент, прилегающий к точке вставки.

### <a name="example"></a>Пример

```cpp
// cliext_set_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_bool Pairib;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

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
    Myset c2;
    Myset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    Myset c3;
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
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="setiterator-stlclr"></a><a name="iterator"></a>набор:Iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T1` типа, который может служить двунаправленным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setkey_comp-stlclr"></a><a name="key_comp"></a>комплект:key_comp (STL/CLR)

Копирует делегата-заказа на два ключа.

### <a name="syntax"></a>Синтаксис

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает делегата заказа, используемого для заказа контролируемой последовательности. Используется для сравнения двух ключей.

### <a name="example"></a>Пример

```cpp
// cliext_set_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
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

## <a name="setkey_compare-stlclr"></a><a name="key_compare"></a>набор::key_compare (STL/CLR)

Делегат заказа на два ключа.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Remarks

Тип является синонимом делегата, определяющего порядок его ключевых аргументов.

### <a name="example"></a>Пример

```cpp
// cliext_set_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
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

## <a name="setkey_type-stlclr"></a><a name="key_type"></a>набор::key_type (STL/CLR)

Тип ключа упорядочения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом *ключевого*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_set_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using key_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setlower_bound-stlclr"></a><a name="lower_bound"></a>комплект:lower_bound (STL/CLR)

Находит начало диапазона, который соответствует указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Remarks

Функция члена определяет первый `X` элемент в контролируемой последовательности, который имеет эквивалентный заказ *на ключ.* Если такого элемента не существует, он возвращает [набор::end (STL/CLR);](../dotnet/set-end-stl-clr.md)`()` в противном случае он возвращает `X`итератор, который обозначает . Вы используете его, чтобы найти начало последовательности элементов, наданных в настоящее время в контролируемой последовательности, которые соответствуют указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_set_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setmake_value-stlclr"></a><a name="make_value"></a>набор::make_value (STL/CLR)

Строит объект значения.

### <a name="syntax"></a>Синтаксис

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключевое значение для использования.

### <a name="remarks"></a>Remarks

Функция элемента `value_type` возвращает объект, ключ от которого является *ключевым.* Вы используете его для составления объекта, пригодного для использования с несколькими другими функциями-членами.

### <a name="example"></a>Пример

```cpp
// cliext_set_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(Myset::make_value(L'a'));
    c1.insert(Myset::make_value(L'b'));
    c1.insert(Myset::make_value(L'c'));

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setoperator-stlclr"></a><a name="op_as"></a>набор:оператор (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Remarks

Оператор-член копирует *право* на объект, а затем возвращается. `*this` Вы используете его, чтобы заменить контролируемую последовательность с копией контролируемой последовательности в *правой*.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="setrbegin-stlclr"></a><a name="rbegin"></a>набор:rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает обратный итератор, который обозначает последний элемент контролируемой последовательности, или просто после начала пустой последовательности. Таким образом, он задает для обратной последовательности параметр `beginning`. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_set_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    Myset::reverse_iterator rit = c1.rbegin();
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

## <a name="setreference-stlclr"></a><a name="reference"></a>набор:reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Remarks

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_set_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setrend-stlclr"></a><a name="rend"></a>набор::rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает обратный итератор, который указывает только за началом контролируемой последовательности. Таким образом, он задает для обратной последовательности параметр `end`. Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_set_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::reverse_iterator rit = c1.rend();
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

## <a name="setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>набор::reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T3` типа, который может служить обратным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setset-stlclr"></a><a name="set"></a>набор:set (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
set();
explicit set(key_compare^ pred);
set(set<Key>% right);
set(set<Key>^ right);
template<typename InIter>
    setset(InIter first, InIter last);
template<typename InIter>
    set(InIter first, InIter last,
        key_compare^ pred);
set(System::Collections::Generic::IEnumerable<GValue>^ right);
set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для вставки.

*Последний*<br/>
Конец диапазона для вставки.

*Pred*<br/>
Заказ предиката для контролируемой последовательности.

*Правильно*<br/>
Объект или диапазон для вставки.

### <a name="remarks"></a>Remarks

Конструктор:

`set();`

инициализирует контролируемую последовательность без элементов, `key_compare()`с предикатом по умолчанию. Вы используете его для указания пустой начальной контролируемой последовательности с предикатом по умолчанию.

Конструктор:

`explicit set(key_compare^ pred);`

инициализирует контролируемую последовательность без элементов, с заказом предикат *predicate pred.* Вы используете его для указания пустой начальной контролируемой последовательности с указанным предикатом заказа.

Конструктор:

`set(set<Key>% right);`

инициализирует контролируемую`right.begin()`последовательность с последовательностью , `right.end()`с предикатом по умолчанию. Вы используете его, чтобы указать начальную контролируемую последовательность, которая является копией последовательности, контролируемой *правой*установкой объекта, с предикатом заказа по умолчанию.

Конструктор:

`set(set<Key>^ right);`

инициализирует контролируемую`right->begin()`последовательность с последовательностью , `right->end()`с предикатом по умолчанию. Вы используете его, чтобы указать начальную контролируемую последовательность, которая является копией последовательности, контролируемой *правой*установкой объекта, с предикатом заказа по умолчанию.

Конструктор:

`template<typename InIter> set(InIter first, InIter last);`

инициализирует контролируемую`first`последовательность с последовательностью , `last`с предикатом по умолчанию. Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности, с предикатом по умолчанию.

Конструктор:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

инициализирует контролируемую`first`последовательность с последовательностью , `last`с заказом предикат *predicate pred*. Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности, с указанным предикатом заказа.

Конструктор:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

инициализирует контролируемую последовательность с последовательностью, обозначенной *правой*рекомератором, с предикатом по умолчанию. Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности, описанной регистратором, с предикатом по умолчанию.

Конструктор:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

инициализирует контролируемую последовательность с последовательностью, обозначенной *правом*перечисления, с заказом предиката *pred.* Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности, описанной регистратором, с указанным предикатом заказа.

### <a name="example"></a>Пример

```cpp
// cliext_set_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
// construct an empty container
    Myset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an ordering rule
    Myset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    Myset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range and an ordering rule
    Myset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    Myset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration and an ordering rule
    Myset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct from a generic container
    Myset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myset c8(%c3);
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
c b a
a b c
c b a
a b c
c b a
c b a
a b c
```

## <a name="setsize-stlclr"></a><a name="size"></a>набор:размер (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Remarks

Функция-член возвращает длину управляемой последовательности. Вы используете его для определения количества элементов, наиболее наиболее контролируемых последовательности. Если все, что вас волнует, является ли последовательность имеет ненулевой размер, см. [set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)`()`

### <a name="example"></a>Пример

```cpp
// cliext_set_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setsize_type-stlclr"></a><a name="size_type"></a>комплект:size_type (STL/CLR)

Тип подписанного расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Remarks

Тип описывает неотрицательное количество элементов.

### <a name="example"></a>Пример

```cpp
// cliext_set_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::size_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="setswap-stlclr"></a><a name="swap"></a>набор:Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Remarks

Функция члена меняет контролируемые последовательности между `this` и *правыми.* Он делает это в постоянное время, и он не бросает никаких исключений. Вы используете его как быстрый способ обмена содержимого двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_set_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    Myset c2;
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

## <a name="setto_array-stlclr"></a><a name="to_array"></a>набор::to_array (STL/CLR)

Копирует контролируемую последовательность в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает массив, содержащий контролируемую последовательность. Вы используете его для получения копии контролируемой последовательности в форме массива.

### <a name="example"></a>Пример

```cpp
// cliext_set_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setupper_bound-stlclr"></a><a name="upper_bound"></a>набор::upper_bound (STL/CLR)

Находит конец диапазона, который соответствует указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Remarks

Функция члена определяет последний `X` элемент в контролируемой последовательности, который имеет эквивалентный заказ *на ключ.* Если такого элемента `X` не существует, или если это последний элемент в контролируемой последовательности, он возвращает [набор::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; в противном случае он возвращает итератор, `X`который обозначает первый элемент за пределами . Вы используете его, чтобы найти конец последовательности элементов, наданных в настоящее время в контролируемой последовательности, которые соответствуют указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_set_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setvalue_comp-stlclr"></a><a name="value_comp"></a>набор::value_comp (STL/CLR)

Копирует делегата заказа для двух значений элементов.

### <a name="syntax"></a>Синтаксис

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает делегата заказа, используемого для заказа контролируемой последовательности. Вы используете его для сравнения двух значений элементов.

### <a name="example"></a>Пример

```cpp
// cliext_set_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_compare-stlclr"></a><a name="value_compare"></a>набор::value_compare (STL/CLR)

Делегат заказа для двух значений элементов.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Remarks

Тип является синонимом делегата, определяющего упорядочение аргументов его ценности.

### <a name="example"></a>Пример

```cpp
// cliext_set_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_type-stlclr"></a><a name="value_type"></a>набор::value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом `generic_value`.

### <a name="example"></a>Пример

```cpp
// cliext_set_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using value_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-set-stlclr"></a><a name="op_neq"></a>оператор! (набор) (STL/CLR)

Список не равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left == right)`возвращается. Вы используете его для проверки того, не упорядочен ли *левый* порядок так же, как *и справа,* когда два набора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lt"></a>оператор&lt; (набор) (STL/CLR)

Список меньше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора возвращается верно, если, для самой низкой позиции, `i` для которой `!(right[i] < left[i])` это также верно, что `left[i] < right[i]`. В противном `left->size() < right->size()` случае, он возвращает Вы используете его для проверки того, *левая* упорядочена перед *правой,* когда два набора сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lteq"></a>оператор&lt;(набор) (STL/CLR)

Список меньше или равного сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(right < left)`возвращается. Вы используете его для проверки того, не заказываются ли *левые* после *справа,* когда два набора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-set-stlclr"></a><a name="op_eq"></a>оператор (набор) (STL/CLR)

Список равного сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора возвращается верно только в том случае, если последовательности, `i`контролируемые *левым* и *правым,* имеют одинаковую длину и для каждой позиции. `left[i] ==` `right[i]` Вы используете его для проверки того, упорядочен ли *левый* такой же, как *и справа,* когда два набора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gt"></a>оператор&gt; (набор) (STL/CLR)

Список больше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `right` `<` `left`возвращается. Вы используете его для проверки того, упорядочен ли *левый* после *справа,* когда два набора сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gteq"></a>оператор&gt;(набор) (STL/CLR)

Список больше или равного сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left < right)`возвращается. Вы используете его для проверки того, не заказывают ли *левый* перед *правой,* когда два набора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_set_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
