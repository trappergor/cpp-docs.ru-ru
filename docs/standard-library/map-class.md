---
title: Класс map | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- map/std::map
- map/std::map::allocator_type
- map/std::map::const_iterator
- map/std::map::const_pointer
- map/std::map::const_reference
- map/std::map::const_reverse_iterator
- map/std::map::difference_type
- map/std::map::iterator
- map/std::map::key_compare
- map/std::map::key_type
- map/std::map::mapped_type
- map/std::map::pointer
- map/std::map::reference
- map/std::map::reverse_iterator
- map/std::map::size_type
- map/std::map::value_type
- map/std::map::at
- map/std::map::begin
- map/std::map::cbegin
- map/std::map::cend
- map/std::map::clear
- map/std::map::count
- map/std::map::crbegin
- map/std::map::crend
- map/std::map::emplace
- map/std::map::emplace_hint
- map/std::map::empty
- map/std::map::end
- map/std::map::equal_range
- map/std::map::erase
- map/std::map::find
- map/std::map::get_allocator
- map/std::map::insert
- map/std::map::key_comp
- map/std::map::lower_bound
- map/std::map::max_size
- map/std::map::rbegin
- map/std::map::rend
- map/std::map::size
- map/std::map::swap
- map/std::map::upper_bound
- map/std::map::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::map [C++]
- std::map [C++], allocator_type
- std::map [C++], const_iterator
- std::map [C++], const_pointer
- std::map [C++], const_reference
- std::map [C++], const_reverse_iterator
- std::map [C++], difference_type
- std::map [C++], iterator
- std::map [C++], key_compare
- std::map [C++], key_type
- std::map [C++], mapped_type
- std::map [C++], pointer
- std::map [C++], reference
- std::map [C++], reverse_iterator
- std::map [C++], size_type
- std::map [C++], value_type
- std::map [C++], at
- std::map [C++], begin
- std::map [C++], cbegin
- std::map [C++], cend
- std::map [C++], clear
- std::map [C++], count
- std::map [C++], crbegin
- std::map [C++], crend
- std::map [C++], emplace
- std::map [C++], emplace_hint
- std::map [C++], empty
- std::map [C++], end
- std::map [C++], equal_range
- std::map [C++], erase
- std::map [C++], find
- std::map [C++], get_allocator
- std::map [C++], insert
- std::map [C++], key_comp
- std::map [C++], lower_bound
- std::map [C++], max_size
- std::map [C++], rbegin
- std::map [C++], rend
- std::map [C++], size
- std::map [C++], swap
- std::map [C++], upper_bound
- std::map [C++], value_comp
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccab97a7ac1fd0ad073a3f507dfa6687f311efc4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703928"
---
# <a name="map-class"></a>Класс map

Используется для хранения и извлечения данных из коллекции, в которой каждый элемент является парой, обладающей одновременно значением данных и ключом сортировки. Значение ключа уникально и применяется для автоматической сортировки данных.

Значение элемента в сопоставлении можно изменить напрямую. Значение ключа является константой, и его нельзя изменить. Вместо этого значения ключей, связанные со старыми элементами, необходимо удалить и вставить новые значения ключей для новых элементов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Type,
    class Traits = less<Key>,
    class Allocator=allocator<pair <const Key, Type>>>
