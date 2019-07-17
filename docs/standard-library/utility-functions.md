---
title: Функции &lt;utility&gt;
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 723b077500b9b741445efcd8574fb26cd53e5fc7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246300"
---
# <a name="ltutilitygt-functions"></a>Функции &lt;utility&gt;

## <a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает *T*.

## <a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a> Exchange

**(C++14)** Назначает новое значение объекту и возвращает его старое значение.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Параметры

*Val*\
Объект, который будет получать значение new_val.

*new_val*\
Объект, значение которого копируется или перемещается в val.

### <a name="remarks"></a>Примечания

В случае со сложными типами `exchange` не копирует старое значение, если доступен конструктор перемещения, не копирует новое значение, если оно является временным или переносится, и принимает любой тип в качестве нового значения, используя любой доступный оператор назначения с конвертацией. Функция exchange отличается от [std::swap](../standard-library/algorithm-functions.md#swap) в том, что левый аргумент не или копируются на правый аргумент.

### <a name="example"></a>Пример

В следующем примере показано, как использовать `exchange`. В реальной ситуации `exchange` наиболее полезен с большими объектами, копирование которых является дорогостоящим:

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a> вперед

Условно приводит свой аргумент к ссылке rvalue, если аргумент представляет собой rvalue или ссылку rvalue. Это восстанавливает присущие rvalue характеристики аргумента для функции пересылки для обеспечения точной пересылки.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Параметры

*Тип*\
Тип значения, передаваемого в *Arg*, который может отличаться от типа *Arg*. Как правило, определяется аргументом шаблона функции пересылки.

*Arg*\
Аргумент для приведения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку rvalue на *Arg* Если значение, переданное в *Arg* изначально было rvalue или ссылку на rvalue; в противном случае возвращает *Arg* не изменяя его тип.

### <a name="remarks"></a>Примечания

Необходимо указать явный аргумент шаблона для вызова `forward`.

`forward` не пересылает аргумент. Вместо этого путем условного приведения аргумента к ссылке rvalue, как если бы он изначально был rvalue или ссылкой rvalue, `forward` позволяет компилятору выполнять разрешение перегрузки с использованием сведений об исходном типе пересылаемого аргумента. Видимый тип аргумента для функции пересылки может отличаться от его исходного типа, к примеру, если rvalue используется в качестве аргумента в функцию и привязан к имени параметра; наличие имени делает его lvalue, с любой существует значение фактически как rvalue — `forward` восстановит присущие rvalue характеристики аргумента.

Восстановление присущих rvalue характеристик исходного значения аргумента для разрешения перегрузки известно как *точную пересылку*. Точная пересылка позволяет шаблонной функции принимать аргумент любого ссылочного типа и восстановить его присущие rvalue характеристики, когда это необходимо для правильного разрешения перегрузки. С помощью точной пересылки можно сохранять семантику перемещения для значений rvalue и избегать необходимости предоставления перегрузок функциям, которые отличаются только ссылочным типом их аргументов.

## <a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a> Получить

Получает элемент из объекта `pair` по позиции индекса или по типу.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>Параметры

*Индекс*\
Отсчитываемый от нуля индекс выбранного элемента.

*T1*\
Тип первого элемента пары.

*T2*\
Тип второго элемента пары.

*запрос на Вытягивание*\
Пара для выбора элемента.

### <a name="remarks"></a>Примечания

Каждая функция шаблона возвращает ссылку на элемент аргумента `pair` .

Для индексированных перегрузок Если значение *индекс* является 0, функция возвращает `pr.first` и, если значение *индекс* — 1, функция возвращает `pr.second`. Тип `RI` — это тип возвращаемого элемента.

Для перегрузок, у которых нет параметра индекса по аргументу типа выводится возвращаемого элемента. Вызов `get<T>(Tuple)` приведет к ошибке компилятора, если *pr* содержит больше или меньше одного элемента типа T.

### <a name="example"></a>Пример

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a> make_pair

Функция шаблона, которую можно использовать для построения объектов типа `pair`, где типы компонентов автоматически выбираются на основе типов данных, переданных в качестве параметров.

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>Параметры

*val1*\
Значение, которое инициализирует первый элемент `pair`.

*Val2*\
Значение, которое инициализирует второй элемент `pair`.

### <a name="return-value"></a>Возвращаемое значение

Создаваемый парный объект: `pair` < `T`,`U`> (`Val1`, `Val2`).

### <a name="remarks"></a>Примечания

`make_pair` преобразует объект типа [reference_wrapper Class](../standard-library/reference-wrapper-class.md) в типы ссылки, а убывающие массивы и функции — в указатели.

В возвращенном объекте `pair` `T` определяется следующим образом:

- Если тип ввода `T` имеет значение `reference_wrapper<X>`, возвращаемый тип `T` имеет значение `X&`.

- В противном случае возвращаемый тип `T` имеет значение `decay<T>::type`. Если [класс decay](../standard-library/decay-class.md) не поддерживается, то возвращаемый тип `T` совпадает с входным типом `T`.

Возвращаемый тип `U` аналогичным образом определяется по типу ввода `U`.

Одно из преимуществ `make_pair` том, что типы объектов, сохраненные автоматически определяются компилятором и не должно быть задано явным образом. Не используйте явные аргументы шаблона, такие как `make_pair<int, int>(1, 2)` при использовании `make_pair` , так как он является подробным и добавляет проблемах со ссылками rvalue сложных, способные вызвать сбой компиляции. В данном случае правильный синтаксис — `make_pair(1, 2)`

Вспомогательная функция `make_pair` также предоставляет возможность передать два значения в функцию, которой в качестве параметра ввода требуется пара.

### <a name="example"></a>Пример

Пример использования вспомогательной функции `make_pair` для объявления и инициализации пары см. в разделе [Структура pair](../standard-library/pair-structure.md).

## <a name="move"></a> Перемещение

Безусловно приводит свой аргумент к ссылке rvalue, тем самым указывая, что его можно переместить, если его тип допускает перемещения.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Параметры

*Тип*\
Тип, выведенный из типа аргумента, переданного в *Arg*вместе с правилами сворачивания ссылок.

*Arg*\
Аргумент для приведения. Хотя тип *Arg* определен как ссылка rvalue, `move` также принимает аргументы lvalue, поскольку ссылки lvalue можно привязать к ссылкам rvalue.

### <a name="return-value"></a>Возвращаемое значение

`Arg` используется в качестве ссылки rvalue вне зависимости от того, является ли его тип ссылочным.

### <a name="remarks"></a>Примечания

Аргумент шаблона *тип* не предназначено для использования был задан явно, но выводить из типа значения, передаваемого в *Arg*. Тип *тип* Дополнительно адаптируется в соответствии с правилами сворачивания ссылок.

`move` не перемещает свой аргумент. Вместо этого, путем безусловного приведения аргумента, который может быть lvalue — к ссылке rvalue, он обеспечивает компилятору возможность впоследствии переместить, а не копировать, значение, переданное в *Arg* если его тип допускает перемещение. Если его тип не допускает перемещения, его значение копируется.

Если значение, переданное в *Arg* является ссылкой lvalue, то есть он имеет имя, или ее адрес — он станет недействительным при перемещении. Не ссылаются на значения, передаваемого в *Arg* по его имени или адресу после перемещения.

## <a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a> Swap

Меняет местами элементы двух типов или [структура pair](../standard-library/pair-structure.md) объектов.

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Объект типа или типа `pair`.

*Правильно*\
Объект типа или типа `pair`.

### <a name="remarks"></a>Примечания

Одно из преимуществ `swap` том, что типы объектов, сохраненные автоматически определяются компилятором и не должно быть задано явным образом. Не используйте явные аргументы шаблона, такие как `swap<int, int>(1, 2)` при использовании `swap` , так как он является подробным и добавляет проблемах со ссылками rvalue сложных, способные вызвать сбой компиляции.

## <a name="to_chars"></a> to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value); 
to_chars_result to_chars(char* first, char* last, double value); 
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>Примечания

Преобразует значение в строку символов, заполнив диапазон `[first, last)`, где `[first, last)` должен быть допустимый диапазон.
