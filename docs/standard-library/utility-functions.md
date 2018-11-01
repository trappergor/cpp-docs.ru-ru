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
ms.openlocfilehash: 7a061ede19c5c4c181b5fea912b9c6212c583267
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543914"
---
# <a name="ltutilitygt-functions"></a>Функции &lt;utility&gt;

||||
|-|-|-|
|[exchange](#exchange)|[forward](#forward)|[get Function &lt;utility&gt;](#get)|
|[make_pair](#make_pair)|[move](#move)|[swap](#swap)|

## <a name="exchange"></a>  exchange

**(C++14)** Назначает новое значение объекту и возвращает его старое значение.

```cpp
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Объект, который будет получать значение new_val.

*new_val*<br/>
Объект, значение которого копируется или перемещается в val.

### <a name="remarks"></a>Примечания

В случае со сложными типами `exchange` не копирует старое значение, если доступен конструктор перемещения, не копирует новое значение, если оно является временным или переносится, и принимает любой тип в качестве нового значения, используя любой доступный оператор назначения с конвертацией.  Функция exchange отличается от [std::swap](../standard-library/algorithm-functions.md#swap) в том, что левый аргумент не перемещается и не копируется в правый аргумент.

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

## <a name="forward"></a>  forward

Условно приводит свой аргумент к ссылке rvalue, если аргумент представляет собой rvalue или ссылку rvalue. Это восстанавливает присущие rvalue характеристики аргумента для функции пересылки для обеспечения точной пересылки.

```cpp
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Type*|Тип значения, передаваемого в *Arg*, который может отличаться от типа *Arg*. Как правило, определяется аргументом шаблона функции пересылки.|
|*Arg*|Аргумент для приведения.|

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку rvalue на *Arg* Если значение, переданное в *Arg* изначально было rvalue или ссылку на rvalue; в противном случае возвращает *Arg* не изменяя его тип.

### <a name="remarks"></a>Примечания

Необходимо указать явный аргумент шаблона для вызова `forward`.

`forward` не пересылает аргумент. Вместо этого путем условного приведения аргумента к ссылке rvalue, как если бы он изначально был rvalue или ссылкой rvalue, `forward` позволяет компилятору выполнять разрешение перегрузки с использованием сведений об исходном типе пересылаемого аргумента. Видимый тип аргумента для функции пересылки может отличаться от его исходного типа, например, если rvalue используется в качестве аргумента для функции и привязано к имени параметра; наличие имени делает его lvalue независимо от того, существует ли это значение фактически как rvalue, `forward` восстановит присущие rvalue характеристики аргумента.

Восстановление присущих rvalue характеристик исходного значения аргумента для выполнения разрешения перегрузки известно как *точная пересылка*. Точная пересылка позволяет шаблонной функции принимать аргумент любого ссылочного типа и восстановить его присущие rvalue характеристики, когда это необходимо для правильного разрешения перегрузки. С помощью точной пересылки можно сохранять семантику перемещения для значений rvalue и избегать необходимости предоставления перегрузок функциям, которые отличаются только ссылочным типом их аргументов.

## <a name="get"></a>  get

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

*Index*<br/>
Индекс указанного элемента, отсчитываемый от нуля.

*T1*<br/>
Тип первого элемента пары.

*T2*<br/>
Тип второго элемента пары.

*запрос на Вытягивание*<br/>
Пара для выбора элемента.

### <a name="remarks"></a>Примечания

Каждая функция шаблона возвращает ссылку на элемент аргумента `pair` .

Для индексированных перегрузок Если значение *индекс* является 0, функция возвращает `pr.first` и, если значение *индекс* — 1, функция возвращает `pr.second`. Тип `RI` — это тип возвращаемого элемента.

Для перегрузок, для которых не указан параметр Index, возвращаемый элемент определяется по аргументу типа. Вызов `get<T>(Tuple)` приведет к ошибке компилятора, если *pr* содержит больше или меньше одного элемента типа T.

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

    /*
    Output:
    9 3.14
    1 0.27
    */

}
```

## <a name="make_pair"></a>  make_pair

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

*val1*<br/>
Значение, которое инициализирует первый элемент `pair`.

*Val2*<br/>
Значение, которое инициализирует второй элемент `pair`.

### <a name="return-value"></a>Возвращаемое значение

Создаваемый парный объект: `pair`< `T`, `U`>(`Val1`, `Val2`).

### <a name="remarks"></a>Примечания

`make_pair` преобразует объект типа [reference_wrapper Class](../standard-library/reference-wrapper-class.md) в типы ссылки, а убывающие массивы и функции — в указатели.

В возвращенном объекте `pair` `T` определяется следующим образом:

- Если тип ввода `T` имеет значение `reference_wrapper<X>`, возвращаемый тип `T` имеет значение `X&`.

- В противном случае возвращаемый тип `T` имеет значение `decay<T>::type`. Если [класс decay](../standard-library/decay-class.md) не поддерживается, то возвращаемый тип `T` совпадает с типом ввода `T`.

Возвращаемый тип `U` аналогичным образом определяется по типу ввода `U`.

Одно из преимуществ `make_pair` заключается в том, что сохраненные типы объектов автоматически определяются компилятором, и их не требуется задавать явным образом. Не используйте явные аргументы шаблона, например `make_pair<int, int>(1, 2)`, при использовании `make_pair`, так как для них характерна избыточная подробность, которая создает дополнительные проблемы со сложными ссылками rvalue, способные вызвать сбой компиляции. В данном случае правильный синтаксис — `make_pair(1, 2)`

Вспомогательная функция `make_pair` также предоставляет возможность передать два значения в функцию, которой в качестве параметра ввода требуется пара.

### <a name="example"></a>Пример

Пример использования вспомогательной функции `make_pair` для объявления и инициализации пары см. в разделе [Структура pair](../standard-library/pair-structure.md).

## <a name="move"></a>  move

Безусловно приводит свой аргумент к ссылке rvalue, тем самым указывая, что его можно переместить, если его тип допускает перемещения.

```cpp
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Type*|Тип, выведенный из типа аргумента, переданного в *Arg*вместе с правилами сворачивания ссылок.|
|*Arg*|Аргумент для приведения. Хотя тип *Arg* определен как ссылка rvalue, `move` также принимает аргументы lvalue, поскольку ссылки lvalue можно привязать к ссылкам rvalue.|

### <a name="return-value"></a>Возвращаемое значение

`Arg` используется в качестве ссылки rvalue вне зависимости от того, является ли его тип ссылочным.

### <a name="remarks"></a>Примечания

Аргумент шаблона *тип* не был задан явно, но выводить из типа значения, передаваемого в *Arg*. Тип *тип* Дополнительно адаптируется в соответствии с правилами сворачивания ссылок.

`move` не перемещает свой аргумент. Вместо этого, путем безусловного приведения аргумента, который может быть lvalue — к ссылке rvalue, он обеспечивает компилятору возможность впоследствии переместить, а не копировать, значение, переданное в *Arg* если его тип допускает перемещение. Если тип значения не допускает перемещения, значение копируется.

Если значение, переданное в *Arg* является ссылкой lvalue, то есть он имеет имя, или ее адрес — он станет недействительным при перемещении. Ссылается на значение, переданное в *Arg* по его имени или адресу после перемещения.

## <a name="swap"></a>  swap

Меняет местами элементы двух объектов [структуры pair](../standard-library/pair-structure.md).

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*left*|Объект типа `pair`.|
|*right*|Объект типа `pair`.|

### <a name="remarks"></a>Примечания

Одно из преимуществ `swap` заключается в том, что сохраненные типы объектов автоматически определяются компилятором, и их не требуется задавать явным образом. Не используйте явные аргументы шаблона, например `swap<int, int>(1, 2)`, при использовании `swap`, так как для них характерна избыточная подробность, которая создает дополнительные проблемы со сложными ссылками rvalue, способные вызвать сбой компиляции.

## <a name="see-also"></a>См. также

[\<utility>](../standard-library/utility.md)<br/>