class map;
```

### <a name="parameters"></a>Параметры

*Key*<br/>
Тип данных ключа для сохранения в сопоставлении.

*Тип*<br/>
Тип данных элемента для сохранения в сопоставлении.

*Признаки*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элемента как ключи сортировки, чтобы определить их относительный порядок в сопоставлении. Этот аргумент является необязательным, и в качестве значения по умолчанию используется бинарный предикат `less<Key>`.

В C++ 14 вы можете включить разнородный поиск, указав предикат std::less<>, не имеющий параметров типа. Дополнительные сведения см. в статье [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)

*Распределитель*<br/>
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для сопоставления. Этот аргумент является необязательным, и значением по умолчанию является `allocator<pair<const Key, Type> >`.

## <a name="remarks"></a>Примечания

Класс map в стандартной библиотеке С++ — это:

- Контейнер переменного размера, фактически извлекающий значения элементов на основе связанных значений ключей.

- Реверсивный, поскольку он предоставляет двунаправленные итераторы для получения доступа к его элементам.

- Сортируется, поскольку его элементы упорядочены по значениям ключей в соответствии с заданной функцией сравнения.

- Является уникальным, поскольку каждый его элемент должен обладать уникальным ключом.

- Является контейнером ассоциативной пары, поскольку его значения данных элементов отличаются от его значений ключей.

- Класс шаблона, поскольку функции, которые он предоставляет, являются универсальными и не зависят от типа элемента или ключа. Типы данных, используемые для элементов и ключей, определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Итератор, предоставляемый классом сопоставления, является двунаправленным итератором, но функции-члены класса [insert](#insert) и [map](#map) обладают версиями, принимающими в качестве параметров шаблона более слабый итератор ввода, чьи функциональные требования ниже, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов связаны уточнениями функциональности. Каждая концепция итератора обладает собственным набором требований, и совместимые с ней алгоритмы должны быть ограничены этими требованиями. Итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован следующему итератору в последовательности.

Рекомендуется выбирать тип контейнера на основе типа поиска и вставки, который требуется приложению. Ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают данные операторы, выполняют их в самом неблагоприятном случае, пропорционально логарифму числа элементов в контейнере. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие конкретно на удаленные элементы.

Рекомендуется сделать сопоставление предпочтительным ассоциативным контейнером, где условия, ассоциирующие значения с ключами, удовлетворяют требованиям приложения. Модель для этого типа структуры представляет собой упорядоченный список уникальных ключевых слов, с которыми связаны значения строк, предоставляющие определения. Если для слова существует несколько правильных определений и ключ не является уникальным, предпочтительным контейнером будет множественное сопоставление. Если сохранен обычный список слов, подходящим контейнером будет набор. Если допускается многократное использование слов, допустимым вариантом будет множественный набор.

Сопоставление упорядочивает контролируемые им элементы путем вызова сохраненного объекта-функции типа [key_compare](#key_compare). Этот сохраненный объект является функцией сравнения, для доступа к которой нужно обратиться к методу [key_comp](#key_comp). Как правило, любые два заданных элемента сравниваются, чтобы определить, что один из них меньше другого или они равны. После сравнения всех элементов создается упорядоченная последовательность неэквивалентных элементов.

> [!NOTE]
> Функция сравнения — это бинарный предикат, который вызывает строгое слабое упорядочение в стандартном математически смысле. Бинарный предикат f(x,y) является объектом функции, обладающим двумя объектами аргументов x и y и возвращаемым значением **true** или **false**. Порядок, заданный на набор является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и транзитивным и если эквивалентность является транзитивной, где два объекта x и y определяются как эквивалентные, когда и f(x,y) и f(y,x) равны **false** . Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т. е. все элементы упорядочиваются в соответствии друг с другом) и сопоставленные ключи будут неотличимы друг от друга.
>
> В C++ 14 вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Более подробные сведения см. в разделе [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[map](#map)|Создание списка определенного размера или с элементами, обладающими указанным значением или указанным `allocator`, либо в качестве копии другого сопоставления.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Typedef для класса `allocator` для объекта сопоставления.|
|[const_iterator](#const_iterator)|Typedef для двунаправленного итератора, который может читать **const** элемента в сопоставлении.|
|[const_pointer](#const_pointer)|Typedef для указателя на **const** элемент в сопоставлении.|
|[const_reference](#const_reference)|Typedef для ссылки на **const** элемент, хранящийся в сопоставлении для чтения и выполнения **const** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считать любой элемент **const** в сопоставлении.|
|[difference_type](#difference_type)|Цельночисленный Typedef со знаком для числа элементов в сопоставлении, в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Typedef для двунаправленного итератора, который может считывать или изменять любой элемент в сопоставлении.|
|[key_compare](#key_compare)|Typedef для объекта функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в сопоставлении.|
|[key_type](#key_type)|Typedef для ключа сортировки, хранящегося в каждом элементе сопоставления.|
|[mapped_type](#mapped_type)|Typedef для данных, хранящихся в каждом элементе сопоставления.|
|[pointer](#pointer)|Typedef для указателя на **const** элемент в сопоставлении.|
|[reference](#reference)|Typedef для ссылки на элемент, сохраненный в сопоставлении.|
|[reverse_iterator](#reverse_iterator)|Typedef для двунаправленного итератора, который может считывать или изменять элемент в обратном сопоставлении.|
|[size_type](#size_type)|Целочисленный Typedef без знака для числа элементов в сопоставлении|
|[value_type](#value_type)|Typedef для типа объекта, хранящейся в виде элемента в сопоставлении.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[at](#at)|Поиск элемента с заданным значением ключа.|
|[begin](#begin)|Возврат итератора, указывающего на первый элемент в сопоставлении.|
|[cbegin](#cbegin)|Возвращает итератор const, указывающего на первый элемент в сопоставлении.|
|[cend](#cend)|Возврат итератора const после конца.|
|[clear](#clear)|Стирает все элементы в сопоставлении.|
|[count](#count)|Возврат числа элементов в сопоставлении, ключ которого соответствует ключу, заданному в параметре.|
|[crbegin](#crbegin)|Возврат итератора const, указывающего на первый элемент в обратном сопоставлении.|
|[crend](#crend)|Возврат итератора const, указывающего на местоположение после завершающего элемента в обратном сопоставлении.|
|[emplace](#emplace)|Вставка в сопоставление элемента, созданного в качестве замены.|
|[emplace_hint](#emplace_hint)|Вставка в сопоставление элемента, созданного в качестве замены, с подсказкой о размещении.|
|[empty](#empty)|Возвращает **true** Если сопоставление является пустым.|
|[end](#end)|Возврат итератора после конца.|
|[equal_range](#equal_range)|Возвращает пару итераторов. Первый итератор в паре указывает на первый элемент в `map` с ключом, который больше указанного ключа. Второй итератор в паре указывает на первый элемент в `map` с ключом, который больше или равен данному ключу.|
|[erase](#erase)|Удаление элемента или диапазона элементов в сопоставлении с заданных позиций.|
|[find](#find)|Возврат итератора, указывающего на расположение элемента в сопоставлении с ключом, равным указанному ключу.|
|[get_allocator](#get_allocator)|Возврат копии объекта `allocator`, который используется для формирования сопоставления.|
|[insert](#insert)|Вставка элемента или диапазона элементов в сопоставление в заданной позиции.|
|[key_comp](#key_comp)|Возврат копии объекта сравнения, который используется для упорядочивания ключей в сопоставлении.|
|[lower_bound](#lower_bound)|Возврат итератора, указывающего на первый элемент в сопоставлении с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возврат максимальной длины сопоставления.|
|[rbegin](#rbegin)|Возврат итератора, указывающего на первый элемент в обратном сопоставлении.|
|[rend](#rend)|Возврат итератора, указывающего на местоположение после завершающего элемента в обратном сопоставлении.|
|[size](#size)|Возврат количества элементов в сопоставлении.|
|[swap](#swap)|Обмен элементами между двумя сопоставлениями.|
|[upper_bound](#upper_bound)|Возврат итератора, указывающего на первый элемент в сопоставлении со значением ключа, которое больше указанного ключа.|
|[value_comp](#value_comp)|Извлечение копии объекта сравнения, который используется для упорядочивания значений элементов в сопоставлении.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator&#91;&#93;](#op_at)|Вставка элемента в сопоставление с заданным значением ключа.|
|[оператор=](#op_eq)|Замена элементов сопоставления копией другого сопоставления.|

## <a name="requirements"></a>Требования

**Заголовок:** \<map>

**Пространство имен:** std

## <a name="allocator_type"></a>  map::allocator_type

Тип, представляющий класс распределителя для объекта-сопоставления.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Пример

См. пример для [get_allocator](#get_allocator) в качестве примера использования `allocator_type`.

## <a name="at"></a>  map::at

Поиск элемента с заданным значением ключа.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|Параметр|Описание|
|*key*|Значение ключа, которое необходимо найти.|

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного элемента.

### <a name="remarks"></a>Примечания

Если ключевое значение-аргумент не найдено, то функция выдает объект класса [класс out_of_range](../standard-library/out-of-range-class.md).

### <a name="example"></a>Пример

```cpp
// map_at.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

typedef std::map<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// find and show elements
    std::cout << "c1.at('a') == " << c1.at('a') << std::endl;
    std::cout << "c1.at('b') == " << c1.at('b') << std::endl;
    std::cout << "c1.at('c') == " << c1.at('c') << std::endl;

    return (0);
    }
