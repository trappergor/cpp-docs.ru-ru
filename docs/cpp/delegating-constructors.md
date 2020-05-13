---
title: Делегирование конструкторов
description: Используйте делегирование конструкторов в СЗ для обращения к другим конструкторам и уменьшения повторения кода.
ms.date: 11/19/2019
ms.openlocfilehash: f26a013aa3c081d900ffc3eb32649acc77505db0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316675"
---
# <a name="delegating-constructors"></a>Делегирующие конструкторы

Во многих классах есть несколько конструкторов, которые делают похожие вещи, например, проверяют параметры:

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

Можно уменьшить повторяющийся код, добавив функцию, которая выполняет всю проверку, `class_c` но код для него будет легче понять и сохранить, если один конструктор может делегировать часть работы другому. Чтобы добавить делегирование конструкторов, `constructor (. . .) : constructor (. . .)` используйте синтаксис:

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

При ступить через предыдущий пример, обратите `class_c(int, int, int)` внимание, что `class_c(int, int)`конструктор сначала `class_c(int)`вызывает конструктор, который в свою очередь вызывает. Каждый из конструкторов выполняет только те работы, которые не выполняются другими конструкторами.

Первый конструктор, который называется инициализирует объект так, что все его члены инициализированы в этой точке. Вы не можете сделать инициализацию участников в конструкторе, который делегирует другому конструктору, как показано здесь:

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

Следующий пример показывает использование нестатических инициализаторов данных. Обратите внимание, что если конструктор также инициализирует данный участник данных, то инициатор участника переопределяется:

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

Синтаксис делегации конструктора не предотвращает случайное создание рекурсии конструктора – Constructor1 вызывает Constructor2, который вызывает Constructor1, и ошибки не выбрасываются до тех пор, пока не будет переполнения стека. Это ваша ответственность, чтобы избежать циклов.

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
