---
title: оператор if-else (C++)
description: Используйте if-else, if-else с инициализатором и инструкции If-constexpr для управления условным ветвлением.
ms.date: 10/02/2020
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 20d828bf00a79687fe0a9fffbeb1a9cc56fae08c
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765302"
---
# <a name="if-else-statement-c"></a>оператор if-else (C++)

Оператор if-else управляет условным ветвлением. Операторы в *`if-branch`* выполняются, только если *`condition`* результатом вычисления является ненулевое значение (или **`true`** ). Если значение *`condition`* не равно нулю, выполняется следующая инструкция, а инструкция, следующая за необязательным, **`else`** пропускается. В противном случае пропускается Следующая инструкция, и, если имеется **`else`** оператор после оператора, **`else`** выполняется инструкция.

*`condition`* выражения, принимающие ненулевые значения:

- **`true`**
- указатель, отличный от NULL,
- любое ненулевое арифметическое значение или
- тип класса, определяющий однозначное преобразование в арифметический, логический или тип указателя. (Дополнительные сведения о преобразованиях см. в разделе [стандартные преобразования](../cpp/standard-conversions.md).)

## <a name="syntax"></a>Синтаксис

*`init-statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`simple-declaration`*

*`condition`*:\
&emsp; *`expression`*\
&emsp;*`attribute-specifier-seq`* <sub>*неявное согласие*</sub> *`decl-specifier-seq`* *`declarator`**`brace-or-equal-initializer`*

*`statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`compound-statement`*

*`expression-statement`*:\
&emsp;*`expression`* <sub>*неявное согласие*</sub>**`;`**

*`compound-statement`*:\
&emsp;**`{`** *`statement-seq`* <sub>*неявное согласие*</sub>**`}`**

*`statement-seq`*:\
&emsp; *`statement`*\
&emsp; *`statement-seq`* *`statement`*

*`if-branch`*:\
&emsp; *`statement`*

*`else-branch`*:\
&emsp; *`statement`*

*`selection-statement`*:\
&emsp;**`if`** **`constexpr`** <sub>*отказ*</sub>от<sup>17</sup> **`(`** *`init-statement`* <sub>*OPT*</sub><sup>17</sup> 17 *`condition`* **`)`***`if-branch`*\
&emsp;**`if`** **`constexpr`** <sub>*отказ*</sub>от<sup>17</sup> **`(`** *`init-statement`* <sub>*OPT*</sub><sup>17</sup> 17 *`condition`* **`)`** *`if-branch`* **`else`***`else-branch`*

<sup>17</sup> этот необязательный элемент доступен начиная с c++ 17.

## <a name="if-else-statements"></a>операторы if-else

Для всех форм **`if`** инструкции, *`condition`* которая может иметь любое значение, кроме структуры, вычисляется, включая все побочные эффекты. Управление передается из **`if`** оператора в следующий оператор в программе, если только не выполняется *`if-branch`* или не *`else-branch`* содержит [`break`](../cpp/break-statement-cpp.md) , [`continue`](../cpp/continue-statement-cpp.md) или [`goto`](../cpp/goto-statement-cpp.md) .

**`else`** Предложение `if...else` оператора связано с ближайшим предыдущим **`if`** оператором в той же области, у которой нет соответствующей **`else`** инструкции.

### <a name="example"></a>Например, .

В этом примере кода показано **`if`** Использование нескольких использованных операторов как с, так и без него **`else`** :

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

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a> Оператор If с инициализатором

Начиная с C++ 17, **`if`** оператор может также содержать *`init-statement`* выражение, которое объявляет и инициализирует именованную переменную. Используйте эту форму оператора if, если переменная необходима только в области действия оператора if. Для **Microsoft**. Эта форма доступна в Visual Studio 2017 версии 15,3, и для нее требуется по крайней мере [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) параметр компилятора.

### <a name="example"></a>Например, .

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

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr"> If constexpr, операторы

Начиная с C++ 17, можно использовать **`if constexpr`** инструкцию в шаблонах функций, чтобы принимать решения о ветвлении во время компиляции без необходимости прибегать к нескольким перегрузкам функций. Для **Microsoft**. Эта форма доступна в Visual Studio 2017 версии 15,3, и для нее требуется по крайней мере [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) параметр компилятора.

### <a name="example"></a>Например, .

В этом примере показано, как можно написать одну функцию, которая обрабатывает распаковку параметров. Никаких перегрузок с нулевым параметром не требуется:

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

## <a name="see-also"></a>См. также раздел

[Операторы выбора](../cpp/selection-statements-cpp.md)\
[Словами](../cpp/keywords-cpp.md)\
[Оператор `switch` (C++)](../cpp/switch-statement-cpp.md)
