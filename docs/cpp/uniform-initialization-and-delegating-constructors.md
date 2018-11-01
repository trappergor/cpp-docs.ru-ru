---
title: Единообразная инициализация и делегирование конструкторов
ms.date: 11/04/2016
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
ms.openlocfilehash: 5c5cb6421d9c8ce20f0c5e24de986ee50d9b2238
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496609"
---
# <a name="uniform-initialization-and-delegating-constructors"></a>Единообразная инициализация и делегирование конструкторов

В современном C++ можно использовать *парные фигурные скобки инициализации* для любой тип без знака равенства. Кроме того можно использовать для упрощения кода, когда у вас есть несколько конструкторов, которые выполняют одинаковые делегирующие конструкторы.

## <a name="brace-initialization"></a>Фигурных скобок.

Фигурных скобок можно использовать для любого класса, структуры или объединения. Если тип имеет конструктор по умолчанию, неявно или явно объявлен, можно использовать по умолчанию фигурных скобок. (с помощью пустых фигурных скобок). Например следующий класс может инициализироваться с помощью по умолчанию и не по умолчанию фигурных скобок:

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

Если класс содержит конструкторы не по умолчанию, порядок, в какой класс в скобки инициализатор отображаться элементы — это порядок, в котором соответствующие параметры отображаются в конструкторе, не порядок, в котором объявлены элементы (как в случае с `class_a` в Предыдущий пример). В противном случае если тип не имеет объявленный конструктора, порядок, в котором элементы отображаются в скобки инициализатор совпадает со значением порядок, в котором они объявлены; Таким образом вы можете инициализировать большее число открытых членов, как требуется, но нельзя пропустить любой член. В следующем примере показано порядок, используемый в фигурных скобок. Если нет объявленных конструктора:

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
    class_d d5("string", 'c', 2.0 }; // compiler error
}
```

Если конструктор по умолчанию явно объявлена, но помечаются как удаленные, не может использоваться по умолчанию фигурных скобок:

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

Фигурных скобок можно использовать в любом месте вы обычно выполняете инициализации — например, как функция параметр или возвращаемое значение или с **новый** ключевое слово:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

## <a name="initializerlist-constructors"></a>initializer_list конструкторы

[Класс initializer_list](../standard-library/initializer-list-class.md) представляет список объектов указанного типа, который может использоваться в конструкторе и в других контекстах. Объект initializer_list можно создать с помощью фигурных скобок:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  Чтобы использовать этот класс, необходимо включить [ \<initializer_list >](../standard-library/initializer-list.md) заголовка.

`initializer_list` Можно скопировать. В этом случае новый список членов являются ссылками на элементы исходного списка:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Классы контейнеров стандартной библиотеки, а также `string`, `wstring`, и `regex`, имеют `initializer_list` конструкторы. Ниже приведены примеры инициализации с помощью этих конструкторов, заключать в кавычки.

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{'x', 'y', 'z'};
```

## <a name="delegating-constructors"></a>Делегирующие конструкторы

Многие классы иметь несколько конструкторов, сделать что-то подобное — например, проверка параметров:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

Повторяющийся код можно уменьшить, добавив функцию, которая выполняет все проверки, но код `class_c` бы проще для понимания и поддержки, если один конструктор может делегировать часть работы на другой узел. Чтобы добавить делегирующие конструкторы, используйте `constructor (. . .) : constructor (. . .)` синтаксис:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

При пошаговом выполнении предыдущего примера, обратите внимание, что конструктор `class_c(int, int, int)` сначала вызывает конструктор `class_c(int, int)`, который в свою очередь вызывает `class_c(int)`. Каждый из конструкторов выполняет только работу, не выполняется для других конструкторов.

Первый конструктор, вызываемый инициализирует объект таким образом, чтобы все его члены инициализируются в этот момент. Не удается не инициализация члена в конструктор, который делегирует другого конструктора, как показано ниже:

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

В следующем примере использование инициализаторы нестатических данных членов. Обратите внимание на то, что если конструктор также инициализирует заданного члена данных, переопределяется Инициализатор члена:

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

Делегирование синтаксиса конструктора не предотвращает случайное Создание конструктору рекурсию — Constructor1 вызывает Constructor2, который вызывает Constructor1 — и не будет выдана ошибка до переполнения стека. Это необходимо исключить циклы.

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```