```

## <a name="begin"></a>  map::begin

Возвращает итератор, адресующий первый элемент в сопоставлении.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий первый элемент в сопоставлении или положение после пустого сопоставления.

### <a name="example"></a>Пример

```cpp
// map_begin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: const_iterator m1_cIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 0, 0 ) );
   m1.insert ( Int_Pair ( 1, 1 ) );
   m1.insert ( Int_Pair ( 2, 4 ) );

   m1_cIter = m1.begin ( );
   cout << "The first element of m1 is " << m1_cIter -> first << endl;

   m1_Iter = m1.begin ( );
   m1.erase ( m1_Iter );

   // The following 2 lines would err because the iterator is const
   // m1_cIter = m1.begin ( );
   // m1.erase ( m1_cIter );

   m1_cIter = m1.begin( );
   cout << "The first element of m1 is now " << m1_cIter -> first << endl;
}
```

```Output
The first element of m1 is 0
The first element of m1 is now 1
```

## <a name="cbegin"></a>  map::cbegin

Возвращает **const** итератор, адресующий расположение после последнего элемента в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** Двунаправленный итератор, адресующий первый элемент диапазона или расположение прямо за концом пустой диапазона (для пустого диапазона `cbegin() == cend()`).

### <a name="remarks"></a>Примечания

Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличным от **const**) контейнер любого вида, который поддерживает `begin()` и `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  map::cend

Возвращает **const** итератор, адресующий расположение после последнего элемента в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** итератор двунаправленного доступа, который указывает конец диапазона.

### <a name="remarks"></a>Примечания

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличным от **const**) контейнер любого вида, который поддерживает `end()` и `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="clear"></a>  map::clear

Стирает все элементы в сопоставлении.

```cpp
void clear();
```

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена map::clear.

```cpp
// map_clear.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 4));

    i = m1.size();
    cout << "The size of the map is initially "
         << i << "." << endl;

    m1.clear();
    i = m1.size();
    cout << "The size of the map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the map is initially 2.
The size of the map after clearing is 0.
```

## <a name="const_iterator"></a>  map::const_iterator

Тип, предоставляющий двунаправленный итератор, который может читать элемент **const** сопоставления.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

`const_iterator`, определенный сопоставлением, указывает на элементы, которые являются объектами [value_type](#value_type) типа `pair`\< **constKey**, **Type**>, первый член которых — ключ элемента, а второй — сопоставленные данные, хранящиеся в элементе.

Для разыменования `const_iterator` `cIter` указывающего на элемент в сопоставлении, используйте `->` оператор.

Для получения доступа к значению ключа для элемента используйте `cIter` -> **first**, что эквивалентно (\* `cIter`). **first**.

Для получения доступа к значению сопоставленных данных элемента используйте `cIter` -> **second**, что эквивалентно (\* `cIter`). **second**.

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="const_pointer"></a>  map::const_pointer

Тип, предоставляющий указатель на элемент **const** в сопоставлении.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-сопоставлении следует использовать [итератор](#iterator).

## <a name="const_reference"></a>  map::const_reference

Тип, предоставляющий ссылку на элемент **const**, хранящийся в сопоставлении, для чтения и выполнения операций **const**.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Пример

```cpp
// map_const_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
```

## <a name="const_reverse_iterator"></a>  map::const_reverse_iterator

Тип, предоставляющий двунаправленный итератор, который может считать любой элемент **const** в сопоставлении.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора сопоставления в обратном порядке.

`const_reverse_iterator` Определяется сопоставлением, указывает на элементы, которые являются объектами [value_type](#value_type), то есть типа `pair<const Key, Type>`, первый член которых является ключом для элемента, а второй — сопоставленные данные, хранящиеся в элементе.

Для разыменования `const_reverse_iterator crIter` указывающего на элемент в сопоставлении, используйте `->` оператор.

Чтобы получить значение ключа для элемента, используйте `crIter`  ->  **первый**, что эквивалентно (\* `crIter`). **Первый**.

Для доступа к значению сопоставленных данных для элемента, используйте `crIter`  ->  **второй**, что эквивалентно (\* `crIter`). **Первый**.

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="count"></a>  map::count

Возвращает число элементов в объекте map, ключи которых соответствуют ключу, заданному параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа для сравнения с ключами элементов объекта map.

### <a name="return-value"></a>Возвращаемое значение

1, если объект map содержит элемент, ключ сортировки которого совпадает с ключом параметра. 0, если объект map не содержит ни одного элемента с соответствующим ключом.

### <a name="remarks"></a>Примечания

Функция-член возвращает количество элементов *x* в диапазоне

[`lower_bound` (_ *Key*), `upper_bound` (\_ *Key*))

— 0 или 1 для map, который является уникальным ассоциативным контейнером.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена map::count.

```cpp
// map_count.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 1));
    m1.insert(Int_Pair(1, 4));
    m1.insert(Int_Pair(2, 1));

    // Keys must be unique in map, so duplicates are ignored
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
The number of elements in m1 with a sort key of 1 is: 1.
The number of elements in m1 with a sort key of 2 is: 1.
The number of elements in m1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a>  map::crbegin

Возвращает константный итератор на первый элемент в обратной карте.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [сопоставлении](../standard-library/map-class.md) или адресующий то, что было последним элементом в `map` до замены его порядка на обратный.

### <a name="remarks"></a>Примечания

