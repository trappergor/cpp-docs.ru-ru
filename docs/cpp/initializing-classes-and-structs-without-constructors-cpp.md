---
title: Инициализация скобки для классов, структур и союзов
description: Инициализация скобки с любым классом, структурой или союзом
ms.date: 11/19/2019
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 4628ffe8935fc32e86468c631d5d9e9622d63d2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374079"
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

Обратите внимание, что, когда класс или структура не имеет конструктора, вы предоставляете элементы списка в порядке, который члены объявляются в классе. Если класс имеет конструктор, предоставьте элементы в порядке параметров. Если тип имеет конструктор по умолчанию, либо неявно или явно объявлен, можно использовать инициализацию скобки по умолчанию (с пустыми скобками). Например, следующий класс может быть инициализирован с помощью инициализации как по умолчанию, так и непо умолчанию скобки:

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

Если класс не имеет конструкторов по умолчанию, порядок, в котором члены класса отображаются в инициаторе скобки, является `class_a` порядком, в котором соответствующие параметры отображаются в конструкторе, а не порядком, в котором объявляются участники (как в предыдущем примере). В противном случае, если тип не имеет объявленного конструктора, порядок, в котором члены отображаются в инициаторе скобки, такой же, как и порядок, в котором они объявлены; в этом случае вы можете инициализировать как можно больше членов, как вы хотите, но вы не можете пропустить любого члена. Ниже приводится порядок, используемый при инициализации скобки, когда нет заявленного конструктора:

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

Если конструктор по умолчанию явно объявлен, но помечен как удаленный, инициализация скобки по умолчанию не может быть использована:

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

Инициализация скобки может использоваться где угодно, где обычно инициализация — например, в качестве параметра функции или значения возврата или с **новым** ключевым словом:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

В режиме **/std:c'17** правила инициализации пустых скобки немного более ограничительны. Смотрите [производные конструкторы и расширенную агрегированную инициализацию.](constructors-cpp.md#extended_aggregate)

## <a name="initializer_list-constructors"></a>initializer_list конструкторы

[Initializer_list класс](../standard-library/initializer-list-class.md) представляет собой список объектов определенного типа, которые могут быть использованы в конструкторе и в других контекстах. Вы можете построить initializer_list с помощью инициализации скобки:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
> Чтобы использовать этот класс, необходимо включить [ \<initializer_list>](../standard-library/initializer-list.md) заголовок.

Можно `initializer_list` скопировать. В этом случае членами нового списка являются ссылки на членов первоначального списка:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Стандартные классы контейнеров `string` `wstring`библиотеки, а также , и `regex`, есть `initializer_list` конструкторы. Следующие примеры показывают, как сделать скобки инициализации с этими конструкторами:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{ 'x', 'y', 'z' };
```

## <a name="see-also"></a>См. также раздел

[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Конструкторы](../cpp/constructors-cpp.md)
