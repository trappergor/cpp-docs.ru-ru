---
title: Инициализация фигурных скобок для классов, структур и объединений
description: Использовать инициализацию фигурных скобок с любым C++ классом, структурой или объединением
ms.date: 11/19/2019
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: a2c9db4572b0dde94c42ec6768a0f3bed7766a96
ms.sourcegitcommit: 15677b0e4d2518847ce59b158990b25c4077e565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75652628"
---
# <a name="brace-initialization"></a>Инициализация фигурных скобок

Не всегда обязательно определять конструктор для класса (особенно для относительно простых классов). Пользователи могут использовать для объектов класса или структур унифицированную инициализацию, как показано в следующем примере:

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

Обратите внимание, что если класс или структура не имеет конструктора, вы предоставляете элементы списка в том порядке, в котором элементы объявляются в классе. Если у класса есть конструктор, укажите элементы в порядке параметров. Если у типа есть конструктор по умолчанию, явно или неявно объявленный, можно использовать инициализацию скобок по умолчанию (с пустыми фигурными скобками). Например, следующий класс можно инициализировать с помощью инициализации по умолчанию и стандартной фигурной скобки:

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

Если класс имеет конструкторы, отличные от конструктора по умолчанию, то порядок, в котором члены класса отображаются в инициализаторе фигурных скобок, является порядком, в котором соответствующие параметры отображаются в конструкторе, а не в том порядке, в котором объявляются элементы (как в предыдущем примере с `class_a`). В противном случае, если тип не имеет объявленного конструктора, порядок, в котором элементы отображаются в инициализаторе фигурных скобок, совпадает с порядком, в котором они объявляются. в этом случае можно инициализировать столько открытых членов, сколько нужно, но нельзя пропустить ни одного элемента. В следующем примере показан порядок, который используется в инициализации фигурных скобок при отсутствии объявленного конструктора:

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5{ "string", 'c', 2.0 }; // compiler error
}
```

Если конструктор по умолчанию объявлен явно, но помечен как удаленный, инициализацию по умолчанию нельзя использовать:

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

Можно использовать инициализацию фигурных скобок в любом месте, как обычно при инициализации, например в качестве параметра функции или возвращаемого значения или с помощью ключевого слова **New** :

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

В **/std: режим c++ 17** правила инициализации пустой скобки немного более ограниченны. См. раздел [производные конструкторы и расширенная агрегатная инициализация](constructors-cpp.md#extended_aggregate).

## <a name="initializer_list-constructors"></a>конструкторы initializer_list

[Класс initializer_list](../standard-library/initializer-list-class.md) представляет список объектов указанного типа, которые могут использоваться в конструкторе и в других контекстах. Вы можете создать initializer_list с помощью инициализации фигурных скобок:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  Чтобы использовать этот класс, необходимо включить заголовок [\<initializer_list >](../standard-library/initializer-list.md) .

Можно скопировать `initializer_list`. В этом случае члены нового списка являются ссылками на элементы исходного списка:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Классы контейнеров стандартной библиотеки, а также `string`, `wstring`и `regex`, имеют `initializer_list` конструкторы. В следующих примерах показано, как выполнить инициализацию фигурных скобок с помощью этих конструкторов:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{ 'x', 'y', 'z' };
```


## <a name="see-also"></a>См. также:

[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Конструкторы](../cpp/constructors-cpp.md)