`crbegin` используется с обратным `map` так же, как [begin](#begin) используется с обычным `map`.

При возвращенном значении `crbegin` объект `map` изменить нельзя.

`crbegin` можно использовать для перебора `map` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// map_crbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
```

## <a name="crend"></a>  map::crend

Возвращает константный итератор, адресующий положение после последнего элемента в обратном сопоставлении.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном [сопоставлении](../standard-library/map-class.md) (положение, которое предшествовало первому элементу в `map` до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`crend` используется с обратным сопоставлением так же, как [end](#end) используется с обычным `map`.

Если возвращаемое значение `crend`, то объект `map` невозможно изменить.

`crend` используется, чтобы проверить, достиг ли итератор конца `map`.

Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// map_crend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crend( );
   m1_crIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
```

## <a name="difference_type"></a>  map::difference_type

Целочисленный тип со знаком, который можно использовать для представления количества элементов в сопоставлении в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне *[ first,  last)* между итераторами `first` и `last`, включая элемент, на который указывает `first`, и диапазон элементов до элемента, на который указывает `last`, но не включая его.

Обратите внимание, что хотя `difference_type` доступен для всех итераторов, соответствующих требованиям для итератора ввода, что включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, например наборами, вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, например векторами.

### <a name="example"></a>Пример

```cpp
// map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <map>
#include <algorithm>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );
   m1.insert ( Int_Pair ( 2, 30 ) );

   map <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;
   m1_bIter = m1.begin( );
   m1_eIter = m1.end( );

   // Count the number of elements in a map
   map <int, int>::difference_type  df_count = 1;
   m1_Iter = m1.begin( );
   while ( m1_Iter != m1_eIter)
   {
      df_count++;
      m1_Iter++;
   }

   cout << "The number of elements in the map m1 is: "
        << df_count << "." << endl;
}
```

```Output
The number of elements in the map m1 is: 4.
```

## <a name="emplace"></a>  map::emplace

Вставляет в сопоставление элемент, созданный на месте (без выполнения операций копирования или перемещения).

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|Параметр|Описание|
|*аргументы*|Аргументы, передаваемые для создания элемента для вставки в сопоставление, кроме случаев, когда сопоставление уже содержит элемент, значение которого правильным образом упорядочено.|

### <a name="return-value"></a>Возвращаемое значение

Объект [пары](../standard-library/pair-structure.md) которого **bool** компонент является значение true, если вставка была выполнена и значение false, если сопоставление уже содержало элемент эквивалентное значение порядка. Компонент итератора пары возвращаемых значений указывает на вставленный элемент, если **bool** компонент равно true, или на существующий элемент Если **bool** компонента имеет значение false.

Для доступа к компоненту-итератору `pair` `pr`, использовать `pr.first`; для его разыменования используйте `*pr.first`. Чтобы получить доступ к **bool** компонент, используйте `pr.second`. См. пример кода далее в этой статье.

### <a name="remarks"></a>Примечания

Эта функция не делает недействительными никакие итераторы или ссылки.

Если во время размещения создается исключение, состояние контейнера не изменяется.

[value_type](#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

### <a name="example"></a>Пример

```cpp
// map_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

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
    map<int, string> m1;

    auto ret = m1.emplace(10, "ten");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
        cout << "map not modified" << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;

    ret = m1.emplace(10, "one zero");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;
}

```

## <a name="emplace_hint"></a>  map::emplace_hint

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
|Параметр|Описание|
|*аргументы*|Аргументы, передаваемые для создания элемента, который будет вставлен в сопоставление, кроме ситуации, когда сопоставление уже содержит этот элемента или, в более общем случае, кроме ситуации, когда сопоставление уже содержит элемент, ключ которого правильно упорядочен.|
|*where*|Место начала поиска правильной точки вставки. (Если этой точки непосредственно предшествует *где*, вставка может происходить в амортизированном константном времени вместо логарифмического времени.)|

### <a name="return-value"></a>Возвращаемое значение

Итератор на вставленный элемент.

Если вставка не удалась, так как элемент уже существует, возвращается итератор, указывающий на существующий элемент с его ключом.

### <a name="remarks"></a>Примечания

Эта функция не делает недействительными никакие итераторы или ссылки.

Если во время размещения создается исключение, состояние контейнера не изменяется.

[value_type](#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

### <a name="example"></a>Пример

```cpp
// map_emplace.cpp
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
    map<string, string> m1;

    // Emplace some test data
    m1.emplace("Anna", "Accounting");
    m1.emplace("Bob", "Accounting");
    m1.emplace("Carmine", "Engineering");

    cout << "map starting data: ";
    print(m1);
    cout << endl;

    // Emplace with hint
    // m1.end() should be the "next" element after this emplacement
    m1.emplace_hint(m1.end(), "Doug", "Engineering");

    cout << "map modified, now contains ";
    print(m1);
    cout << endl;
}

```

## <a name="empty"></a>  map::empty

Проверяет, что сопоставление пустое.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если сопоставление пустое; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// map_empty.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2;

   typedef pair <int, int> Int_Pair;
   m1.insert ( Int_Pair ( 1, 1 ) );

   if ( m1.empty( ) )
      cout << "The map m1 is empty." << endl;
   else
      cout << "The map m1 is not empty." << endl;

   if ( m2.empty( ) )
      cout << "The map m2 is empty." << endl;
   else
      cout << "The map m2 is not empty." << endl;
}
```

```Output
The map m1 is not empty.
The map m2 is empty.
```

## <a name="end"></a>  map::end

Возврат итератора после конца.

```cpp
const_iterator end() const;


iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор после конца. Если карта пуста, то `map::end() == map::begin()`.

### <a name="remarks"></a>Примечания

`end` используется для проверки, прошел ли итератор конца своего сопоставления.

Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

Пример кода см. в [map::find](#find).

## <a name="equal_range"></a>  map::equal_range

Возвращает пару итераторов, представляющих [lower_bound](#lower_bound) ключа и [upper_bound](#upper_bound) ключа.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключевое значение для сравнения с ключом сортировки элемента из сопоставления, в котором ведется поиск.

### <a name="return-value"></a>Возвращаемое значение

Для доступа к первому итератору пары `pr`, возвращаемому функцией-членом, используйте `pr`. **first**, а для сброса ссылки на итератор нижней границы — \*( `pr`. **first**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **second**, а для сброса ссылки на итератор верхней границы — \*( `pr`. **second**).

### <a name="example"></a>Пример

```cpp
// map_equal_range.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef map <int, int, less<int> > IntMap;
   IntMap m1;
   map <int, int> :: const_iterator m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = m1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   m1_RcIter = m1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << m1_RcIter -> second << "," << endl
        << " matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = m1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )
      cout << "The map m1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of map m1 with a key >= 40 is: "
           << p2.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the map m1 is: 20.
The upper bound of the element with a key of 2 in the map m1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
 matching the 2nd element of the pair returned by equal_range( 2 ).
The map m1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a>  map::erase

Удаляет элемент или диапазон элементов из сопоставления из указанной позиции или удаляет элементы, которые соответствуют указанному ключу.

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

*Where*<br/>
Положение удаляемого элемента.

*Первый*<br/>
Положение первого удаляемого элемента.

*последний*<br/>
Положение перед последним удаляемым элементом.

*Key*<br/>
Значение ключа удаляемых элементов.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов это двунаправленный итератор, обозначающий первый элемент, остающийся после любых удаленных элементов, или элемент в конце сопоставления, если таких элементов нет.

Третья функция-член возвращает количество элементов, которые были удалены из сопоставления.

### <a name="example"></a>Пример

```cpp
// map_erase.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>
#include <iterator> // next() and prev() helper functions
#include <utility>  // make_pair()

using namespace std;

using mymap = map<int, string>;

void printmap(const mymap& m) {
    for (const auto& elem : m) {
        cout << " [" << elem.first << ", " << elem.second << "]";
    }
    cout << endl << "size() == " << m.size() << endl << endl;
}

int main()
{
    mymap m1;

    // Fill in some data to test with, one at a time
    m1.insert(make_pair(1, "A"));
    m1.insert(make_pair(2, "B"));
    m1.insert(make_pair(3, "C"));
    m1.insert(make_pair(4, "D"));
    m1.insert(make_pair(5, "E"));

    cout << "Starting data of map m1 is:" << endl;
    printmap(m1);
    // The 1st member function removes an element at a given position
    m1.erase(next(m1.begin()));
    cout << "After the 2nd element is deleted, the map m1 is:" << endl;
    printmap(m1);

    // Fill in some data to test with, one at a time, using an intializer list
    mymap m2
    {
        { 10, "Bob" },
        { 11, "Rob" },
        { 12, "Robert" },
        { 13, "Bert" },
        { 14, "Bobby" }
    };

    cout << "Starting data of map m2 is:" << endl;
    printmap(m2);
    // The 2nd member function removes elements
    // in the range [First, Last)
    m2.erase(next(m2.begin()), prev(m2.end()));
    cout << "After the middle elements are deleted, the map m2 is:" << endl;
    printmap(m2);

    mymap m3;

    // Fill in some data to test with, one at a time, using emplace
    m3.emplace(1, "red");
    m3.emplace(2, "yellow");
    m3.emplace(3, "blue");
    m3.emplace(4, "green");
    m3.emplace(5, "orange");
    m3.emplace(6, "purple");
    m3.emplace(7, "pink");

    cout << "Starting data of map m3 is:" << endl;
    printmap(m3);
    // The 3rd member function removes elements with a given Key
    mymap::size_type count = m3.erase(2);
    // The 3rd member function also returns the number of elements removed
    cout << "The number of elements removed from m3 is: " << count << "." << endl;
    cout << "After the element with a key of 2 is deleted, the map m3 is:" << endl;
    printmap(m3);
}

```

## <a name="find"></a>  map::find

Возвращает итератор, ссылающийся на элемент в карте, ключ которого эквивалентен заданному ключу.

```cpp
iterator find(const Key& key);


const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа, с которым сравнивается ключ сортировки элемента из карты, по которой выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор, ссылающийся на расположение элемента с указанным ключом или на расположение элемента после последнего элемента в карте (`map::end()`), если для ключа не найдено совпадений.

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор, который ссылается на элемент в карте с ключом сортировки, эквивалентным ключу аргумента согласно двоичному предикату, применяющему упорядочение на основе отношения сравнения «меньше».

Если возвращаемое значение `find` присвоено `const_iterator`, то объект сопоставления изменить нельзя. Если возвращаемое значение `find` назначается `iterator`, объект-сопоставление можно изменить.

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
    map<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });
    cout << "The starting map m1 is (key, value):" << endl;
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

    cout << "The modified map m1 is (key, value):" << endl;
    print_collection(m1);
    cout << endl;
    findit(m1, 45);
    findit(m1, 6);
}

```

## <a name="get_allocator"></a>  map::get_allocator

Возвращает копию объекта-распределителя, использованного для создания сопоставления.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый сопоставлением.

### <a name="remarks"></a>Примечания

Распределители для класса map определяют, как это класс управляет памятью. Распределители по умолчанию для классов контейнеров из стандартной библиотеки C++ достаточны для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// map_get_allocator.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int>::allocator_type m1_Alloc;
   map <int, int>::allocator_type m2_Alloc;
   map <int, double>::allocator_type m3_Alloc;
   map <int, int>::allocator_type m4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   map <int, int> m1;
   map <int, int, allocator<int> > m2;
   map <int, double, allocator<double> > m3;

   m1_Alloc = m1.get_allocator( );
   m2_Alloc = m2.get_allocator( );
   m3_Alloc = m3.get_allocator( );

   cout << "The number of integers that can be allocated\n"
        << "before free memory is exhausted: "
        << m2.max_size( ) << ".\n" << endl;

   cout << "The number of doubles that can be allocated\n"
        << "before free memory is exhausted: "
        << m3.max_size( ) <<  ".\n" << endl;

   // The following line creates a map m4
   // with the allocator of map m1.
   map <int, int> m4( less<int>( ), m1_Alloc );

   m4_Alloc = m4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( m1_Alloc == m4_Alloc )
   {
      cout << "The allocators are interchangeable." << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable." << endl;
   }
}
```

## <a name="insert"></a>  map::insert

Вставляет элемент или диапазон элементов в сопоставление.

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
|Параметр|Описание|
|*Val*|Значение элемента, вставляемого в сопоставление, если оно уже не содержит элемент, ключ которого эквивалентно упорядочен.|
|*Where*|Место начала поиска правильной точки вставки. (Если этой точки непосредственно предшествует *где*, вставка может происходить в амортизированном константном времени вместо логарифмического времени.)|
|*ValTy*|Параметр шаблона, определяющий тип аргумента, с карты можно использовать для создания элемента из [value_type](#value_type)и точно пересылает *Val* как аргумент.|
|*Первый*|Позиция первого элемента, который следует скопировать.|
|*последний*|Позиция непосредственно перед последним элементом, который следует скопировать.|
|*InputIterator*|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](#value_type).|
|*IList*|[initializer_list](../standard-library/initializer-list.md), из которого нужно скопировать элементы.|

### <a name="return-value"></a>Возвращаемое значение

Функции-члены одного элемента, (1) и (2) возвращают [пары](../standard-library/pair-structure.md) которого **bool** компонент является значение true, если вставка была выполнена и значение false, если сопоставление уже содержало элемент, ключ которого имел эквивалентное значение в этом упорядочении. Компонент итератора пары возвращаемых значений указывает на вставленный элемент, если **bool** компонент равно true, или на существующий элемент Если **bool** компонента имеет значение false.

Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, который указывает на позицию, где новый элемент был вставлен, или, если элемент с эквивалентным ключом уже существует, указывает на существующий элемент.

### <a name="remarks"></a>Примечания

Эта функция не делает никакие итераторы, указатели или ссылки недействительными.

Если во время вставки одного элемента вызывается исключение, состояние контейнера не изменяется. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

Для доступа к компоненту итератора `pair` `pr`, возвращаемого одноэлементными функциями-членами, используйте `pr.first`. Для разыменования итератора в возвращенной паре используйте `*pr.first`, чтобы получить элемент. Чтобы получить доступ к **bool** компонент, используйте `pr.second`. См. пример кода далее в этой статье.

[value_type](#value_type) контейнера — это определение типа, который принадлежит контейнеру. Для сопоставления `map<K, V>::value_type` — это `pair<const K, V>`. Значение элемента — это упорядоченная пара, в которой первый компонент эквивалентен значению ключа, а второй компонент — значению данных элемента.

Функция-член с диапазоном (5) вставляет последовательность значений элементов в сопоставление, соответствующее каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `m.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `m`. Вставляются только элементы с уникальными значениями в диапазоне. Повторяющиеся значения игнорируются. Чтобы увидеть, какие элементы отклонены, используйте одноэлементные версии `insert`.

Функция-член списка инициализатора (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в сопоставление.

Для вставки элемента, созданного на месте (то есть без операций копирования или перемещения) см. разделы [map::emplace](#emplace) и [map::emplace_hint](#emplace_hint).

### <a name="example"></a>Пример

```cpp
// map_insert.cpp
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
    map<int, int> m1;
    // call insert(const value_type&) version
    m1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    m1.insert(make_pair(2, 20));

    cout << "The original key and mapped values of m1 are:" << endl;
    print(m1);

    // intentionally attempt a duplicate, single element
    auto ret = m1.insert(make_pair(1, 111));
    if (!ret.second){
        auto pr = *ret.first;
        cout << "Insert failed, element with key value 1 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "The modified key and mapped values of m1 are:" << endl;
        print(m1);
    }
    cout << endl;

    // single element, with hint
    m1.insert(m1.end(), make_pair(3, 30));
    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);
    cout << endl;

    // The templatized version inserting a jumbled range
    map<int, int> m2;
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
    map<int, string>  m3;
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

    map<int, int> m4;
    // Insert the elements from an initializer_list
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });
    cout << "After initializer_list insertion, m4 contains:" << endl;
    print(m4);
    cout << endl;
}

