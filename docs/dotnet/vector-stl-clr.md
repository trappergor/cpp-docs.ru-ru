---
title: vector (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
ms.openlocfilehash: c6a001797e90bd7381358abb16612926442e8d9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371824"
---
# <a name="vector-stlclr"></a>vector (STL/CLR)

Класс шаблона описывает объект, который управляет последовательностью элементов различной длины, которая имеет случайный доступ. Контейнер используется `vector` для управления последовательностью элементов в качестве смежного блока хранения. Блок реализован как массив, который растет по требованию.

В описании `GValue` ниже, так же, как *значение,* если последний `Value^`тип реф, и в этом случае это .

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    ref class vector
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IVector<GValue>
    { ..... };
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Тип элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/векторная>

**Название:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[vector::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[vector::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[vector::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[vector::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[vector::generic_container (STL/CLR)](#generic_container)|Тип общего интерфейса для контейнера.|
|[vector::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для общего интерфейса для контейнера.|
|[vector::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для общего интерфейса для контейнера.|
|[vector::generic_value (STL/CLR)](#generic_value)|Тип элемента для общего интерфейса для контейнера.|
|[vector::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[vector::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[vector::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[vector::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|
|[vector::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[vector::assign (STL/CLR)](#assign)|Заменяет все элементы.|
|[vector::at (STL/CLR)](#at)|Обращается к элементу в указанной позиции.|
|[vector::back (STL/CLR)](#back)|Обращается к последнему элементу.|
|[vector::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[vector::capacity (STL/CLR)](#capacity)|Возвращает объем пространства, выделенного для хранения контейнера.|
|[vector::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[vector::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[vector::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[vector::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[vector::front (STL/CLR)](#front)|Обращается к первому элементу.|
|[vector::insert (STL/CLR)](#insert)|Добавляет элементы в заданном положении.|
|[vector::pop_back (STL/CLR)](#pop_back)|Удаляет последний элемент.|
|[vector::push_back (STL/CLR)](#push_back)|Добавляет новый последний элемент.|
|[vector::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[vector::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[vector::reserve (STL/CLR)](#reserve)|Обеспечивает минимальную емкость роста контейнера.|
|[vector::resize (STL/CLR)](#resize)|Изменяет количество элементов.|
|[vector::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[vector::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[vector::to_array (STL/CLR)](#to_array)|Копирует контролируемую последовательность в новый массив.|
|[vector::vector (STL/CLR)](#vector)|Создает объект контейнера.|

|Свойство|Описание|
|--------------|-----------------|
|[vector::back_item (STL/CLR)](#back_item)|Обращается к последнему элементу.|
|[vector::front_item (STL/CLR)](#front_item)|Обращается к первому элементу.|

|Оператор|Описание|
|--------------|-----------------|
|[vector::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|
|[vector::operator (STL/CLR)](#op)|Обращается к элементу в указанной позиции.|
|[оператор! (вектор) (STL/CLR)](#op_neq)|Определяет, не `vector` равен ли `vector` объект другому объекту.|
|[оператор< (вектор) (STL/CLR)](#op_lt)|Определяет, является `vector` ли объект `vector` меньше, чем другой объект.|
|[оператор<(вектор) (STL/CLR)](#op_lteq)|Определяет, является `vector` ли объект меньше или `vector` равен другому объекту.|
|[оператора (вектор) (STL/CLR)](#op_eq)|Определяет, приравнивается `vector` ли `vector` объект к другому объекту.|
|[operator> (vector) (STL/CLR)](#op_gt)|Определяет, является `vector` ли объект `vector` больше другого объекта.|
|[оператор>(вектор) (STL/CLR)](#op_gteq)|Определяет, является `vector` ли объект больше или `vector` равен другому объекту.|

## <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Дублирование объекта.|
|<xref:System.Collections.IEnumerable>|Последовательность через элементы.|
|<xref:System.Collections.ICollection>|Поддержание группы элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность через набранные элементы.|
|<xref:System.Collections.Generic.ICollection%601>|Поддержание группы набранных элементов.|
|<xref:System.Collections.Generic.IList%601>|Поддержание упорядоченной группы набранных элементов.|
|Значение IVector<\>|Поддержание общего контейнера.|

## <a name="remarks"></a>Remarks

Объект выделяет и освобождает хранилище для последовательности, которую он контролирует через сохраненный массив элементов *значения,* который растет по требованию. Рост происходит таким образом, что стоимость приложения нового элемента амортизируется постоянное время. Другими словами, стоимость добавления элементов в конце не увеличивается, в среднем, так как длина контролируемой последовательности увеличивается. Таким образом, вектор является хорошим кандидатом для базового контейнера для стека класса шаблонов [(STL/CLR).](../dotnet/stack-stl-clr.md)

Поддерживает `vector` итераторы случайного доступа, что означает, что вы можете обратиться к элементу непосредственно с учетом `size() - 1` его численного положения, считая от нуля для первого (переднего) элемента, до последнего (обратного) элемента. Это также означает, что вектор является хорошим кандидатом для базового контейнера для priority_queue класса [шаблонов (STL/CLR).](../dotnet/priority-queue-stl-clr.md)

Векторный итератор хранит ручку к связанному объекту вектора, а также смещения элемента, который он обозначает. Итераторы можно использовать только с связанными с ними контейнерными объектами. Смещение векторного элемента такое же, как и его положение.

Вставка или стирание элементов могут изменять значение элемента, хранящееся в заданном положении, поэтому значение, назначенное итератором, также может изменяться. (Контейнер, возможно, придется копировать элементы вверх или вниз, чтобы создать отверстие перед вставкой или заполнить отверстие после стирания.) Тем не менее, векторный итератор остается в `[0, size()]`силе до тех пор, пока его предвзятость находится в диапазоне. Кроме того, действительный итератор остается недопустимым - его можно использовать для доступа или изменения значения элемента, `size()`который он обозначает, - до тех пор, пока его смещение не равно .

Стирание или удаление элемента вызывает деструктор для его хранимого значения. Уничтожение контейнера стирает все элементы. Таким образом, контейнер, тип элемента которого является классом реф, гарантирует, что никакие элементы не переживут контейнер. Обратите внимание, однако, что контейнер с ручками не разрушает его элементы.

## <a name="members"></a>Участники

## <a name="vectorassign-stlclr"></a><a name="assign"></a>вектор:назначить (STL/CLR)

Заменяет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*Первый*<br/>
Начало диапазона для вставки.

*Последний*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Валь*<br/>
Значение элемента для вставки.

### <a name="remarks"></a>Remarks

Функция первого члена заменяет контролируемую последовательность повторением *элементов подсчета* стоимости *val.* Вы используете его для заполнения контейнера с элементами, все имеющие одинаковое значение.

Если `InIt` это целый тип, вторая функция члена ведет `assign((size_type)first, (value_type)last)`себя так же, как и . В противном случае, он заменяет`first` `last`контролируемую последовательность с последовательностью , ). Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности.

Функция третьего члена заменяет контролируемую последовательность последовательностью, обозначенной *правом*регистратора. Вы используете его, чтобы сделать контролируемую последовательность копией последовательности, описанной регистратором.

### <a name="example"></a>Пример

```cpp
// cliext_vector_assign.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// assign a repetition of values
    cliext::vector<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign an iterator range
    c2.assign(c1.begin(), c1.end() - 1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign an enumeration
    c2.assign(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
x x x x x x
a b
a b c
```

## <a name="vectorat-stlclr"></a><a name="at"></a>вектор:at (STL/CLR)

Обращается к элементу в указанной позиции.

### <a name="syntax"></a>Синтаксис

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>Параметры

*pos*<br/>
Позиция элемента, к которому осуществляется доступ.

### <a name="remarks"></a>Remarks

Функция члена возвращает ссылку на элемент контролируемой последовательности при *позиции pos*. Вы используете его, чтобы читать или писать элемент, положение которого вы знаете.

### <a name="example"></a>Пример

```cpp
// cliext_vector_at.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using at
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// change an entry and redisplay
    c1.at(1) = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorback-stlclr"></a><a name="back"></a>вектор:назад (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference back();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает ссылку на последний элемент контролируемой последовательности, который должен быть непустым. Вы используете его для доступа к последнему элементу, когда вы знаете, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_vector_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

// alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="vectorback_item-stlclr"></a><a name="back_item"></a>вектор:back_item (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Remarks

Свойство получает доступ к последнему элементу контролируемой последовательности, который должен быть непустым. Вы используете его для чтения или написания последнего элемента, когда вы знаете, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_vector_back_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

// alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="vectorbegin-stlclr"></a><a name="begin"></a>вектор::начало (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает итератор случайного доступа, который обозначает первый элемент контролируемой последовательности, или просто после окончания пустой последовательности. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_vector_begin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);

// alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
x y c
```

## <a name="vectorcapacity-stlclr"></a><a name="capacity"></a>вектор:емкость (STL/CLR)

Возвращает объем пространства, выделенного для хранения контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
size_type capacity();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает хранилище, выделенное в настоящее время для удержания контролируемой последовательности, значение по крайней мере такой же большой, как [вектор::размер (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`. Вы используете его, чтобы определить, сколько контейнер может вырасти, прежде чем он должен перераспределить хранения для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_capacity.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorclear-stlclr"></a><a name="clear"></a>вектор:ясно (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Remarks

Функция участника эффективно вызывает [вектор::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [вектор::начало (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [вектор::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)`())`. Вы используете его для обеспечения того, чтобы контролируемая последовательность была пустой.

### <a name="example"></a>Пример

```cpp
// cliext_vector_clear.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

// add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');

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

## <a name="vectorconst_iterator-stlclr"></a><a name="const_iterator"></a>вектор:const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T2` типа, который может служить постоянным итератором случайного доступа для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_const_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reference-stlclr"></a><a name="const_reference"></a>вектор:const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Remarks

Тип описывает постоянную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_vector_const_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::vector<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>вектор::const_reverse_iterator (STL/CLR)

Тип постоянного обратного итератора для контролируемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T4` типа, который может служить постоянным обратным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="vectordifference_type-stlclr"></a><a name="difference_type"></a>вектор::difference-type (STL/CLR)

Типы подписанного расстояния между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Remarks

Тип описывает количество подписанных элементов.

### <a name="example"></a>Пример

```cpp
// cliext_vector_difference_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::difference_type diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.end();
        it != c1.begin(); --it) --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="vectorempty-stlclr"></a><a name="empty"></a>вектор:пустой (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Remarks

Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [вектору:размер (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() == 0`. Вы используете его, чтобы проверить, является ли вектор пустым.

### <a name="example"></a>Пример

```cpp
// cliext_vector_empty.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

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

## <a name="vectorend-stlclr"></a><a name="end"></a>вектор:конец (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Remarks

Функция участника возвращает итератор случайного доступа, который указывает только за пределами контролируемой последовательности. Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_vector_end.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    cliext::vector<wchar_t>::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);

// alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
a x y
```

## <a name="vectorerase-stlclr"></a><a name="erase"></a>вектор::erase (STL/CLR)

Удаляет элементы в указанных позициях.

### <a name="syntax"></a>Синтаксис

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало диапазона для стирания.

*Последний*<br/>
Конец диапазона для стирания.

*Где*<br/>
Элемент для стирания.

### <a name="remarks"></a>Remarks

Функция первого члена удаляет элемент контролируемой последовательности, на который *указывается, где*. Вы используете его для удаления одного элемента.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Вы используете его для удаления ноль или более смежных элементов.

Обе функции участника возвращают итератор, который обозначает первый элемент, оставшийся за пределами удаленных элементов, или [вектор::конец (STL/CLR),](../dotnet/vector-end-stl-clr.md) `()` если такого элемента не существует.

При стирании элементов количество копий элементов линейное по количеству элементов между концом стирания и более близкой концом последовательности. (При стихе одного или нескольких элементов на обоих концах последовательности копии элементов не возникают.)

### <a name="example"></a>Пример

```cpp
// cliext_vector_erase.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

// add elements and display " b c d e"
    c1.push_back(L'd');
    c1.push_back(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase all but end
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorfront-stlclr"></a><a name="front"></a>вектор:фронт (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference front();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает ссылку на первый элемент контролируемой последовательности, который должен быть непустым. Вы используете его для чтения или написания первого элемента, когда вы знаете, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_vector_front.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

// alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="vectorfront_item-stlclr"></a><a name="front_item"></a>вектор:front_item (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Remarks

Свойство получает доступ к первому элементу контролируемой последовательности, который должен быть непустым. Вы используете его для чтения или написания первого элемента, когда вы знаете, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_vector_front_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

// alter first item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="vectorgeneric_container-stlclr"></a><a name="generic_container"></a>вектор:generic_container (STL/CLR)

Тип общего интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    IVector<generic_value>
    generic_container;
```

### <a name="remarks"></a>Remarks

Тип описывает общий интерфейс для этого класса контейнеров шаблонов.

### <a name="example"></a>Пример

```cpp
// cliext_vector_generic_container.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->insert(gc1->end(), L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.push_back(L'e');

    System::Collections::IEnumerator^ enum1 =
        gc1->GetEnumerator();
    while (enum1->MoveNext())
        System::Console::Write("{0} ", enum1->Current);
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

## <a name="vectorgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>вектор:generic_iterator (STL/CLR)

Тип итератора для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает общий итератор, который может быть использован с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_vector_generic_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="vectorgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>вектор:generic_reverse_iterator (STL/CLR)

Тип обратного итератора для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает общий обратный итератор, который может быть использован с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_vector_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c c
```

## <a name="vectorgeneric_value-stlclr"></a><a name="generic_value"></a>вектор:generic_value (STL/CLR)

Тип элемента для использования с общим интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Remarks

Тип описывает объект типа, `GValue` описывающий значение сохраненного элемента для использования с общим интерфейсом для этого класса контейнеров шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_vector_generic_value.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="vectorinsert-stlclr"></a><a name="insert"></a>вектор:вставка (STL/CLR)

Добавляет элементы в заданном положении.

### <a name="syntax"></a>Синтаксис

```cpp
iterator insert(iterator where, value_type val);
void insert(iterator where, size_type count, value_type val);
template<typename InIt>
    void insert(iterator where, InIt first, InIt last);
void insert(iterator where,
    System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*Первый*<br/>
Начало диапазона для вставки.

*Последний*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Валь*<br/>
Значение элемента для вставки.

*Где*<br/>
Где в контейнер вставить раньше.

### <a name="remarks"></a>Remarks

Каждый из функций участника вставляет, прежде чем элемент указал, *где* в контролируемой последовательности, последовательность, указанная остальными работами.

Функция первого элемента вставляет элемент с значением *val* и возвращает итератор, который обозначает вновь вставленный элемент. Вы используете его для вставки одного элемента перед местом, назначенным итератором.

Функция второго члена вставляет повторение элементов *подсчета* значений *val.* Вы используете его для вставки ноль или более смежных элементов, которые являются копиями одного и того же значения.

Если `InIt` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(where, (size_type)first, (value_type)last)`. В противном случае,`first`он `last`вставляет последовательность , ). Вы используете его для вставки нуля или более смежных элементов, скопированных из другой последовательности.

Функция четвертого члена вставляет последовательность, обозначенную *справа.* Вы используете его для вставки последовательности, описанной регистратором.

При вставке одного элемента количество копий элементов линейное в количестве элементов между точкой вставки и более близкой концом последовательности. (При вставке одного или нескольких элементов на обоих концах последовательности копии элементов не возникают.) Если `InIt` итератор ввода, третья функция элемента эффективно выполняет одну вставку для каждого элемента в последовательности. В противном `N` случае при вставке элементов количество `N` копий элементов линейное плюс количество элементов между точкой вставки и более близкой концом последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_insert.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value using iterator
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a repetition of values
    cliext::vector<wchar_t> c2;
    c2.insert(c2.begin(), 2, L'y');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an iterator range
    it = c1.end();
    c2.insert(c2.end(), c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    c2.insert(c2.begin(),   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(begin()+1, L'x') = x
a x b c
y y
y y a x b
a x b c y y a x b
```

## <a name="vectoriterator-stlclr"></a><a name="iterator"></a>вектор:Iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T1` типа, который может служить в качестве итератора случайного доступа для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();

// alter first element and redisplay
    it = c1.begin();
    *it = L'x';
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x b c
```

## <a name="vectoroperator-stlclr"></a><a name="op_as"></a>вектор:оператор ( STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
vector<Value>% operator=(vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Remarks

Оператор-член копирует *право* на объект, а затем возвращается. `*this` Вы используете его, чтобы заменить контролируемую последовательность с копией контролируемой последовательности в *правой*.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_as.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="vectoroperatorstlclr"></a><a name="op"></a>вектор:оператор (STL/CLR)

Обращается к элементу в указанной позиции.

### <a name="syntax"></a>Синтаксис

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>Параметры

*pos*<br/>
Позиция элемента, к которому осуществляется доступ.

### <a name="remarks"></a>Remarks

Оператор-член возвращает референ элементу в позиционном *pos*. Вы используете его для доступа к элементу, положение которого вы знаете.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_sub.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using subscripting
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();

// change an entry and redisplay
    c1[1] = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorpop_back-stlclr"></a><a name="pop_back"></a>вектор::pоп-бэк (STL/CLR)

Удаляет последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void pop_back();
```

### <a name="remarks"></a>Remarks

Функция члена удаляет последний элемент контролируемой последовательности, который должен быть непустым. Вы используете его, чтобы сократить вектор на один элемент на спине.

### <a name="example"></a>Пример

```cpp
// cliext_vector_pop_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// pop an element and redisplay
    c1.pop_back();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b
```

## <a name="vectorpush_back-stlclr"></a><a name="push_back"></a>вектор::push'back (STL/CLR)

Добавляет новый последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>Remarks

Функция члена вставляет элемент `val` со значением в конце контролируемой последовательности. Вы используете его для придатка другого элемента к вектору.

### <a name="example"></a>Пример

```cpp
// cliext_vector_push_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorrbegin-stlclr"></a><a name="rbegin"></a>вектор:rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает обратный итератор, который обозначает последний элемент контролируемой последовательности, или просто после начала пустой последовательности. Таким образом, он задает для обратной последовательности параметр `beginning`. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_vector_rbegin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);

// alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
a y x
```

## <a name="vectorreference-stlclr"></a><a name="reference"></a>вектор:ссылка (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Remarks

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_vector_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

// modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;

        ref += (wchar_t)(L'A' - L'a');
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
A B C
```

## <a name="vectorrend-stlclr"></a><a name="rend"></a>вектор::rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает обратный итератор, который указывает только за началом контролируемой последовательности. Таким образом, он задает для обратной последовательности параметр `end`. Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_vector_rend.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);

// alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
y x c
```

## <a name="vectorreserve-stlclr"></a><a name="reserve"></a>вектор:резерв (STL/CLR)

Обеспечивает минимальную емкость роста контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
void reserve(size_type count);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Новая минимальная емкость контейнера.

### <a name="remarks"></a>Remarks

Функция члена гарантирует, `capacity()` что отныне возвращается по крайней мере *кол*. Вы используете его для обеспечения того, чтобы контейнер не должен перераспределять хранилище для контролируемой последовательности, пока он не вырос до заданного размера.

### <a name="example"></a>Пример

```cpp
// cliext_vector_reserve.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorresize-stlclr"></a><a name="resize"></a>вектор:изгабаритный размер (STL/CLR)

Изменяет количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>Параметры

*new_size*<br/>
Новый размер контролируемой последовательности.

*Валь*<br/>
Значение обивки элемента.

### <a name="remarks"></a>Remarks

Функции участника гарантируют, что [вектор::размер (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` отныне *возвращается new_size.* Если это должно сделать контролируемую последовательность длиннее, функция первого члена придукивает элементы `value_type()`значением, в то время как функция второго члена придувает элементы с *значением val.* Чтобы сделать контролируемую последовательность короче, обе функции элемента эффективно стирают последний [вектор элемента: размер (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` раз. Вы используете его для обеспечения того, чтобы контролируемая последовательность имеет размер *new_size,* либо обрезки или обивка текущей контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_resize.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container and pad with default values
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());
    c1.resize(4);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// resize to empty
    c1.resize(0);
    System::Console::WriteLine("size() = {0}", c1.size());

// resize and pad
    c1.resize(5, L'x');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
0 0 0 0
size() = 0
x x x x x
```

## <a name="vectorreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>вектор::reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает объект неопределенного `T3` типа, который может служить обратным итератором для контролируемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_vector_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();

// alter first element and redisplay
    rit = c1.rbegin();
    *rit = L'x';
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
x b a
```

## <a name="vectorsize-stlclr"></a><a name="size"></a>вектор:размер (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Remarks

Функция-член возвращает длину управляемой последовательности. Вы используете его для определения количества элементов, наиболее наиболее контролируемых последовательности. Если все, что вас волнует, является ли последовательность имеет ненулевой размер, см. [вектор::пустой (STL/CLR)](../dotnet/vector-empty-stl-clr.md)`()`.

### <a name="example"></a>Пример

```cpp
// cliext_vector_size.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

// add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');
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

## <a name="vectorsize_type-stlclr"></a><a name="size_type"></a>вектор:size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Remarks

Тип описывает неотрицательное количество элементов.

### <a name="example"></a>Пример

```cpp
// cliext_vector_size_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="vectorswap-stlclr"></a><a name="swap"></a>вектор:своп (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Remarks

Функция члена меняет контролируемые последовательности между `*this` и *правыми.* Он делает это в постоянное время, и он не бросает никаких исключений. Вы используете его как быстрый способ обмена содержимого двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_vector_swap.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::vector<wchar_t> c2(5, L'x');
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

## <a name="vectorto_array-stlclr"></a><a name="to_array"></a>вектор:to_array (STL/CLR)

Копирует контролируемую последовательность в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Remarks

Функция члена возвращает массив, содержащий контролируемую последовательность. Вы используете его для получения копии контролируемой последовательности в форме массива.

### <a name="example"></a>Пример

```cpp
// cliext_vector_to_array.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push_back(L'd');
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

## <a name="vectorvalue_type-stlclr"></a><a name="value_type"></a>вектор:value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом *значения*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_vector_value_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using value_type
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::vector<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorvector-stlclr"></a><a name="vector"></a>вектор:вектор (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
vector();
vector(vector<Value>% right);
vector(vector<Value>^ right);
explicit vector(size_type count);
vector(size_type count, value_type val);
template<typename InIt>
    vector(InIt first, InIt last);
vector(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*Первый*<br/>
Начало диапазона для вставки.

*Последний*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Объект или диапазон для вставки.

*Валь*<br/>
Значение элемента для вставки.

### <a name="remarks"></a>Remarks

Конструктор:

`vector();`

инициализирует контролируемую последовательность без элементов. Вы используете его для указания пустой начальной контролируемой последовательности.

Конструктор:

`vector(vector<Value>% right);`

инициализирует контролируемую`right.begin()`последовательность с последовательностью , `right.end()`). Вы используете его для указания начальной контролируемой последовательности, которая является копией последовательности, контролируемой *правой*векторной объектом.

Конструктор:

`vector(vector<Value>^ right);`

инициализирует контролируемую`right->begin()`последовательность с последовательностью , `right->end()`). Вы используете его для указания начальной контролируемой последовательности, которая является копией последовательности, контролируемой векторным объектом, рукоятки которого *правы.*

Конструктор:

`explicit vector(size_type count);`

инициализирует контролируемую последовательность `value_type()`с *элементами подсчета* каждый со значением. Вы используете его для заполнения контейнера элементами, имеющими значение по умолчанию.

Конструктор:

`vector(size_type count, value_type val);`

инициализирует контролируемую последовательность с *элементами подсчета* каждый с *значением val.* Вы используете его для заполнения контейнера с элементами, все имеющие одинаковое значение.

Конструктор:

`template<typename InIt>`

`vector(InIt first, InIt last);`

инициализирует контролируемую`first`последовательность с последовательностью , `last`). Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности.

Конструктор:

`vector(System::Collections::Generic::IEnumerable<Value>^ right);`

инициализирует контролируемую последовательность с последовательностью, обозначенной *правом*перечисления. Вы используете его, чтобы сделать контролируемую последовательность копией другой последовательности, описанной регистратором.

### <a name="example"></a>Пример

```cpp
// cliext_vector_construct.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct with a repetition of default values
    cliext::vector<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// construct with a repetition of values
    cliext::vector<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    cliext::vector<wchar_t>::iterator it = c3.end();
    cliext::vector<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    cliext::vector<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying a container handle
    cliext::vector<wchar_t> c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
0 0 0
x x x x x x
x x x x x
x x x x x x
x x x x x x
x x x x x x
```

## <a name="operator-vector-stlclr"></a><a name="op_neq"></a>оператор! (вектор) (STL/CLR)

Вектор не равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator!=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left == right)`возвращается. Вы используете его для проверки того, не упорядочен ли *левый* порядок так же, как *справа,* когда два вектора сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_ne.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lt"></a>оператор&lt; (вектор) (STL/CLR)

Вектор меньше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator<(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора возвращается верно, если, для самой низкой позиции, `i` для которой `!(right[i] < left[i])` это также верно, что `left[i] < right[i]`. В противном `left->size() < right->size()` случае, он возвращает Вы используете его для проверки того, *левая* упорядочена перед *правой,* когда два вектора сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_lt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lteq"></a>оператор&lt;(вектор) (STL/CLR)

Вектор меньше или равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator<=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(right < left)`возвращается. Вы используете его для проверки того, не заказываются ли *левые* после *справа,* когда два вектора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_le.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operator-vector-stlclr"></a><a name="op_eq"></a>оператора (вектор) (STL/CLR)

Вектор равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator==(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора возвращается верно только в том случае, если последовательности, `i`контролируемые *левым* и *правым,* имеют одинаковую длину и для каждой позиции. `left[i] ==` `right[i]` Вы используете его для проверки того, упорядочен ли *левый* такой же, как *и справа,* когда два вектора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_eq.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gt"></a>оператор&gt; (вектор) (STL/CLR)

Вектор больше сравнения.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator>(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `right` `<` `left`возвращается. Вы используете его для проверки того, упорядочен ли *левый* после *справа,* когда два вектора сравниваются элемент за элементом.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_gt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gteq"></a>оператор&gt;(вектор) (STL/CLR)

Вектор больше или равное сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator>=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Левой*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Remarks

Функция оператора `!(left < right)`возвращается. Вы используете его для проверки того, не заказывают ли *левый* перед *правой,* когда два вектора сравниваются по элементам.

### <a name="example"></a>Пример

```cpp
// cliext_vector_operator_ge.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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
