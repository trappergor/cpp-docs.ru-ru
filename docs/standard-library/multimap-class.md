---
title: Класс multimap
ms.date: 10/18/2018
f1_keywords:
- map/std::multimap
- map/std::multimap::allocator_type
- map/std::multimap::const_iterator
- map/std::multimap::const_pointer
- map/std::multimap::const_reference
- map/std::multimap::const_reverse_iterator
- map/std::multimap::difference_type
- map/std::multimap::iterator
- map/std::multimap::key_compare
- map/std::multimap::key_type
- map/std::multimap::mapped_type
- map/std::multimap::pointer
- map/std::multimap::reference
- map/std::multimap::reverse_iterator
- map/std::multimap::size_type
- map/std::multimap::value_type
- map/std::multimap::begin
- map/std::multimap::cbegin
- map/std::multimap::cend
- map/std::multimap::clear
- map/std::multimap::count
- map/std::multimap::crbegin
- map/std::multimap::crend
- map/std::multimap::emplace
- map/std::multimap::emplace_hint
- map/std::multimap::empty
- map/std::multimap::end
- map/std::multimap::equal_range
- map/std::multimap::erase
- map/std::multimap::find
- map/std::multimap::get_allocator
- map/std::multimap::insert
- map/std::multimap::key_comp
- map/std::multimap::lower_bound
- map/std::multimap::max_size
- map/std::multimap::rbegin
- map/std::multimap::rend
- map/std::multimap::size
- map/std::multimap::swap
- map/std::multimap::upper_bound
- map/std::multimap::value_comp
helpviewer_keywords:
- std::multimap [C++]
- std::multimap [C++], allocator_type
- std::multimap [C++], const_iterator
- std::multimap [C++], const_pointer
- std::multimap [C++], const_reference
- std::multimap [C++], const_reverse_iterator
- std::multimap [C++], difference_type
- std::multimap [C++], iterator
- std::multimap [C++], key_compare
- std::multimap [C++], key_type
- std::multimap [C++], mapped_type
- std::multimap [C++], pointer
- std::multimap [C++], reference
- std::multimap [C++], reverse_iterator
- std::multimap [C++], size_type
- std::multimap [C++], value_type
- std::multimap [C++], begin
- std::multimap [C++], cbegin
- std::multimap [C++], cend
- std::multimap [C++], clear
- std::multimap [C++], count
- std::multimap [C++], crbegin
- std::multimap [C++], crend
- std::multimap [C++], emplace
- std::multimap [C++], emplace_hint
- std::multimap [C++], empty
- std::multimap [C++], end
- std::multimap [C++], equal_range
- std::multimap [C++], erase
- std::multimap [C++], find
- std::multimap [C++], get_allocator
- std::multimap [C++], insert
- std::multimap [C++], key_comp
- std::multimap [C++], lower_bound
- std::multimap [C++], max_size
- std::multimap [C++], rbegin
- std::multimap [C++], rend
- std::multimap [C++], size
- std::multimap [C++], swap
- std::multimap [C++], upper_bound
- std::multimap [C++], value_comp
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
ms.openlocfilehash: 2f6ae50a825d6eff2eb64c84b209fa81c4b7949f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363854"
---
# <a name="multimap-class"></a>Класс multimap

Класс multimap в стандартной библиотеке С++ используется для хранения и извлечения данных из коллекции, в которой каждый элемент является парой, хранящей значение данных и ключ сортировки. Значение ключа может не быть уникальным и применяется для автоматической сортировки данных. Значение элементов в multimap, но не связанное с ним значение ключа, можно изменить напрямую. Значения ключей, связанные со старыми элементами, необходимо удалить и вставить новые значения ключей, связанные с новыми элементами.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Type,
    class Traits=less <Key>,
    class Allocator=allocator <pair  <const Key, Type>>>