```

## <a name="iterator"></a>  map::iterator

Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в сопоставлении.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Примечания

Итератор, определенный сопоставлением, указывает на элементы, которые являются объектами [value_type](#value_type), то есть типа `pair<const Key, Type>`, первый член которых является ключом для элемента, а второй — сопоставленные данные, хранящиеся в элементе.

Для разыменования итератора *Iter* указывающего на элемент в сопоставлении, используйте `->` оператор.

Чтобы получить значение ключа для элемента, используйте `Iter->first`, что эквивалентно `(*Iter).first`. Для доступа к значению сопоставленных данных для элемента, используйте `Iter->second`, что эквивалентно `(*Iter).second`.

### <a name="example"></a>Пример

См. пример для [начать](#begin) пример того, как объявить и использовать `iterator`.

## <a name="key_comp"></a>  map::key_comp

Извлекает копию объекта сравнения, использованного для упорядочивания ключей в сопоставлении.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую сопоставление использует для упорядочивания своих элементов.

### <a name="remarks"></a>Примечания

Хранимый объект определяет функцию-член

`bool operator(const Key& left, const Key& right);`

которая возвращает **true**, если `left` предшествует `right` в порядке сортировки и не равен ему.

### <a name="example"></a>Пример

```cpp
// map_key_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;
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

   map <int, int, greater<int> > m2;
   map <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );
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

