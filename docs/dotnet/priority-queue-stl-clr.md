---
title: priority_queue (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd6d7ec3c4314f1a1798da3d5078b0409d44d026
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423914"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)

Класс шаблона описывает объект, управляющий переменной длины упорядоченную последовательность элементов, который имеет ограниченный доступ. Использование адаптера контейнера `priority_queue` для управления базового контейнера, как очереди с приоритетом.

В следующем описании `GValue` совпадает со значением *значение* последний ссылочного типа, в противном случае он является `Value^`. Аналогичным образом `GContainer` совпадает со значением *контейнера* последний ссылочного типа, в противном случае он является `Container^`.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    ref class priority_queue
        System::ICloneable,
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Тип элемента в управляемой последовательности.

*Контейнер*<br/>
Тип базового контейнера.

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext или очереди >

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[priority_queue::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[priority_queue::container_type (STL/CLR)](#container_type)|Тип базового контейнера.|
|[priority_queue::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[priority_queue::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для адаптера контейнера.|
|[priority_queue::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для адаптера контейнера.|
|[priority_queue::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[priority_queue::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|
|[priority_queue::value_compare (STL/CLR)](#value_compare)|Делегат упорядочения для двух элементов.|
|[priority_queue::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[priority_queue::assign (STL/CLR)](#assign)|Заменяет все элементы.|
|[priority_queue::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[priority_queue::get_container (STL/CLR)](#get_container)|Обращается к базового контейнера.|
|[priority_queue::pop (STL/CLR)](#pop)|Удаляет элемент hghest приоритетом.|
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|Создает объект контейнера.|
|[priority_queue::push (STL/CLR)](#push)|Добавляет новый элемент.|
|[priority_queue::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[priority_queue::top (STL/CLR)](#top)|Обращается к элементу с наивысшим приоритетом.|
|[priority_queue::to_array (STL/CLR)](#to_array)|Копирует управляемой последовательности в новый массив.|
|[priority_queue::value_comp (STL/CLR)](#value_comp)|Копирует делегат упорядочения для двух элементов.|

|Свойство.|Описание|
|--------------|-----------------|
|[priority_queue::top_item (STL/CLR)](#top_item)|Обращается к элементу с наивысшим приоритетом.|

|Оператор|Описание|
|--------------|-----------------|
|[priority_queue::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|

## <a name="interfaces"></a>интерфейсов,

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Создание дубликата объекта.|
|IPriorityQueue\<значение, контейнер >|Ведение адаптера универсального контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для управляемой последовательности с его помощью базового контейнера, типа `Container`, хранящий `Value` элементов и увеличивается по требованию. Она хранит последовательность, упорядоченную как куча, в элементе с наивысшим приоритетом (верхний элемент) легко доступной и съемных. Объект ограничивает доступ к новые элементы перемещая и выталкивая просто элемент с наивысшим приоритетом, реализация очереди с приоритетом.

Объект Упорядочивает управляемую им последовательность путем вызова объекта хранимых делегат типа [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Объект хранимой делегата можно указать при создании priority_queue; Если указать объект делегата, значение по умолчанию является сравнение `operator<(value_type, value_type)`. Доступ к этот сохраненный объект, вызвав функцию-член [priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.

Такой объект делегата должна налагать строгое слабое упорядочение к значениям типа [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:

`value_comp()(X, Y)` Возвращает результат же логическое значение при каждом вызове.

Если `value_comp()(X, Y)` имеет значение true, затем `value_comp()(Y, X)` должно иметь значение false.

Если `value_comp()(X, Y)` имеет значение true, затем `X` говорят, что допускается упорядочение перед `Y`.

Если `!value_comp()(X, Y) && !value_comp()(Y, X)` имеет значение true, затем `X` и `Y` называются имеют эквивалентное упорядочение.

Для любого элемента `X` , предшествующий `Y` в управляемой последовательности, `key_comp()(Y, X)` имеет значение false. (Для объекта делегата по умолчанию, ключи никогда не уменьшаются.)

Таким образом элемент наивысшего приоритета является одним из элементов, которые не упорядочен перед любым другим элементом.

Так как базового контейнера хранятся элементы, упорядоченные в виде кучи:

Контейнер должен поддерживать итераторов произвольного доступа.

Элементы с эквивалентным упорядочением могут извлекаться в другом порядке, чем они были отправлены. (Порядок нестабилен.)

Таким образом, для базового контейнера могут использоваться [deque (STL/CLR)](../dotnet/deque-stl-clr.md) и [вектор (STL/CLR)](../dotnet/vector-stl-clr.md).

## <a name="members"></a>Участники

## <a name="assign"></a> priority_queue::Assign (STL/CLR)

Заменяет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void assign(priority_queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Адаптер контейнера, для вставки.

### <a name="remarks"></a>Примечания

Функция-член назначает `right.get_container()` для базового контейнера. Используется, чтобы изменить все содержимое очереди.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign a repetition of values
    Mypriority_queue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="const_reference"></a> priority_queue::const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает постоянную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mypriority_queue::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="container_type"></a> priority_queue::container_type (STL/CLR)

Тип базового контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Container`.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c" using container_type
    Mypriority_queue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="difference_type"></a> priority_queue::difference_type (STL/CLR)

Типы со знаком расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает число возможно отрицательное элемент.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute negative difference
    Mypriority_queue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

    // compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
c a b
pushing 2 = -2
popping 3 = 3
```

## <a name="empty"></a> priority_queue::Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)`() == 0`. Можно использовать для тестирования ли очередь пуста.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
c a b
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="generic_container"></a> priority_queue::generic_container (STL/CLR)

Тип универсального интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>
    generic_container;
```

### <a name="remarks"></a>Примечания

Этот тип описывает универсальный интерфейс для этого класс адаптера контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
d c b a
e d b a c
```

## <a name="generic_value"></a> priority_queue::generic_value (STL/CLR)

Тип элемента для использования с универсальный интерфейс для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для этого класса контейнера шаблона. (`GValue` либо `value_type` или `value_type^` Если `value_type` является типом ссылки.)

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get interface to container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display in priority order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mypriority_queue::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
c b a
```

## <a name="get_container"></a> priority_queue::get_container (STL/CLR)

Обращается к базового контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
container_type get_container();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает базового контейнера. Используется для обхода ограничений, налагаемых оболочкой контейнера.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="op_as"></a> priority_queue::operator = (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*right*<br/>
Адаптер контейнера, для копирования.

### <a name="remarks"></a>Примечания

Копирует оператор член *правой* объекту, затем возвращает `*this`. Оно позволяет заменить управляемую последовательность копией управляемой последовательности в *правой*.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mypriority_queue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="pop"></a> priority_queue::POP (STL/CLR)

Удаляет элемент наивысший proirity.

### <a name="syntax"></a>Синтаксис

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

Функция-член удаляет элемент с наивысшим приоритетом управляемой последовательности, который должен быть пустым. Используется для сокращения очереди на один элемент в серверной части.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
b a
```

## <a name="priority_queue"></a> priority_queue::priority_queue (STL/CLR)

Создает объект адаптера контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
priority_queue();
priority_queue(priority_queue<Value, Container> right);
priority_queue(priority_queue<Value, Container> right);
explicit priority_queue(value_compare^ pred);
priority_queue(value_compare^ pred, container_type% cont);
template<typename InIt>
    priority_queue(InIt first, InIt last);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred, container_type% cont);
```

#### <a name="parameters"></a>Параметры

*Продолжение*<br/>
Контейнер для копирования.

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

`priority_queue();`

Создает пустой контейнер оболочку, с помощью упорядочения предикат по умолчанию. Используется для указания пустой начальной управляемой последовательности, со значением по умолчанию, упорядочение предикат.

Конструктор:

`priority_queue(priority_queue<Value, Container>% right);`

Создает оболочку контейнер, который является копией `right.get_container()`, с помощью предикат упорядочения `right.value_comp()`. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта очереди *правой*, с тем же предикат упорядочения.

Конструктор:

`priority_queue(priority_queue<Value, Container>^ right);`

Создает оболочку контейнер, который является копией `right->get_container()`, с помощью предикат упорядочения `right->value_comp()`. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта очереди `*right`, с тем же предикат упорядочения.

Конструктор:

`explicit priority_queue(value_compare^ pred);`

Создает пустой контейнер оболочку, с предикат упорядочения *pred*. Используется для указания пустой начальной управляемой последовательности, указанный предикат упорядочения.

Конструктор:

`priority_queue(value_compare^ pred, container_type cont);`

Создает пустой контейнер оболочку, с предикат упорядочения *pred*, помещает все элементы *cont* используется для указания начальной управляемой последовательности из существующего контейнера, с указанный предикат упорядочения.

Конструктор:

`template<typename InIt> priority_queue(InIt first, InIt last);`

Создает пустой контейнер оболочку, с помощью предикат упорядочения по умолчанию, а затем помещает последовательность [`first`, `last`). Используется для указания начальной управляемой последовательности из указанного eqeuence, с указанным предикатом упорядочивания.

Конструктор:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`

Создает пустой контейнер оболочку, с предикат упорядочения *pred*, помещает последовательность [`first`, `last`). Используется для указания начальной управляемой последовательности из указанного seqeuence, с указанным предикатом упорядочивания.

Конструктор:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`

Создает пустой контейнер оболочку, с предикат упорядочения *pred*, помещает все элементы *cont* плюс последовательность [`first`, `last`). Используется для указания начальной управляемой последовательности из существующего контейнера и указанного seqeuence, с указанным предикатом упорядочивания.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/deque>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
typedef cliext::deque<wchar_t> Mydeque;
int main()
    {
// construct an empty container
    Mypriority_queue c1;
    Mypriority_queue::container_type^ wc1 = c1.get_container();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    for each (wchar_t elem in wc1)
        c2.push(elem);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule by copying an underlying container
    Mypriority_queue c2x =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
   for each (wchar_t elem in c2x.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mypriority_queue c3(wc1->begin(), wc1->end());
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mypriority_queue c4(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>());
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range, another container, and an ordering rule
    Mypriority_queue c5(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c5.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mypriority_queue c6(c3);
    for each (wchar_t elem in c6.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mypriority_queue c7(%c3);
    for each (wchar_t elem in c7.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule, by copying an underlying container
    Mypriority_queue c8 =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c8.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
c a b
size() = 0
a c b
a c b
c a b
a c b
a a b c c b
c a b
c a b
a c b
```

## <a name="push"></a> priority_queue::Push (STL/CLR)

Добавляет новый элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Примечания

Функция-член вставляет элемент со значением `val` в управляемой последовательности и упорядочивает управляемую последовательность для сохранения дисциплины кучи. Используется для добавления другого элемента в очередь.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="reference"></a> priority_queue::Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Этот тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify top of priority_queue and redisplay
    Mypriority_queue::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
x a b
```

## <a name="size"></a> priority_queue::size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Используется для определения числа элементов в данный момент в управляемой последовательности. Если вас интересуют ли последовательность имеет ненулевой размер, см. в разделе [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

    // add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
c a b
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="size_type"></a> priority_queue::size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает элемент неотрицательное число.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mypriority_queue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
c a b
size difference = 2
```

## <a name="to_array"></a> priority_queue::to_array (STL/CLR)

Копирует управляемой последовательности в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает массив, содержащий управляемой последовательности. Вы можете использовать его для получения копии управляемой последовательности в форме массива.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
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
d c b a
c a b
```

## <a name="top"></a> priority_queue::Top (STL/CLR)

Обращается к элементу с наивысшим приоритетом.

### <a name="syntax"></a>Синтаксис

```cpp
reference top();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на элемент управляемой последовательности, который должен быть пустым сверху (с наивысшим приоритетом). Он понадобится на доступ к элементу с наивысшим приоритетом, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_top.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top() = {0}", c1.top());

    // alter last item and reinspect
    c1.top() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

## <a name="top_item"></a> priority_queue::top_item (STL/CLR)

Обращается к элементу с наивысшим приоритетом.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Примечания

Свойство обращается к верхней (с наивысшим приоритетом) элемент управляемой последовательности, который должен быть пустым. Используется для чтения или записи элемента с наивысшим приоритетом, в том случае, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_top_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top_item = {0}", c1.top_item);

    // alter last item and reinspect
    c1.top_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
top_item = c
x a b
```

## <a name="value_comp"></a> priority_queue::value_comp (STL/CLR)

Копирует делегат упорядочения для двух элементов.

### <a name="syntax"></a>Синтаксис

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Используется для сравнения двух значений.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_value_comp.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="value_compare"></a> priority_queue::value_compare (STL/CLR)

Делегат упорядочения для двух значений.

### <a name="syntax"></a>Синтаксис

```cpp
binary_delegate<value_type, value_type, int> value_compare;
```

### <a name="remarks"></a>Примечания

Тип является синонимом делегат, который определяет, упорядочена ли первый аргумент, чтобы второй.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_value_compare.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="value_type"></a> priority_queue::value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона *значение*.

### <a name="example"></a>Пример

```cpp
// cliext_priority_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mypriority_queue::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```