class multimap;
```

### <a name="parameters"></a>Параметры

*Ключ*\
Тип данных ключа для сохранения в контейнере multimap.

*Тип*\
Тип данных элемента, который необходимо сохранить в контейнере multimap.

*Черты*\
Тип, предоставляющий объект функции, который может сравнивать два значения элемента как ключи сортировки, чтобы определить их относительный порядок в контейнере multimap. Бинарный предикат `less<Key>` является значением по умолчанию.

В C++ 14 вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Более подробные сведения см. в разделе [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#heterogeneous-lookup-in-associative-containers-c14)

*Распределителя*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для сопоставления. Этот аргумент является необязательным, и значением по умолчанию является `allocator<pair <const Key, Type> >`.

## <a name="remarks"></a>Remarks

Класс multimap в стандартной библиотеке С++ — это:

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа.

- Реверсивный, поскольку он предоставляет двунаправленные итераторы для получения доступа к его элементам.

- Сортированный, поскольку его элементы упорядочены по значениям ключей в контейнере в соответствии с заданной функцией сравнения.

- Множественный, поскольку его элементы не обязательно должны иметь уникальные ключи, т. е. одному значению ключа может соответствовать много значений данных элементов, связанных с ним.

- Является контейнером ассоциативной пары, поскольку его значения данных элементов отличаются от его значений ключей.

- Шаблон класса, поскольку предоставляемая им функциональность является универсальной и не зависит от конкретного типа данных, содержащихся в качестве элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Итератор, предоставляемый классом map, является двунаправленным итератором, но функции-члены класса [insert](#insert) и [multimap](#multimap) имеют версии, которые принимают в качестве параметров-шаблонов более слабый итератор ввода, чьи функциональные требования ниже, чем гарантируемые классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функциональных возможностей, но его достаточно, чтобы иметь возможность осмысленно говорить о диапазоне итераторов `[First, Last)`, в контексте функций-членов класса.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, являются эффективными и в среднем выполняют их пропорционально логарифму числа элементов в контейнере. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.

Класс multimap рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Модель для этого типа структуры — это упорядоченный список ключевых слов со связанными значениями строк, предоставляющими, например, определения, в которых слова не всегда обладают уникальными определениями. Если же ключевые слова обладают уникальными определениями, и ключи уникальны, то сопоставление будет предпочтительным контейнером. Если же сохранен только список слов, то в качестве контейнера необходимо выбрать набор. Если допускается повторное использование слов, то подходящей структурой контейнера будет multiset.

Мультиотображение упорядочивает контролируемую им последовательность посредством вызова хранимого объекта-функции типа [key_compare](#key_compare). Хранимый объект — это функция сравнения, доступ к которой можно получить вызовом функции-члена [key_comp](#key_comp). В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат `f(x,y)` является объектом функции, обладающим двумя объектами аргументов `x` и `y`, а также возвращаемым значением true или false. Порядок, заданный для набора, является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и переходящим и если эквивалентность является переходящей, где два объекта `x` и `y` заданы как эквивалентные при том, что `f(x,y)` и `f(y,x)` имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

В C++ 14 вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Более подробные сведения см. в разделе [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[multimap](#multimap)|Создает контейнер `multimap`, который является пустым или копией части или целого другого контейнера `multimap`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `multimap`.|
|[const_iterator](#const_iterator)|Тип, который обеспечивает двунаправленный итератор, который может `multimap`читать **конст элемент** в .|
|[const_pointer](#const_pointer)|Тип, который обеспечивает указатель на элемент `multimap` **const** в .|
|[const_reference](#const_reference)|Тип, который предоставляет ссылку на **конст** элемент, хранящийся в `multimap` для чтения и выполнения **конст-операций.**|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, который обеспечивает двунаправленный итератор, который может `multimap`читать любой **конст элемент** в .|
|[difference_type](#difference_type)|Тип целого числа со знаком, пригодный для представления количества элементов в контейнере `multimap` в диапазоне между элементами, на которые указывают итераторы.|
|[Итератор](#iterator)|Тип, который предоставляет различие между 2 итераторами, относящимися к элементам в одном контейнере `multimap`.|
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `multimap`.|
|[Key_type](#key_type)|Тип, описывающий объект ключа сортировки, составляющий каждый элемент контейнера `multimap`.|
|[mapped_type](#mapped_type)|Тип, который представляет тип данных, хранящийся в контейнере `multimap`.|
|[указатель](#pointer)|Тип, который обеспечивает указатель на элемент `multimap` **const** в .|
|[Ссылки](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `multimap`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `multimap`.|
|[size_type](#size_type)|Неподписанный тип integer, который обеспечивает указатель на `multimap` **элемент const** в .|
|[Value_type](#value_type)|Тип, предоставляющий объект функции, который может сравнить два элемента в качестве ключей сортировки для определения их относительного порядка в контейнере `multimap`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Начать](#begin)|Возвращает итератор, обращающийся к первый элемент в контейнере `multimap`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `multimap`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `multimap`.|
|[Ясно](#clear)|Стирает все элементы в `multimap`.|
|[count](#count)|Возвращает число элементов в контейнере `multimap`, ключи которых соответствуют ключу, заданному параметром.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `multimap`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `multimap`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `multimap`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `multimap` с подсказкой о размещении|
|[Пустой](#empty)|Проверяет, пуст ли `multimap`.|
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `multimap`.|
|[equal_range](#equal_range)|Находит диапазон элементов, где ключ элемента соответствует заданному значению.|
|[erase](#erase)|Удаляет элемент или диапазон элементов в `multimap` с заданных позиций или удаляет элементы, соответствующие заданному ключу.|
|[Найти](#find)|Возвращает итератор, который обращается к первому местоположению элемента в контейнере `multimap` с ключом, эквивалентным указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `multimap`.|
|[Вставить](#insert)|Вставляет элемент или диапазон элементов в `multimap`.|
|[key_comp](#key_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в контейнере `multimap`.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `multimap` с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `multimap`.|
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `multimap`.|
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `multimap`.|
|[Размер](#size)|Возвращает количество элементов в контейнере `multimap`.|
|[Своп](#swap)|Выполняет обмен элементами между двумя объектами `multimap`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `multimap` с ключом, который больше указанного ключа.|
|[value_comp](#value_comp)|Функция-член возвращает объект функции, который определяет порядок элементов в `multimap` путем сравнения значения ключа.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Заменяет элементы `multimap` копией другого `multimap`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<map>

**Пространство имен:** std

Пары ( **ключ**, **значение**) хранятся в мультиотображении в виде объектов типа `pair`. Класс pair требует заголовка \<utility>, который автоматически включается \<map>.

## <a name="multimapallocator_type"></a><a name="allocator_type"></a>мультикарта::allocator_type

Тип, который представляет класс распределителя для объекта-мультиотображения.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Пример

См. пример использования [get_allocator](#get_allocator) в качестве примера использования `allocator_type`.

## <a name="multimapbegin"></a><a name="begin"></a>мультикарта::начало

Возвращает итератор, адресующий первый элемент в мультиотображении.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий первый элемент в мультиотображении или положение после пустого мультиотображения.

### <a name="example"></a>Пример

```cpp
// multimap_begin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: const_iterator m1_cIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 0, 0 ) );
   m1.insert ( Int_Pair ( 1, 1 ) );
   m1.insert ( Int_Pair ( 2, 4 ) );

   m1_cIter = m1.begin ( );
   cout << "The first element of m1 is " << m1_cIter -> first << endl;

   m1_Iter = m1.begin ( );
   m1.erase ( m1_Iter );

   // The following 2 lines would err as the iterator is const
   // m1_cIter = m1.begin ( );
   // m1.erase ( m1_cIter );

   m1_cIter = m1.begin( );
   cout << "First element of m1 is now " << m1_cIter -> first << endl;
}
```

```Output
The first element of m1 is 0
First element of m1 is now 1
```

## <a name="multimapcbegin"></a><a name="cbegin"></a>мультикарта::cbegin

Возвращает **конст-итератор,** который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**Конст** двунаправленный доступ итератор, который указывает на первый элемент диапазона, или расположение только за `cbegin() == cend()`пределами конца пустого диапазона (для пустого диапазона, ).

### <a name="remarks"></a>Remarks

Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере, `Container` рассмотреть в качестве изменяемого (не **конст)** контейнер любого рода, который поддерживает `begin()` и `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="multimapcend"></a><a name="cend"></a>мультикарта::cend

Возвращает **конст-итератор,** который обращается к местоположению только за пределами последнего элемента в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

**Конст** двунаправленный доступ итератор, который указывает только за пределами диапазона.

