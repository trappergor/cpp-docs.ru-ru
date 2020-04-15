---
title: utility (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: 6d025230abcff42e367a231e616a13f0f8c684f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320297"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

Включите заголовок `<cliext/utility>` STL/CLR для `pair` определения класса шаблонов и нескольких вспомогательных функций шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
#include <utility>
```

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/полезность>

**Название:** cliext

## <a name="declarations"></a>Объявления

|Class|Описание|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Оберните пару элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Парное равное сравнение.|
|[оператор! (пара) (STL/CLR)](#op_neq)|Пара не равное сравнение.|
|[оператор< (пара) (STL/CLR)](#op_lt)|Пара меньше, чем сравнение.|
|[оператор\<(пара) (STL/CLR)](#op_lteq)|Пара меньше или равное сравнение.|
|[оператор> (пара) (STL/CLR)](#op_gt)|Пара больше, чем сравнение.|
|[оператор>(пара) (STL/CLR)](#op_gteq)|Пара больше или равного сравнения.|

|Компонент|Описание|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Сделайте пару из пары значений.|

## <a name="members"></a>Участники

## <a name="pair-stlclr"></a><a name="pair"></a>пара (STL/CLR)

Класс шаблона описывает объект, который обертывает пару значений.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Параметры

*Значение1*<br/>
Тип первого обернутого значения.

*Значение2*<br/>
Тип второго обернутого значения.

## <a name="members"></a>Участники

|Определение типа|Описание|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|Тип первого обернутого значения.|
|[pair::second_type (STL/CLR)](#second_type)|Тип второго обернутого значения.|

|Объект участника|Описание|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|Первое сохраненное значение.|
|[pair::second (STL/CLR)](#second)|Второе сохраненное значение.|

|Функция-член|Описание|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Строит объект пары.|
|[pair::swap (STL/CLR)](#swap)|Свопирует содержимое двух пар.|

|Оператор|Описание|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Заменяет сохраненную пару значений.|

## <a name="remarks"></a>Remarks

Объект хранит пару значений. Этот класс шаблонов объединяет два значения в один объект. Кроме того, `cliext::pair` объект (описанный здесь) хранит только управляемые типы; для хранения пары неуправляемых `std::pair`типов `<utility>`использования, объявлено в .

## <a name="pairfirst-stlclr"></a><a name="first"></a>пара::первый (STL/CLR)

Первое обернутое значение.

### <a name="syntax"></a>Синтаксис

```cpp
Value1 first;
```

### <a name="remarks"></a>Remarks

Объект хранит первое обернутое значение.

### <a name="example"></a>Пример

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>пара::first_type (STL/CLR)

Тип первого обернутого значения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом параметра *шаблона Value1.*

### <a name="example"></a>Пример

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>пара::оператор ( STL/CLR)

Заменяет сохраненную пару значений.

### <a name="syntax"></a>Синтаксис

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Пара для копирования.

### <a name="remarks"></a>Remarks

Оператор-член копирует *право* на объект, а затем возвращается. `*this` Вы используете его, чтобы заменить сохраненные пары значений с копией сохраненной пары значений в *правой.*

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>пара::pair (STL/CLR)

Строит объект пары.

### <a name="syntax"></a>Синтаксис

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Пара для хранения.

*val1*<br/>
Первое значение для хранения.

*val2*<br/>
Второе значение для хранения.

### <a name="remarks"></a>Remarks

Конструктор:

`pair();`

инициализирует сохраненную пару с значениями, построенными по умолчанию.

Конструктор:

`pair(pair<Value1, Value2>% right);`

инициализирует хранит хранимые пары `right.`с [парой::первый (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right.` [пара::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

инициализирует хранит хранимые пары `right->`с [парой::первый (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right>` [пара::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Конструктор:

`pair(Value1 val1, Value2 val2);`

инициализирует хранящуюся пару с *val1* и *val2*.

### <a name="example"></a>Пример

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="pairsecond-stlclr"></a><a name="second"></a>пара::второй (STL/CLR)

Второе обернутое значение.

### <a name="syntax"></a>Синтаксис

```cpp
Value2 second;
```

### <a name="remarks"></a>Remarks

Объект хранит второе обернутое значение.

### <a name="example"></a>Пример

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>пара::second_type (STL/CLR)

Тип второго обернутого значения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом параметра *шаблона Value2.*

### <a name="example"></a>Пример

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairswap-stlclr"></a><a name="swap"></a>пара::swap (STL/CLR)

Свопирует содержимое двух пар.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Пара для обмена содержимого с.

### <a name="remarks"></a>Remarks

Функция члена меняет сохраненную пару значений между `*this` и *правыми.*

### <a name="example"></a>Пример

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
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
x x x x x
x x x x x
a b c
```

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair (STL/CLR)

Сделать `pair` из пары значений.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Параметры

*Значение1*<br/>
Тип первого обернутого значения.

*Значение2*<br/>
Тип второго обернутого значения.

*Первый*<br/>
Первое значение для обертывания.

*Второй*<br/>
Второе значение для упаковки.

### <a name="remarks"></a>Remarks

Функция шаблона возвращает `pair<Value1, Value2>(first, second)`. Вы используете его `pair<Value1, Value2>` для построения объекта из пары значений.

### <a name="example"></a>Пример

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>оператор! (пара) (STL/CLR)

Пара не равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left == right)`возвращается. Вы используете его, чтобы проверить, не упорядочен ли *левый* порядок так же, как *справа,* когда две пары сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>оператор&lt; (пара) (STL/CLR)

Пара меньше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`возвращается. Вы используете его, чтобы проверить, является ли *левый* приказал перед *правом,* когда две пары сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>оператор&lt;(пара) (STL/CLR)

Пара меньше или равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(right < left)`возвращается. Вы используете его, чтобы проверить, не заказываются ли *левые* после *справа,* когда две пары сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>оператор (пара) (STL/CLR)

Парное равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `left.first ==` `right.first &&` `left.second ==` `right.second`возвращается. Вы используете его, чтобы проверить, упорядочен ли *левый* такой же, как *и справа,* когда две пары сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>оператор&gt; (пара) (STL/CLR)

Пара больше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `right` `<` `left`возвращается. Вы используете его, чтобы проверить, является ли *левый* упорядочен после *справа,* когда две пары сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>оператор&gt;(пара) (STL/CLR)

Пара больше или равного сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Правильная пара для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left < right)`возвращается. Вы используете его для проверки того, не заказывают ли *левый* перед *правой,* когда две пары сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```