## <a name="key_compare"></a>  map::key_compare

Тип, предоставляющий объект-функцию, которая может сравнить два ключа сортировки для определения относительного порядка двух элементов в сопоставлении.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Примечания

`key_compare` является синонимом для параметра-шаблона *Traits*.

Дополнительные сведения о *Traits* см. в разделе [класс map](../standard-library/map-class.md) раздела.

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="key_type"></a>  map::key_type

Тип, который описывает ключ сортировки, хранящийся в каждом элементе сопоставления.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

`key_type` является синонимом для параметра-шаблона *ключ*.

Дополнительные сведения о *ключ*, см. в разделе "Примечания" [класс map](../standard-library/map-class.md) раздела.

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="lower_bound"></a>  map::lower_bound

Возвращает итератор, указывающий на первый элемент в сопоставлении с ключом, значение которого больше указанного ключа или равно ему.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключевое значение для сравнения с ключом сортировки элемента из сопоставления, в котором ведется поиск.

### <a name="return-value"></a>Возвращаемое значение

`iterator` Или `const_iterator` , расположение элемента в сопоставлении с ключом, равным или больше, чем ключ аргумента, или адресует положение после последнего элемента в сопоставлении, если соответствие найдено для ключа.

Если возвращаемое значение `lower_bound` присвоено `const_iterator`, то объект сопоставления изменить нельзя. Если возвращаемое значение `lower_bound` назначается `iterator`, объект-сопоставление можно изменить.

### <a name="example"></a>Пример

```cpp
// map_lower_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.lower_bound( 2 );
   cout << "The first element of map m1 with a key of 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for this key, end( ) is returned
   m1_RcIter = m1. lower_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of map m1 with a key of 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.end( );
   m1_AcIter--;
   m1_RcIter = m1. lower_bound ( m1_AcIter -> first );
   cout << "The element of m1 with a key matching "
        << "that of the last element is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key of 2 is: 20.
The map m1 doesn't have an element with a key of 4.
The element of m1 with a key matching that of the last element is: 30.
```

## <a name="map"></a>  map::map

Создает сопоставление, которое является пустым или копией части или целого другого сопоставления.