### <a name="remarks"></a>Remarks

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере, `Container` рассмотреть в качестве изменяемого (не **конст)** контейнер любого рода, который поддерживает `end()` и `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="multimapclear"></a><a name="clear"></a>мультикарта::ясно

Стирает все элементы мультиотображения.

```cpp
void clear();
```

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена multimap::clear.

```cpp
// multimap_clear.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1;
   multimap<int, int>::size_type i;
   typedef pair<int, int> Int_Pair;

   m1.insert(Int_Pair(1, 1));
   m1.insert(Int_Pair(2, 4));

   i = m1.size();
   cout << "The size of the multimap is initially "
        << i << "." << endl;

   m1.clear();
   i = m1.size();
   cout << "The size of the multimap after clearing is "
        << i << "." << endl;
}
```

```Output
The size of the multimap is initially 2.
The size of the multimap after clearing is 0.
```

## <a name="multimapconst_iterator"></a><a name="const_iterator"></a>мультикарта::const_iterator

Тип, предоставляющий двунаправленный итератор, который может читать элемент **const** в мультиотображении.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Remarks

Тип `const_iterator`нельзя использовать для изменения значения элемента.

Определенные `const_iterator` мультикартой точки к объектам [value_type,](#value_type)которые имеют тип. `pair<const Key, Type>` Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.

Чтобы указать `const_iterator` *cIter,* указывающий на элемент в **->** мультикарте, используйте оператора.

Чтобы получить доступ к значению ключа `cIter->first`для элемента, используйте, что `(*cIter).first`эквивалентно. Чтобы получить доступ к значению отображеного `cIter->second`datum `(*cIter).second`для элемента, используйте, что эквивалентно .

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="multimapconst_pointer"></a><a name="const_pointer"></a>мультикарта::const_pointer

Тип, предоставляющий указатель на элемент **const** в мультиотображении.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Remarks

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-мультиотображении следует использовать [iterator](#iterator).

## <a name="multimapconst_reference"></a><a name="const_reference"></a>мультикарта::const_reference

Тип, который предоставляет ссылку на элемент **const**, хранящийся в мультиотображении, для чтения и выполнения операций **const**.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Пример

```cpp
// multimap_const_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of the first element in the multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of the first element in the multimap is "
        << Ref2 << "." << endl;
}
```

```Output
The key of the first element in the multimap is 1.
The data value of the first element in the multimap is 10.
```

## <a name="multimapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>мультикарта::const_reverse_iterator

Тип, предоставляющий ссылку на двунаправленный итератор, который может читать любые элементы **const** в мультиотображении.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора мультиотображения в обратном порядке.

Определенные `const_reverse_iterator` мультикартой точки к объектам [value_type,](#value_type)которые имеют тип. `pair<const Key, Type>` Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.

Чтобы указать `const_reverse_iterator` *crIter,* указывающий на элемент в **->** мультикарте, используйте оператора.

Чтобы получить доступ к значению ключа `crIter->first`для элемента, используйте, что `(*crIter).first`эквивалентно. Чтобы получить доступ к значению отображеного `crIter->second`datum `(*crIter).first`для элемента, используйте, что эквивалентно .

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="multimapcount"></a><a name="count"></a>мультикарта:количество

Возвращает число элементов в мультиотображении, ключи которых совпадают с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*Ключ*\
Ключ для сравнения с ключами элементов мультиотображения.

### <a name="return-value"></a>Возвращаемое значение

Число элементов, ключи сортировки которых совпадают с ключом параметра. 0, если мультиотображение не содержит ни одного элемента с совпадающим ключом.

### <a name="remarks"></a>Remarks

Функция-член возвращает число элементов в диапазоне

\[lower_bound *(ключ),* upper_bound *(ключ)*)

которые имеют ключевой *ключ*значение .

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена multimap::count.

```cpp
// multimap_count.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
    using namespace std;
    multimap<int, int> m1;
    multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 1));
    m1.insert(Int_Pair(1, 4));
    m1.insert(Int_Pair(2, 1));

    // Elements do not need to have unique keys in multimap,
    // so duplicates are allowed and counted
    i = m1.count(1);
    cout << "The number of elements in m1 with a sort key of 1 is: "
         << i << "." << endl;

    i = m1.count(2);
    cout << "The number of elements in m1 with a sort key of 2 is: "
         << i << "." << endl;

    i = m1.count(3);
    cout << "The number of elements in m1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in m1 with a sort key of 1 is: 2.
The number of elements in m1 with a sort key of 2 is: 2.
The number of elements in m1 with a sort key of 3 is: 0.
```

## <a name="multimapcrbegin"></a><a name="crbegin"></a>мультикарта:crbegin

Возвращает константный итератор, адресующий первый элемент в обратном мультиотображении.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [мультиотображении](../standard-library/multimap-class.md) или адресующий то, что было последним элементом в `multimap` до замены его порядка на противоположный.

### <a name="remarks"></a>Remarks

`crbegin` используется с обратным `multimap` так же, как [begin](#begin) используется с обычным `multimap`.

Если возвращаемое значение `crbegin`, то объект `multimap` невозможно изменить.

`crbegin` можно использовать для перебора `multimap` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// multimap_crbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crbegin( );
   cout << "The first element of the reversed multimap m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed multimap m1 is 3.
```

## <a name="multimapcrend"></a><a name="crend"></a>мультикарта::crend

Возвращает константный итератор, адресующий положение после последнего элемента в обратном мультиотображении.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном [мультиотображении](../standard-library/multimap-class.md) (положение, которое предшествовало первому элементу в `multimap` до изменения его порядка на противоположный).

### <a name="remarks"></a>Remarks

`crend` используется с обратным `multimap` так же, как [multimap::end](#end) используется с обычным `multimap`.

Если возвращаемое значение `crend`, то объект `multimap` невозможно изменить.

`crend` используется, чтобы проверить, достиг ли итератор конца `multimap`.

Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// multimap_crend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crend( );
   m1_crIter--;
   cout << "The last element of the reversed multimap m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed multimap m1 is 1.
```

## <a name="multimapdifference_type"></a><a name="difference_type"></a>мультикарта::difference

Целочисленный тип со знаком, который можно использовать для представления числа элементов в мультиотображении в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Remarks

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. Это `difference_type` обычно используется для представления числа элементов в диапазоне -*первый*, *последний*) между `first` итераторами `last`и , включает в себя элемент, указанный `first` и диапазон элементов до, но не включая, элемент, указанный `last`.

Обратите внимание, что хотя `difference_type` доступна для всех итераторов, соответствующих требованиям для входного итератора, что включает класс двунаправленных итераторов, поддерживаемых обратными контейнерами, например наборами, вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, например векторами.

### <a name="example"></a>Пример

```cpp
// multimap_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <map>
#include <algorithm>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );

   // The following will insert as multimap keys are not unique
   m1.insert ( Int_Pair ( 2, 30 ) );

   multimap <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;
   m1_bIter = m1.begin( );
   m1_eIter = m1.end( );

   // Count the number of elements in a multimap
   multimap <int, int>::difference_type  df_count = 0;
   m1_Iter = m1.begin( );
   while ( m1_Iter != m1_eIter )
   {
      df_count++;
      m1_Iter++;
   }

   cout << "The number of elements in the multimap m1 is: "
        << df_count << "." << endl;
}
```

```Output
The number of elements in the multimap m1 is: 4.
```

## <a name="multimapemplace"></a><a name="emplace"></a>мультикарта::место

Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|*Args*|Аргументы, передаваемые для создания элемента, вставляемого в мультиотображение.|

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Remarks

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Если во время вставки создается исключение, контейнер не изменяется и исключение создается повторно.

[value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

### <a name="example"></a>Пример

```cpp
// multimap_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: " << endl;

    for (const auto& p : m) {
        cout << "(" << p.first <<  "," << p.second << ") ";
    }

    cout << endl;
}

