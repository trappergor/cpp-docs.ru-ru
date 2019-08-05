---
title: Оператор if-else (C++)
ms.date: 07/20/2019
description: Используйте инструкции if-else в C++ для управления условным ветвлением.
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 0e9de2d39e09e148c7e4f3ea82c3dadb173c2d0c
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661643"
---
# <a name="if-else-statement-c"></a>Оператор if-else (C++)

Управляет условным ветвлением. Операторы в *блоке if* выполняются только в том случае, если параметр *-Expression* имеет ненулевое значение (или true). Если значение *Expression* не равно нулю, то *оператор1* и все другие операторы в блоке выполняются, а else-Block, если он есть, пропускается. Если значение *Expression* равно нулю, то параметр if-Block пропускается и выполняется else-Block, если он есть. Выражения, результатом которых является ненулевое значение, являются

- true
- указатель, отличный от NULL,
- любое ненулевое арифметическое значение или
- тип класса, определяющий однозначное преобразование к арифметическому, логическому или типу указателя. (Дополнительные сведения о преобразованиях см. в разделе [стандартные преобразования](../cpp/standard-conversions.md).)

## <a name="syntax"></a>Синтаксис

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>Пример

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if_with_init"></a>Оператор If с инициализатором

**Visual Studio 2017 версии 15,3 и более поздних** версий (доступно в [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): Оператор **If** может также содержать выражение, которое объявляет и инициализирует именованную переменную. Используйте эту форму оператора if, если переменная необходима только в области видимости блока if.

## <a name="example"></a>Пример

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

Во всех формах оператора **If** *выражение*, которое может иметь любое значение, кроме структуры, вычисляется, включая все побочные эффекты. Управление передается из оператора **If** в следующий оператор в программе, если только одна из *инструкций*не содержит [прерывание](../cpp/break-statement-cpp.md), [Continue](../cpp/continue-statement-cpp.md)или [goto](../cpp/goto-statement-cpp.md).

Предложение `if...else` else оператора связано с ближайшим предыдущим оператором if в той же области, которая не имеет соответствующей инструкции **else** .

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr">If constexpr, операторы

**Visual Studio 2017 версии 15,3 и более поздних** версий (доступно в [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): В шаблонах функций можно использовать оператор **If constexpr** , чтобы принимать решения о ветвлении во время компиляции без необходимости прибегать к нескольким перегрузкам функций. Например, можно написать одну функцию, которая обрабатывает распаковку параметров (без перегрузки нулевого параметра):

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>См. также

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор switch (C++)](../cpp/switch-statement-cpp.md)