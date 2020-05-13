---
title: switchоператор (C++)
description: Ссылка на стандартную switch инструкцию c++ в Microsoft Visual Studio c++.
ms.date: 04/25/2020
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
no-loc:
- switch
- case
- default
- break
- while
- opt
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d43a7a64b5a74f00833093ae8999d73edd7f5753
ms.sourcegitcommit: c4cf8976939dd0e13e25b82930221323ba6f15d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83204163"
---
# <a name="switch-statement-c"></a>`switch`оператор (C++)

Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.

## <a name="syntax"></a>Синтаксис

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;__`switch`__&nbsp;__`(`__&nbsp;*`init-statement`*<sub>opt</sub> <sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;__`)`__&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>opt</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>Remarks

__`switch`__ Оператор заставляет элемент управления передавать *`labeled-statement`* его в тело оператора в зависимости от значения *`condition`* .

Объект *`condition`* должен иметь целочисленный тип или быть типом класса с однозначным преобразованием в целочисленный тип. Целочисленное повышение выполняется, как описано в разделе [стандартные преобразования](standard-conversions.md).

__`switch`__ Текст инструкции состоит из ряда __`case`__ меток и необязательной __`default`__ метки. Является *`labeled-statement`* одной из этих меток и инструкциями, приведенными ниже. Помеченные операторы не являются синтаксическими требованиями, но __`switch`__ оператор не имеет смысла без них. Ни одно *`constant-expression`* из двух значений в __`case`__ операторах не может иметь одно и то же значение. __`default`__ Метка может отображаться только один раз. __`default`__ Оператор часто помещается в конец, но может находиться в любом месте __`switch`__ тела инструкции. __`case`__ Метка или __`default`__ может использоваться только внутри __`switch`__ оператора.

*`constant-expression`* В каждой __`case`__ метке преобразуется в постоянное значение, которое имеет тот же тип, что и *`condition`* . Затем он сравнивается с *`condition`* для равенства. Управление передается первой инструкции после __`case`__ *`constant-expression`* значения, совпадающего со значением *`condition`* . Поведение, полученное в результате, показано в следующей таблице.

### <a name="switch-statement-behavior"></a>`switch`поведение инструкции

| Условие | Действие |
|--|--|
| Преобразованное значение соответствует значению выражения управления с повышенным уровнем. | Управление передается оператору, следующему за этой меткой. |
| Ни одна из констант не соответствует константам в __`case`__ метках; __`default`__ имеется метка. | Элемент управления передается в __`default`__ метку. |
| Ни одна из констант не соответствует константам в __`case`__ метках; __`default`__ Метка отсутствует. | Элемент управления передается оператору после __`switch`__ оператора. |

Если найдено совпадающее выражение, выполнение можно продолжить через более поздние __`case`__ или __`default`__ метки. [`break`](../cpp/break-statement-cpp.md)Оператор используется для того, чтобы прерывать выполнение и передавать управление оператору после __`switch`__ инструкции. Без __`break`__ оператора выполняется выполнение всех инструкций из соответствующей __`case`__ метки в конец __`switch`__ , включая __`default`__ . Пример:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int uppercase_A, lowercase_a, other;
   char c;
   uppercase_A = lowercase_a = other = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            uppercase_A++;
            break;
         case 'a':
            lowercase_a++;
            break;
         default:
            other++;
      }
   }
   printf_s( "\nUppercase A: %d\nLowercase a: %d\nTotal: %d\n",
      uppercase_A, lowercase_a, (uppercase_A + lowercase_a + other) );
}
```

В предыдущем примере `uppercase_A` увеличивается инкрементно, если `c` — `'A'` в верхнем регистре. __`break`__ Инструкция после `uppercase_A++` завершает выполнение __`switch`__ тела оператора и управление передается в __`while`__ цикл. Без __`break`__ оператора выполнение перейдет к следующему оператору с меткой, так что `lowercase_a` и `other` будет также увеличен. Аналогичное назначение обрабатывается __`break`__ оператором для `case 'a'` . Если `c` параметр является строчным `'a'` , `lowercase_a` то увеличивается и __`break`__ оператор завершает __`switch`__ тело оператора. Если `c` не является `'a'` или `'A'` , __`default`__ выполняется инструкция.

**Visual Studio 2017 и более поздние версии:** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` атрибут указан в стандарте c++ 17. Его можно использовать в __`switch`__ операторе. Это подсказка для компилятора или любой, кто читает код, это пошаговое поведение является намеренным. Компилятор Microsoft C++ в настоящее время не предупреждает о поведении fallthrough, поэтому этот атрибут не влияет на поведение компилятора. В этом примере атрибут применяется к пустой инструкции в незавершенном операторе с меткой. Иными словами, необходимо поставить точку с запятой.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 версии 15,3 и более поздних** версий (доступно в [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)). __`switch`__ Оператор может содержать *`init-statement`* предложение, которое заканчивается точкой с запятой. Он вводит и инициализирует переменную, область которой ограничена блоком __`switch`__ оператора:

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

Внутренний блок __`switch`__ инструкции может содержать определения с инициализаторами, если они *достижимы*, то есть не обходятся всеми возможными путями выполнения. Имена, добавленные с помощью этих объявлений, имеют локальную область видимости. Пример:

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

__`switch`__ Оператор может быть вложенным. При вложении __`case`__ метки или __`default`__ связываются с ближайшим __`switch`__ оператором, в котором они заключены.

### <a name="microsoft-specific-behavior"></a>Поведение, характерное для Майкрософт

Microsoft C++ не ограничивает количество __`case`__ значений в __`switch`__ операторе. Это число ограничивается только объемом доступной памяти.

## <a name="see-also"></a>См. также раздел

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