int main()
{
    multimap<string, string> m1;

    m1.emplace("Anna", "Accounting");
    m1.emplace("Bob", "Accounting");
    m1.emplace("Carmine", "Engineering");

    cout << "multimap modified, now contains ";
    print(m1);
    cout << endl;

    m1.emplace("Bob", "Engineering");

    cout << "multimap modified, now contains ";
    print(m1);
    cout << endl;
}
```

## <a name="multimapemplace_hint"></a><a name="emplace_hint"></a>мультикарта::emplace_hint

Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|*Args*|Аргументы, передаваемые для создания элемента, вставляемого в мультиотображение.|
|*Где*|Место начала поиска правильной точки вставки. (Если эта точка сразу же предшествует, *где,* вставка может произойти в амортизированное постоянное время вместо логарифмического времени.)|

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Remarks

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Если во время размещения создается исключение, состояние контейнера не изменяется.

[value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

Пример кода см. в разделе [map::emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="multimapempty"></a><a name="empty"></a>мультикарта::пустой

Проверяет, что мультиотображение пусто.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если мультиотображение пустое; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// multimap_empty.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2;

   typedef pair <int, int> Int_Pair;
   m1.insert ( Int_Pair ( 1, 1 ) );

   if ( m1.empty( ) )
      cout << "The multimap m1 is empty." << endl;
   else
      cout << "The multimap m1 is not empty." << endl;

   if ( m2.empty( ) )
      cout << "The multimap m2 is empty." << endl;
   else
      cout << "The multimap m2 is not empty." << endl;
}
```

```Output
The multimap m1 is not empty.
The multimap m2 is empty.
```

## <a name="multimapend"></a><a name="end"></a>мультикарта::конец

Возврат итератора после конца.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор после конца. Если мультикарта пуста, то `multimap::end() == multimap::begin()`.

### <a name="remarks"></a>Remarks

**end** используется для проверки, прошел ли итератор конец своего мультиотображения.

Не следует сбрасывать ссылку у значения, возвращаемого **end**.