```cpp
map();

explicit map(
    const Traits& Comp);

map(
    const Traits& Comp,
    const Allocator& Al);

map(
    const map& Right);

map(
    map&& Right);

map(
    initializer_list<value_type> IList);

map(
    initializer_list<value_type> IList,
    const Traits& Comp);

map(
    initializer_list<value_type> IList,
    const Traits& Comp,
    const Allocator& Allocator);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|Параметр|Описание|
|*Al*|Класс распределителя памяти, который будет использоваться для этого объекта-сопоставления. Значение по умолчанию — `Allocator`.|
|*Зап.*|Функция сравнения типа `const Traits` для использования при упорядочивании элементов в сопоставлении. Значение по умолчанию — `hash_compare`.|
|*Справа*|Сопоставление, копией которого будет создаваемое сопоставление.|
|*Первый*|Положение первого элемента в диапазоне копируемых элементов.|
|*последний*|Положение первого элемента после диапазона копируемых элементов.|
|*IList*|Объект initializer_list, из которого будут скопированы элементы.|

### <a name="remarks"></a>Примечания

Все конструкторы сохраняют тип объекта-распределителя, управляющего памятью для сопоставления. Затем его можно получить путем вызова [get_allocator](#get_allocator). Параметр распределителя часто опускается в объявлениях классов и макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы инициализируют свои сопоставления.

Все конструкторы хранят объект-функцию типа Traits, которая используется для упорядочивания ключей сопоставления. Затем функцию можно получить путем вызова [key_comp](#key_comp).

Первые три конструктора указывают пустое начальное сопоставление, второй указывает тип функции сравнения (*Comp*) для использования при установлении порядка элементов, а третий явно указывает тип распределителя ( *Al*) для использования. Ключевое слово **явные** подавляет некоторые виды автоматического преобразования типов.

Четвертый конструктор указывает копию сопоставления *справа*.

Пятый конструктор указывает копию сопоставления путем перемещения *справа*.

Шестой, седьмой и восьмой конструкторы указывают initializer_list, из которого будут копироваться элементы.

Следующие три конструктора копируют диапазон `[First, Last)` сопоставления с повышением точности при указании типа функции сравнения класса `Traits` и распределителя.

### <a name="example"></a>Пример

```cpp
// map_map.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    typedef pair <int, int> Int_Pair;
    map <int, int>::iterator m1_Iter, m3_Iter, m4_Iter, m5_Iter, m6_Iter, m7_Iter;
    map <int, int, less<int> >::iterator m2_Iter;

    // Create an empty map m0 of key type integer
    map <int, int> m0;

    // Create an empty map m1 with the key comparison
    // function of less than, then insert 4 elements
    map <int, int, less<int> > m1;
    m1.insert(Int_Pair(1, 10));
    m1.insert(Int_Pair(2, 20));
    m1.insert(Int_Pair(3, 30));
    m1.insert(Int_Pair(4, 40));

    // Create an empty map m2 with the key comparison
    // function of geater than, then insert 2 elements
    map <int, int, less<int> > m2;
    m2.insert(Int_Pair(1, 10));
    m2.insert(Int_Pair(2, 20));

    // Create a map m3 with the
    // allocator of map m1
    map <int, int>::allocator_type m1_Alloc;
    m1_Alloc = m1.get_allocator();
    map <int, int> m3(less<int>(), m1_Alloc);
    m3.insert(Int_Pair(3, 30));

    // Create a copy, map m4, of map m1
    map <int, int> m4(m1);

    // Create a map m5 by copying the range m1[ first,  last)
    map <int, int>::const_iterator m1_bcIter, m1_ecIter;
    m1_bcIter = m1.begin();
    m1_ecIter = m1.begin();
    m1_ecIter++;
    m1_ecIter++;
    map <int, int> m5(m1_bcIter, m1_ecIter);

    // Create a map m6 by copying the range m4[ first,  last)
    // and with the allocator of map m2
    map <int, int>::allocator_type m2_Alloc;
    m2_Alloc = m2.get_allocator();
    map <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);

    cout << "m1 =";
    for (auto i : m1)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m2 =";
    for(auto i : m2)
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

    // Create a map m7 by moving m5
    cout << "m7 =";
    map<int, int> m7(move(m5));
    for (auto i : m7)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m8 by copying in an initializer_list
    map<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };
    cout << "m8: = ";
    for (auto i : m8)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m9 with an initializer_list and a comparator
    map<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());
    cout << "m9: = ";
    for (auto i : m9)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m10 with an initializer_list, a comparator, and an allocator
    map<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());
    cout << "m10: = ";
    for (auto i : m10)
        cout << i.first << " " << i.second << ", ";
    cout << endl;
}

```

## <a name="mapped_type"></a>  map::mapped_type

Тип, который представляет данные, хранящиеся в сопоставлении.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Примечания

Тип `mapped_type` является синонимом класса *тип* параметр шаблона.

Дополнительные сведения о *тип* см. в разделе [класс map](../standard-library/map-class.md) раздела.

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `mapped_type`.

## <a name="max_size"></a>  map::max_size

Возврат максимальной длины сопоставления.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина сопоставления.

### <a name="example"></a>Пример

```cpp
// map_max_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: size_type i;

   i = m1.max_size( );
   cout << "The maximum possible length "
        << "of the map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="op_at"></a>  map::operator[]

Вставка элемента в сопоставление с заданным значением ключа.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|Параметр|Описание|
|*key*|Ключевое значение элемента для вставки.|

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных вставленного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, он вставляется вместе со значением по умолчанию для такого типа данных.

`operator[]` может использоваться для вставки элементов в сопоставление `m` с помощью `m[ key] = DataValue;` где `DataValue` значение `mapped_type` элемента со значением ключа *ключ*.

