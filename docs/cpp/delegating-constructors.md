---
title: Делегирование конструкторов (C++)
description: Используйте делегирование конструкторов в C++ для вызова других конструкторов и сокращения числа повторений кода.
ms.date: 11/19/2019
ms.openlocfilehash: 533cdfbeb882f3770cc554b0633611a4ffc2cfbd
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74250700"
---
# <a name="delegating-constructors"></a>Делегирующие конструкторы

Многие классы имеют несколько конструкторов, которые выполняют аналогичные действия, например, проверяют параметры:

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

Можно сократить повторяющийся код, добавив функцию, которая выполняет всю проверку, но код для `class_c` будет проще в понимании и сопровождении, если один конструктор может делегировать некоторую работу другому. Чтобы добавить делегирование конструкторов, используйте синтаксис `constructor (. . .) : constructor (. . .)`:

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

При пошаговом выполнении предыдущего примера обратите внимание, что конструктор `class_c(int, int, int)` сначала вызывает конструктор `class_c(int, int)`, который, в свою очередь, вызывает `class_c(int)`. Каждый из конструкторов выполняет только работу, которая не выполняется другими конструкторами.

Первый конструктор, который вызывается, инициализирует объект, чтобы все его члены были инициализированы в этой точке. Невозможно выполнить инициализацию члена в конструкторе, который делегирует другому конструктору, как показано ниже:

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

В следующем примере показано использование нестатических инициализаторов элементов данных. Обратите внимание, что если конструктор также инициализирует данный элемент данных, инициализатор члена переопределяется:

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

Синтаксис делегирования конструктора не предотвращает случайное создание рекурсии конструктора — Constructor1 вызывает Constructor2, который вызывает Constructor1, и ошибки не создаются, пока не произойдет переполнение стека. Вы обязаны избегать циклов.

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