Пример кода см. в разделе [multimap::find](#find).

## <a name="multimapequal_range"></a><a name="equal_range"></a>мультикарта::equal_range

Находит диапазон элементов, где ключ элемента соответствует заданному значению.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*Ключ*\
Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых является [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.

Для доступа к первому итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **во-первых,** и к dereference нижней \* `pr`связаны итератор, использование ( . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **второй** и при справок верхней границы \* `pr`итератора, использование ( . **второй**).

### <a name="example"></a>Пример

```cpp
// multimap_equal_range.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multimap <int, int, less<int> > IntMMap;
   IntMMap m1;
   multimap <int, int> :: const_iterator m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;
   p1 = m1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the multimap m1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the multimap m1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   m1_RcIter = m1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << m1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair "
        << "returned by equal_range( 2 )." << endl;

   p2 = m1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )
      cout << "The multimap m1 doesn't have an element "
           << "with a key less than 4." << endl;
   else
      cout << "The element of multimap m1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the multimap m1 is: 20.
The upper bound of the element with a key of 2 in the multimap m1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The multimap m1 doesn't have an element with a key less than 4.
```

## <a name="multimaperase"></a><a name="erase"></a>мультикарта::стереть

Удаляет элемент или диапазон элементов в мультиотображении из указанных позиций или удаляет элементы, соответствующие заданному ключу.

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

*Где*\
Положение удаляемого элемента.

*Первый*\
Положение первого удаляемого элемента.

*Последний*\
Позиция после последнего элемента для удаления.

*Ключ*\
Ключевое значение элементов для удаления.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов это двунаправленный итератор, обозначающий первый элемент, остающийся после любых удаленных элементов, или элемент в конце сопоставления, если таких элементов нет.

Для третьей функции-члена возвращается количество элементов, которые были удалены из мультиотображения.

### <a name="remarks"></a>Remarks

Пример кода см. в разделе [map::erase](../standard-library/map-class.md#erase).

## <a name="multimapfind"></a><a name="find"></a>мультикарта::найти

Возвращает итератор, ссылающийся на элемент в мультикарте, ключ которого эквивалентен заданному ключу.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*Ключ*\
Значение ключа, с которым сравнивается ключ сортировки элемента из мультикарты, по которой выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор, ссылающийся на расположение элемента с указанным ключом или на расположение элемента после последнего элемента в мультикарте (`multimap::end()`), если для ключа не найдено совпадений.

### <a name="remarks"></a>Remarks

Функция-член возвращает итератор, который ссылается на элемент в мультикарте с ключом сортировки, эквивалентным ключу аргумента согласно двоичному предикату, применяющему упорядочение на основе отношения сравнения «меньше».

Если возвращенное значение `find` назначается `const_iterator`, то объект-мультиотображение изменить нельзя. Если значение `find` возврата назначено объекту `iterator`мультикарты, может быть изменено.

### <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4 /MTd
#include <map>
#include <iostream>
#include <vector>
#include <string>
#include <utility>  // make_pair()

using namespace std;

template <typename A, typename B> void print_elem(const pair<A, B>& p) {
    cout << "(" << p.first << ", " << p.second << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    multimap<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });
    cout << "The starting multimap m1 is (key, value):" << endl;
    print_collection(m1);

    vector<pair<int, string>> v;
    v.push_back(make_pair(43, "Tc"));
    v.push_back(make_pair(41, "Nb"));
    v.push_back(make_pair(46, "Pd"));
    v.push_back(make_pair(42, "Mo"));
    v.push_back(make_pair(44, "Ru"));
    v.push_back(make_pair(44, "Ru")); // attempt a duplicate

    cout << "Inserting the following vector data into m1:" << endl;
    print_collection(v);

    m1.insert(v.begin(), v.end());

    cout << "The modified multimap m1 is (key, value):" << endl;
    print_collection(m1);
    cout << endl;
    findit(m1, 45);
    findit(m1, 6);
}
```

## <a name="multimapget_allocator"></a><a name="get_allocator"></a>мультикарта::get_allocator

Возвращает копию объекта-распределителя, использованного для создания мультиотображения.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, использованный мультиотображением.

### <a name="remarks"></a>Remarks

Распределители для класса multimap определяют, как класс управляет памятью. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// multimap_get_allocator.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int>::allocator_type m1_Alloc;
   multimap <int, int>::allocator_type m2_Alloc;
   multimap <int, double>::allocator_type m3_Alloc;
   multimap <int, int>::allocator_type m4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multimap <int, int> m1;
   multimap <int, int, allocator<int> > m2;
   multimap <int, double, allocator<double> > m3;

   m1_Alloc = m1.get_allocator( );
   m2_Alloc = m2.get_allocator( );
   m3_Alloc = m3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << m2.max_size( ) << ".\n" << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << m3.max_size( ) <<  ".\n" << endl;

   // The following line creates a multimap m4
   // with the allocator of multimap m1.
   map <int, int> m4( less<int>( ), m1_Alloc );

   m4_Alloc = m4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated via the other
   if( m1_Alloc == m4_Alloc )
   {
      cout << "The allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="multimapinsert"></a><a name="insert"></a>мультикарта:вставить

Вставляет элемент или диапазон элементов в множественное сопоставление.

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
|*Val*|Значение элемента, вставляемого в множественное сопоставление.|
|*Где*|Место начала поиска правильной точки вставки. (Если эта точка сразу же предшествует *Где,* вставка может произойти в амортизированное постоянное время вместо логарифмического времени.)|
|*ValTy*|Параметры шаблона, который определяет тип аргумента, который карта может использовать для построения элемента [value_type,](../standard-library/map-class.md#value_type)и совершенный вперед *Val* в качестве аргумента.|
|*Первый*|Позиция первого элемента, который следует скопировать.|
|*Последний*|Позиция непосредственно перед последним элементом, который следует скопировать.|
|*Inputiterator*|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).|
|*IList*|В [initializer_list,](../standard-library/initializer-list.md) из которых можно скопировать элементы.|

### <a name="return-value"></a>Возвращаемое значение

Одноэлементные функции-члены (1) и (2) возвращают итератор в позиции, где был вставлен новый элемент.

Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, указывающий на позицию, где был вставлен новый элемент.

### <a name="remarks"></a>Remarks

Эта функция не делает никакие указатели или ссылки недействительными, но она может сделать недействительными все итераторы контейнера.

Если во время вставки одного элемента вызывается исключение, состояние контейнера не изменяется. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

[value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, который принадлежит контейнеру. Для сопоставления `multimap<K, V>::value_type` — это `pair<const K, V>`. Значение элемента — это упорядоченная пара, в которой первый компонент эквивалентен значению ключа, а второй компонент — значению данных элемента.

Функция члена диапазона (5) вставляет последовательность значений элементов в мультикарту, соответствующую каждому `[First, Last)`элементу, адресованному итератором в диапазоне; таким образом, *Last* не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `m.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `m`.

Функция-член списка инициализатора (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в сопоставление.

Для вставки элемента, созданного на месте (то есть без операций копирования или перемещения), см. разделы [multimap::emplace](#emplace) и [multimap::emplace_hint](#emplace_hint).

### <a name="example"></a>Пример

```cpp
// multimap_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
#include <vector>
#include <utility>  // make_pair()

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: ";

    for (const auto& p : m) {
        cout << "(" << p.first << ", " << p.second << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multimap<int, int> m1;
    // call insert(const value_type&) version
    m1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    m1.insert(make_pair(2, 20));

    cout << "The original key and mapped values of m1 are:" << endl;
    print(m1);

    // intentionally attempt a duplicate, single element
    m1.insert(make_pair(1, 111));

    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);

    // single element, with hint
    m1.insert(m1.end(), make_pair(3, 30));
    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multimap<int, int> m2;
    vector<pair<int, int>> v;
    v.push_back(make_pair(43, 294));
    v.push_back(make_pair(41, 262));
    v.push_back(make_pair(45, 330));
    v.push_back(make_pair(42, 277));
    v.push_back(make_pair(44, 311));

    cout << "Inserting the following vector data into m2:" << endl;
    print(v);

    m2.insert(v.begin(), v.end());

    cout << "The modified key and mapped values of m2 are:" << endl;
    print(m2);
    cout << endl;

    // The templatized versions move-constructing elements
    multimap<int, string>  m3;
    pair<int, string> ip1(475, "blue"), ip2(510, "green");

    // single element
    m3.insert(move(ip1));
    cout << "After the first move insertion, m3 contains:" << endl;
    print(m3);

    // single element with hint
    m3.insert(m3.end(), move(ip2));
    cout << "After the second move insertion, m3 contains:" << endl;
    print(m3);
    cout << endl;

    multimap<int, int> m4;
    // Insert the elements from an initializer_list
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });
    cout << "After initializer_list insertion, m4 contains:" << endl;
    print(m4);
    cout << endl;
}
```

## <a name="multimapiterator"></a><a name="iterator"></a>мультикарта:Iterator

Тип, предоставляющий двунаправленный итератор, который может читать или изменять любой элемент в мультиотображении.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Remarks

Определенные `iterator` мультикартой точки к объектам [value_type,](#value_type)которые имеют тип. `pair<const Key, Type>` Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.

Чтобы указать `iterator` *Iter* на элемент в мультикарте, используйте **->** оператора.

Чтобы получить доступ к значению ключа `Iter->first`для элемента, используйте, что `(*Iter).first`эквивалентно. Чтобы получить доступ к значению отображеного `Iter->second`datum `(*Iter).second`для элемента, используйте, что эквивалентно .

Тип `iterator` может быть использован для изменения значения элемента.

### <a name="example"></a>Пример

См. пример объявления и использования `iterator` см. в разделе [begin](#begin).

## <a name="multimapkey_comp"></a><a name="key_comp"></a>мультикарта::key_comp

Извлекает копию объекта сравнения, использованного для упорядочивания ключей в мультиотображении.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую мультиотображение использует для упорядочивания своих элементов.

### <a name="remarks"></a>Remarks

Хранимый объект определяет функцию-член

`bool operator( const Key& x, const Key& y);`

которая возвращает true если *x* строго предшествует *y* в порядке сортировки.

### <a name="example"></a>Пример

```cpp
// multimap_key_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   multimap <int, int, less<int> > m1;
   multimap <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of m1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of m1."
           << endl;
   }

   multimap <int, int, greater<int> > m2;
   multimap <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of m2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of m2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of m1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of m2.
```

## <a name="multimapkey_compare"></a><a name="key_compare"></a>мультикарта::key_compare

Тип, который предоставляет объект-функцию, которая может сравнить два ключа сортировки для определения относительного порядка двух элементов в мультиотображении.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Remarks

`key_compare` является синонимом для параметра-шаблона `Traits`.

Более подробную информацию по `Traits` см. в разделе [Класс multimap](../standard-library/multimap-class.md).

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="multimapkey_type"></a><a name="key_type"></a>мультикарта::key_type

Тип, описывающий объект-ключ сортировки, который входит в каждый элемент мультиотображения.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Remarks

`key_type` является синонимом для параметра-шаблона `Key`.

Более подробную информацию по `Key` см. в подразделе "Примечания" раздела [Класс multimap](../standard-library/multimap-class.md).

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="multimaplower_bound"></a><a name="lower_bound"></a>мультикарта::lower_bound

Возвращает итератор, указывающий на первый элемент в мультиотображении с ключом, который равен указанному ключу или больше его.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*Ключ*\
Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор или `const_iterator`, адресующий положение элемента в мультиотображении, ключ которого равен ключу-аргументу или больше его, или адресующий положение после последнего элемента в мультиотображении, если сопоставление для ключа не найдено.

Если возвращенное значение `lower_bound` назначается `const_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `lower_bound` назначается **iterator**, то объект-мультиотображение можно изменить.

### <a name="example"></a>Пример

```cpp
// multimap_lower_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.lower_bound( 2 );
   cout << "The element of multimap m1 with a key of 2 is: "
        << m1_RcIter -> second << "." << endl;

   m1_RcIter = m1.lower_bound( 3 );
   cout << "The first element of multimap m1 with a key of 3 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   m1_RcIter = m1.lower_bound( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The multimap m1 doesn't have an element "
              << "with a key of 4." << endl;
   else
      cout << "The element of multimap m1 with a key of 4 is: "
                << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the multimap can be
   // found using a dereferenced iterator addressing the location
   m1_AcIter = m1.end( );
   m1_AcIter--;
   m1_RcIter = m1.lower_bound( m1_AcIter -> first );
   cout << "The first element of m1 with a key matching\n"
        << "that of the last element is: "
        << m1_RcIter -> second << "." << endl;

   // Note that the first element with a key equal to
   // the key of the last element is not the last element
   if ( m1_RcIter == --m1.end( ) )
      cout << "This is the last element of multimap m1."
           << endl;
   else
      cout << "This is not the last element of multimap m1."
           << endl;
}
```

```Output
The element of multimap m1 with a key of 2 is: 20.
The first element of multimap m1 with a key of 3 is: 20.
The multimap m1 doesn't have an element with a key of 4.
The first element of m1 with a key matching
that of the last element is: 20.
This is not the last element of multimap m1.
```

## <a name="multimapmapped_type"></a><a name="mapped_type"></a>мультикарта::mapped_type

Тип, представляющий тип данных, хранящихся в мультиотображении.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Remarks

`mapped_type` является синонимом для параметра-шаблона `Type`.

Более подробную информацию по `Type` см. в разделе [Класс multimap](../standard-library/multimap-class.md).

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="multimapmax_size"></a><a name="max_size"></a>мультикарта::max_size

Возвращает максимальную длину мультиотображения.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина мультиотображения.

### <a name="example"></a>Пример

```cpp
// multimap_max_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: size_type i;

   i = m1.max_size( );
   cout << "The maximum possible length "
        << "of the multimap is " << i << "." << endl;
}
```

## <a name="multimapmultimap"></a><a name="multimap"></a>мультикарта:multimap

Создает мультиотображение, которое является пустым или копией всего или части другого мультиотображения.

```cpp
multimap();

explicit multimap(
    const Traits& Comp);

multimap(
    const Traits& Comp,
    const Allocator& Al);

map(
    const multimap& Right);

multimap(
    multimap&& Right);

multimap(
    initializer_list<value_type> IList);

multimap(
    initializer_list<value_type> IList,
    const Compare& Comp);

multimap(
    initializer_list<value_type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|*Аль*|Класс распределителя памяти для использования для этого объекта-мультиотображения. Значение по умолчанию — Allocator.|
|*Комп*|Функция сравнения типа `constTraits` для использования при упорядочивании элементов в сопоставлении. Значение по умолчанию — `Traits`.|
|*Правильно*|Сопоставление, копией которого будет создаваемое сопоставление.|
|*Первый*|Положение первого элемента в диапазоне копируемых элементов.|
|*Последний*|Положение первого элемента после диапазона копируемых элементов.|
|*IList*|Объект initializer_list, из которого копируются элементы.|

### <a name="remarks"></a>Remarks

Все конструкторы сохраняют тип объекта-распределителя, управляющего памятью для мультиотображения. Затем его можно получить путем вызова [get_allocator](#get_allocator). Параметр-распределитель часто не указывается в объявлениях класса и в макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы инициализируют свои мультиотображения.

Все конструкторы сохраняют объект-функцию типа `Traits`, используемую для установления порядка ключей мультиотображения. Затем эту функцию можно получить путем вызова [key_comp](#key_comp).

Первые три конструктора указывают пустую начальную мультикарту, второй - тип функции сравнения *(Comp),* который будет использоваться при определении порядка элементов, а третий явно указывает тип разлляции (*Al*) для использования. Ключевое слово **явно** подавляет определенные виды автоматического преобразования типа.

Четвертый конструктор указывает копию мультикарты *Право*.

Пятый конструктор определяет копию мультикарты, перемещая *вправо.*

Шестой, седьмой и восьмой конструкторы копируют члены initializer_list.

Следующие три конструктора копируют диапазон `[First, Last)` сопоставления с повышением точности при указании типа функции сравнения класса `Traits` и распределителя.

### <a name="example"></a>Пример

```cpp
// multimap_ctor.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    typedef pair <int, int> Int_Pair;

    // Create an empty multimap m0 of key type integer
    multimap <int, int> m0;

    // Create an empty multimap m1 with the key comparison
    // function of less than, then insert 4 elements
    multimap <int, int, less<int> > m1;
    m1.insert(Int_Pair(1, 10));
    m1.insert(Int_Pair(2, 20));
    m1.insert(Int_Pair(3, 30));
    m1.insert(Int_Pair(4, 40));

    // Create an empty multimap m2 with the key comparison
    // function of greater than, then insert 2 elements
    multimap <int, int, less<int> > m2;
    m2.insert(Int_Pair(1, 10));
    m2.insert(Int_Pair(2, 20));

    // Create a multimap m3 with the
    // allocator of multimap m1
    multimap <int, int>::allocator_type m1_Alloc;
    m1_Alloc = m1.get_allocator();
    multimap <int, int> m3(less<int>(), m1_Alloc);
    m3.insert(Int_Pair(3, 30));

    // Create a copy, multimap m4, of multimap m1
    multimap <int, int> m4(m1);

    // Create a multimap m5 by copying the range m1[ first,  last)
    multimap <int, int>::const_iterator m1_bcIter, m1_ecIter;
    m1_bcIter = m1.begin();
    m1_ecIter = m1.begin();
    m1_ecIter++;
    m1_ecIter++;
    multimap <int, int> m5(m1_bcIter, m1_ecIter);

    // Create a multimap m6 by copying the range m4[ first,  last)
    // and with the allocator of multimap m2
    multimap <int, int>::allocator_type m2_Alloc;
    m2_Alloc = m2.get_allocator();
    multimap <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);

    cout << "m1 =";
    for (auto i : m1)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m2 =";
    for (auto i : m2)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m3 =";
    for (auto i : m3)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m4 =";
    for (auto i : m4)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m5 =";
    for (auto i : m5)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m6 =";
    for (auto i : m6)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m8 by copying in an initializer_list
    multimap<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };
    cout << "m8: = ";
    for (auto i : m8)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m9 with an initializer_list and a comparator
    multimap<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());
    cout << "m9: = ";
    for (auto i : m9)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m10 with an initializer_list, a comparator, and an allocator
    multimap<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());
    cout << "m10: = ";
    for (auto i : m10)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

}
```

## <a name="multimapoperator"></a><a name="op_eq"></a>мультикарта:оператор

Заменяет элементы мультиотображения копией другого мультиотображения.

```cpp
multimap& operator=(const multimap& right);

multimap& operator=(multimap&& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|*Правильно*|[Мультиотображение](../standard-library/multimap-class.md), которое будет копироваться в `multimap`.|

### <a name="remarks"></a>Remarks

После стирания любых `multimap`существующих `operator=` элементов в , либо копии или перемещает содержимое *право* в `multimap`.

### <a name="example"></a>Пример

```cpp
// multimap_operator_as.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
   {
   using namespace std;
   multimap<int, int> v1, v2, v3;
   multimap<int, int>::iterator iter;

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

## <a name="multimappointer"></a><a name="pointer"></a>мультикарта::pоинтер

Тип, предоставляющий указатель на элемент мультиотображения.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Remarks

Тип `pointer` может быть использован для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-мультиотображении следует использовать [iterator](#iterator).

## <a name="multimaprbegin"></a><a name="rbegin"></a>мультикарта::rbegin

Возвращает итератор, адресующий первый элемент в обратном мультиотображении.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном мультиотображении или адресующий то, что было последним элементом в мультиотображении до изменения его порядка на противоположный.

### <a name="remarks"></a>Remarks

`rbegin` используется с обратным мультиотображением так же, как [begin](#begin) используется с прямым мультиотображением.

Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект-мультиотображение можно изменить.

`rbegin` можно использовать для перебора мультиотображения в обратном порядке.

### <a name="example"></a>Пример

```cpp
// multimap_rbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: reverse_iterator m1_rIter;
   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rbegin( );
   cout << "The first element of the reversed multimap m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a multimap in a forward order
   cout << "The multimap is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a multimap in a reverse order
   cout << "The reversed multimap is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A multimap element can be erased by dereferencing its key
   m1_rIter = m1.rbegin( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multimap is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed multimap m1 is 3.
The multimap is: 1 2 3 .
The reversed multimap is: 3 2 1 .
After the erasure, the first element in the reversed multimap is 2.
```

## <a name="multimapreference"></a><a name="reference"></a>мультикарта:ссылка

Тип, который предоставляет ссылку на элемент, хранящийся в мультиотображении.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Пример

```cpp
// multimap_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the multimap is "
        << Ref2 << "." << endl;

   // The non-const_reference can be used to modify the
   // data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the multimap is 1.
The data value of first element in the multimap is 10.
The modified data value of first element is 15.
```

## <a name="multimaprend"></a><a name="rend"></a>мультикарта::ренд

Возвращает итератор, адресующий положение после последнего элемента в обратном мультиотображении.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном мультиотображении (положение, которое предшествовало первому элементу в мультиотображении до изменения его порядка на противоположный).

### <a name="remarks"></a>Remarks

`rend` используется с обратным мультиотображением так же, как [end](../standard-library/map-class.md#end) используется с обычным мультиотображением.

Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект-мультиотображение можно изменить.

`rend` можно использовать для проверки, достиг ли обратный итератор конца своего мультиотображения.

Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// multimap_rend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: reverse_iterator m1_rIter;
   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "The last element of the reversed multimap m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a multimap in a forward order
   cout << "The multimap is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a multimap in a reverse order
   cout << "The reversed multimap is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A multimap element can be erased by dereferencing to its key
   m1_rIter = --m1.rend( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed multimap is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed multimap m1 is 1.
The multimap is: 1 2 3 .
The reversed multimap is: 3 2 1 .
After the erasure, the last element in the reversed multimap is 2.
```

## <a name="multimapreverse_iterator"></a><a name="reverse_iterator"></a>мультикарта::reverse_iterator

Тип, предоставляющий двунаправленный итератор, который может читать и изменять элемент в обратном мультиотображении.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип `reverse_iterator` используется для перебора мультиотображения в обратном порядке.

Определенные `reverse_iterator` мультикартой точки к объектам [value_type,](#value_type)которые имеют тип. `pair<const Key, Type>` Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.

Чтобы указать `reverse_iterator` *rIter,* указывающий на элемент в **->** мультикарте, используйте оператора.

Чтобы получить доступ к значению ключа `rIter->first`для элемента, используйте, что `(*rIter).first`эквивалентно. Чтобы получить доступ к значению отображеного `rIter->second`datum `(*rIter).second`для элемента, используйте, что эквивалентно .

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="multimapsize"></a><a name="size"></a>мультикарта:размер

Возвращает число элементов в мультиотображении.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина мультиотображения.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена multimap::size.

```cpp
// multimap_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    multimap<int, int> m1, m2;
    multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    i = m1.size();
    cout << "The multimap length is " << i << "." << endl;

    m1.insert(Int_Pair(2, 4));
    i = m1.size();
    cout << "The multimap length is now " << i << "." << endl;
}
```

```Output
The multimap length is 1.
The multimap length is now 2.
```

## <a name="multimapsize_type"></a><a name="size_type"></a>мультикарта::size_type

Тип целого числа без знака, который подсчитывает число элементов в мультиотображении.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="multimapswap"></a><a name="swap"></a>мультикарта::swap

Обмен элементами между двумя мультиотображениями.

```cpp
void swap(
    multimap<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Мультиотображение, предоставляющее элементы для обмена, или мультиотображение, элементы которого должны быть заменены на элементы мультиотображения `left`.

### <a name="remarks"></a>Remarks

Функция-член не делает недействительным ссылки, указатели или итераторы, обозначающие элементы в двух мультиотображениях, для которых выполняется обмен элементами.

### <a name="example"></a>Пример

```cpp
// multimap_swap.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   multimap <int, int>::iterator m1_Iter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m2.insert ( Int_Pair ( 10, 100 ) );
   m2.insert ( Int_Pair ( 20, 200 ) );
   m3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   m1.swap( m2 );

   cout << "After swapping with m2, multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( m1, m3 );

   cout << "After swapping with m3, multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original multimap m1 is: 10 20 30.
After swapping with m2, multimap m1 is: 100 200.
After swapping with m3, multimap m1 is: 300.
```

## <a name="multimapupper_bound"></a><a name="upper_bound"></a>мультикарта::upper_bound

Возвращает итератор, указывающий на первый элемент в мультиотображении с ключом, который больше указанного ключа.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*Ключ*\
Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор или `const_iterator`, адресующий положение элемента в мультиотображении с ключом, который равен ключу-аргументу или больше него, либо адресует положение после последнего элемента в мультиотображении, если соответствие для ключа не найдено.

Если возвращенное значение назначается `const_iterator`, то объект-мультиотображение изменить нельзя. Если значение возврата назначено `iterator`объекту мультикарты, может быть изменено.

### <a name="example"></a>Пример

```cpp
// multimap_upper_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m1.insert ( Int_Pair ( 3, 40 ) );

   m1_RcIter = m1.upper_bound( 1 );
   cout << "The 1st element of multimap m1 with "
        << "a key greater than 1 is: "
        << m1_RcIter -> second << "." << endl;

   m1_RcIter = m1.upper_bound( 2 );
   cout << "The first element of multimap m1 with a key "
        << " greater than 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   m1_RcIter = m1.lower_bound( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The multimap m1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of multimap m1 with a key of 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the multimap can be
   // found using a dereferenced iterator addressing the location
   m1_AcIter = m1.begin( );
   m1_RcIter = m1.upper_bound( m1_AcIter -> first );
   cout << "The first element of m1 with a key greater than\n"
        << "that of the initial element of m1 is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The 1st element of multimap m1 with a key greater than 1 is: 20.
The first element of multimap m1 with a key  greater than 2 is: 30.
The multimap m1 doesn't have an element with a key of 4.
The first element of m1 with a key greater than
that of the initial element of m1 is: 20.
```

## <a name="multimapvalue_comp"></a><a name="value_comp"></a>мультикарта::value_comp

Функция-член возвращает объект-функцию, которая определяет порядок элементов в мультиотображении путем сравнения их значений ключа.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию сравнения, которую мультиотображение использует для упорядочения своих элементов.

### <a name="remarks"></a>Remarks

Для мультикарты *м,* если два элемента *e1**(k1,* *d1)* и *e2* `value_type`*(k2,* *d2*) являются объектами типа, где *k1* `mapped_type`и `m.value_comp(e1, e2)` *k2* являются их ключами `key_type` типа и *d1* и *d2* являются их данными типа, то эквивалентно . `m.key_comp(k1, k2)`

### <a name="example"></a>Пример

```cpp
// multimap_value_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   multimap <int, int, less<int> > m1;
   multimap <int, int, less<int> >::value_compare vc1 = m1.value_comp( );
   multimap<int,int>::iterator Iter1, Iter2;

   Iter1= m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );
   Iter2= m1.insert ( multimap <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *Iter1, *Iter2 ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does "
           << "not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1( *Iter2, *Iter1 ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does "
           << "not precede the element ( 1,10 )."
           << endl;
   }
}
```

```Output
The element ( 1,10 ) precedes the element ( 2,5 ).
The element ( 2,5 ) does not precede the element ( 1,10 ).
```

## <a name="multimapvalue_type"></a><a name="value_type"></a>мультикарта::value_type

Тип, представляющий тип объекта, который хранится в виде элемента в мультиотображении.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="example"></a>Пример

```cpp
// multimap_value_type.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   multimap <int, int> m1;
   multimap <int, int> :: key_type key1;
   multimap <int, int> :: mapped_type mapped1;
   multimap <int, int> :: value_type value1;
   multimap <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );

   // Compare another way to insert objects into a hash_multimap
   m1.insert ( cInt2Int ( 2, 20 ) );

   // Initializing key1 and mapped1
   key1 = ( m1.begin( ) -> first );
   mapped1 = ( m1.begin( ) -> second );

   cout << "The key of first element in the multimap is "
        << key1 << "." << endl;

   cout << "The data value of first element in the multimap is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

```Output
The key of first element in the multimap is 1.
The data value of first element in the multimap is 10.
The keys of the mapped elements are: 1 2.
The values of the mapped elements are: 10 20.
```

## <a name="see-also"></a>См. также раздел

[Контейнеры](../cpp/containers-modern-cpp.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Стандартная библиотечная справка по СЗ](../standard-library/cpp-standard-library-reference.md)