При использовании `operator[]` для вставки элементов возвращаемая ссылка не отображает, меняет ли вставка уже существующий элемент или создает новый. Функции-члены [find](#find) и [insert](#insert) можно использовать для определения перед вставкой того, существует ли уже элемент с указанным ключом.

### <a name="example"></a>Пример

```cpp
// map_op_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a map using the operator[] member function
   m1[ 1 ] = 10;

   // Compare other ways to insert objects into a map
   m1.insert ( map <int, int> :: value_type ( 2, 20 ) );
   m1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   m1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   m1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

// insert by moving key
    map<string, int> c2;
    string str("abc");
    cout << "c2[move(str)] == " << c2[move(str)] << endl;
    cout << "c2["abc"] == " << c2["abc"] << endl;

    return (0);
}
```

```Output
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
The keys of the mapped elements are now: 1 2 3 5.
The values of the mapped elements are now: 10 40 30 0.
c2[move(str)] == 0
c2["abc"] == 1
```

## <a name="op_eq"></a>  map::operator=

Замена элементов сопоставления копией другого сопоставления.

```cpp
map& operator=(const map& right);

map& operator=(map&& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|Параметр|Описание|
|*right*|[Сопоставление](../standard-library/map-class.md), копируемое в `map`.|

### <a name="remarks"></a>Примечания

После удаления всех существующих элементов в `map`, `operator=` копирует или перемещает содержимое *правой* в сопоставление.

### <a name="example"></a>Пример

```cpp
// map_operator_as.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
   {
   using namespace std;
   map<int, int> v1, v2, v3;
   map<int, int>::iterator iter;

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

## <a name="pointer"></a>  map::pointer

Тип, предоставляющий указатель на элемент в сопоставлении.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` может использоваться для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-сопоставлении следует использовать [итератор](#iterator).

## <a name="rbegin"></a>  map::rbegin

Возвращает итератор, адресующий первый элемент в обратном сопоставлении.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном сопоставлении или адресующий элемент, который был последним элементов в сопоставлении до изменения его порядка на противоположный.

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным сопоставлением так же, как [begin](#begin) используется с обычным сопоставлением.

Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект-сопоставление изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект-сопоставление можно изменить.

`rbegin` можно использовать для перебора сопоставления в обратном порядке.

### <a name="example"></a>Пример

```cpp
// map_rbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = m1.rbegin( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the first element in the reversed map is 2.
```

## <a name="reference"></a>  map::reference

Тип, предоставляющий ссылку на элемент, хранящийся в сопоставлении.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Пример

```cpp
// map_reference.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;

   //The non-const_reference can be used to modify the
   //data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
The modified data value of first element is 15.
```

## <a name="rend"></a>  map::rend

Возвращает итератор, адресующий положение после последнего элемента в обратном сопоставлении.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном сопоставлении (положение, которое предшествовало первому элементу в сопоставлении до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`rend` используется с обратным сопоставлением так же, как [end](#end) используется с обычным сопоставлением.

Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект-сопоставление изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект-сопоставление можно изменить.

`rend` можно использовать для проверки, достиг ли итератор конца своего сопоставления.

Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// map_rend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = --m1.rend( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the last element in the reversed map is 2.
```

## <a name="reverse_iterator"></a>  map::reverse_iterator

Тип, предоставляющий двунаправленный итератор, который может читать или изменять элементы в обратном сопоставлении.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` не может изменять значение элемента и используется для перебора сопоставления в обратном порядке.

`reverse_iterator` Определяется сопоставлением, указывает на элементы, которые являются объектами [value_type](#value_type), то есть типа `pair<const Key, Type>`, первый член которых является ключом для элемента, а второй — сопоставленные данные, хранящиеся в элементе.

Для разыменования `reverse_iterator` *rIter* указывающего на элемент в сопоставлении, используйте `->` оператор.

Для получения доступа к значению ключа для элемента используйте `rIter` -> **first**, что эквивалентно (\* `rIter`). **first**. Для получения доступа к значению сопоставленных данных элемента используйте `rIter` -> **second**, что эквивалентно (\* `rIter`). **first**.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="size"></a>  map::size

Возврат количества элементов в сопоставлении.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина сопоставления.

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена map::size.

```cpp
// map_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1, m2;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    i = m1.size();
    cout << "The map length is " << i << "." << endl;

    m1.insert(Int_Pair(2, 4));
    i = m1.size();
    cout << "The map length is now " << i << "." << endl;
}
```

```Output
The map length is 1.
The map length is now 2.
```

## <a name="size_type"></a>  map::size_type

Беззнаковый целочисленный тип, который может представлять количество элементов в сопоставлении.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`.

## <a name="swap"></a>  map::swap

Обмен элементами между двумя сопоставлениями.

```cpp
void swap(
    map<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Сопоставление-аргумент предоставляет элементы для обмена с целевым сопоставлением.

### <a name="remarks"></a>Примечания

Функция-член не делает недействительными никакие ссылки, указатели или итераторы, обозначающие элементы в двух сопоставлениях, между которыми выполняется обмен элементами.

### <a name="example"></a>Пример

```cpp
// map_swap.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   map <int, int>::iterator m1_Iter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m2.insert ( Int_Pair ( 10, 100 ) );
   m2.insert ( Int_Pair ( 20, 200 ) );
   m3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   //m2 is said to be the argument map; m1 the target map
   m1.swap( m2 );

   cout << "After swapping with m2, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( m1, m3 );

   cout << "After swapping with m3, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original map m1 is: 10 20 30.
After swapping with m2, map m1 is: 100 200.
After swapping with m3, map m1 is: 300.
```

## <a name="upper_bound"></a>  map::upper_bound

Возвращает итератор, указывающий на первый элемент в сопоставлении с ключом, значение которого равно указанному ключу или больше его.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Аргумент-значение ключа для сравнения с значением ключа сортировки элемента сопоставления, в котором проводится поиск.

### <a name="return-value"></a>Возвращаемое значение

`iterator` Или `const_iterator` , расположение элемента в сопоставлении с ключом больше ключа-аргумента, или адресует положение после последнего элемента в сопоставлении, если соответствие найдено для ключа.

Если возвращенное значение назначается `const_iterator`, объект-сопоставление изменить нельзя. Если возвращаемое значение присваивается `iterator`, объект-сопоставление можно изменить.

### <a name="example"></a>Пример

```cpp
// map_upper_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.upper_bound( 2 );
   cout << "The first element of map m1 with a key "
        << "greater than 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   m1_RcIter = m1. upper_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of map m1 with a key > 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.begin( );
   m1_RcIter = m1. upper_bound ( m1_AcIter -> first );
   cout << "The 1st element of m1 with a key greater than\n"
        << "that of the initial element of m1 is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key greater than 2 is: 30.
The map m1 doesn't have an element with a key greater than 4.
The 1st element of m1 with a key greater than
that of the initial element of m1 is: 20.
```

## <a name="value_comp"></a>  map::value_comp

Функция-член возвращает объект-функцию, которая определяет порядок элементов в сопоставлении путем сравнения значений их ключей.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию сравнения, которую сопоставление использует для упорядочивания своих элементов.

### <a name="remarks"></a>Примечания

Для сопоставления *m*, если два элемента — *e*1( *k*1, *d*1) и *e*2( *k*2, `d`2) являются объектами типа `value_type`, где *k*1 и *k*2 — это их ключи типа `key_type`, а `d`1 и `d`2 — их данные типа `mapped_type`, то *m.*`value_comp`( *e*1, *e*2) эквивалентно *m.*`key_comp`*(k*1, *k*2). Сохраненный объект определяет функцию-член

**bool-оператор**( **value_type &**`left`, **value_type &**`right`);

которая возвращает **true**, если значение ключа `left` предшествует значению ключа `right` в порядке сортировки и не равно ему.

### <a name="example"></a>Пример

```cpp
// map_value_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::value_compare vc1 = m1.value_comp( );
   pair< map<int,int>::iterator, bool > pr1, pr2;

   pr1= m1.insert ( map <int, int> :: value_type ( 1, 10 ) );
   pr2= m1.insert ( map <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *pr1.first, *pr2.first ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."
           << endl;
   }

   if(vc1( *pr2.first, *pr1.first ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."
           << endl;
   }
}
```

```Output
The element ( 1,10 ) precedes the element ( 2,5 ).
The element ( 2,5 ) does not precede the element ( 1,10 ).
```

## <a name="value_type"></a>  map::value_type

Тип объекта, хранящегося в качестве элемента в сопоставлении.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="example"></a>Пример

```cpp
// map_value_type.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: key_type key1;
   map <int, int> :: mapped_type mapped1;
   map <int, int> :: value_type value1;
   map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   m1.insert ( map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a map
   m1.insert ( cInt2Int ( 2, 20 ) );
   m1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( m1.begin( ) -> first );
   mapped1 = ( m1.begin( ) -> second );

   cout << "The key of first element in the map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the map is "
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

## <a name="see-also"></a>См. также

[Контейнеры](../cpp/containers-modern-cpp.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
