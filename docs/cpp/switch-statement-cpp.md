---
title: :::no-loc(switch):::оператор (C++)
description: 'Ссылка на стандартную :::no-loc(switch)::: инструкцию c++ в Microsoft Visual Studio c++.'
ms.date: 04/25/2020
f1_keywords:
- :::no-loc(default):::_cpp
- :::no-loc(switch):::_cpp
- :::no-loc(case):::_cpp
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C++]'
- ':::no-loc(case)::: keyword [C++], in :::no-loc(switch)::: statements'
- ':::no-loc(default)::: keyword [C++]'
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
- ':::no-loc(while):::'
- ':::no-loc(opt):::'
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d71989b6d8af0213c4cd6d4fbd8d5a84b318701a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223594"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::`оператор (C++)

Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.

## <a name="syntax"></a>Синтаксис

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;**`:::no-loc(switch):::`**&nbsp;**`(`**&nbsp;*`init-statement`*<sub>:::no-loc(opt):::</sub> <sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;**`)`**&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>:::no-loc(opt):::</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Примечания

Оператор **`:::no-loc(switch):::`** передает управление одному из *`labeled-statement`* в своем теле в зависимости от значения *`condition`* .

Объект *`condition`* должен иметь целочисленный тип или быть типом класса с однозначным преобразованием в целочисленный тип. Целочисленное повышение выполняется, как описано в разделе [стандартные преобразования](standard-conversions.md).

**`:::no-loc(switch):::`** Текст инструкции состоит из ряда **`:::no-loc(case):::`** меток и :::no-loc(opt)::: **`:::no-loc(default):::`** метки ионал. Является *`labeled-statement`* одной из этих меток и инструкциями, приведенными ниже. Помеченные операторы не являются синтаксическими требованиями, но **`:::no-loc(switch):::`** оператор не имеет смысла без них. Ни одно *`constant-expression`* из двух значений в **`:::no-loc(case):::`** операторах не может иметь одно и то же значение. **`:::no-loc(default):::`** Метка может отображаться только один раз. **`:::no-loc(default):::`** Оператор часто помещается в конец, но может находиться в любом месте **`:::no-loc(switch):::`** тела инструкции. Метка **`:::no-loc(case):::`** или **`:::no-loc(default):::`** может располагаться только внутри оператора **`:::no-loc(switch):::`** .

*`constant-expression`* В каждой **`:::no-loc(case):::`** метке преобразуется в постоянное значение, которое имеет тот же тип, что и *`condition`* . Затем он сравнивается с *`condition`* для равенства. Управление передается первой инструкции после **`:::no-loc(case):::`** *`constant-expression`* значения, совпадающего со значением *`condition`* . Поведение, полученное в результате, показано в следующей таблице.

### <a name="no-locswitch-statement-behavior"></a>`:::no-loc(switch):::`поведение инструкции

| Условие | Действие |
|--|--|
| Преобразованное значение соответствует значению выражения управления с повышенным уровнем. | Управление передается оператору, следующему за этой меткой. |
| Ни одна из констант не соответствует константам в **`:::no-loc(case):::`** метках; **`:::no-loc(default):::`** имеется метка. | Элемент управления передается в **`:::no-loc(default):::`** метку. |
| Ни одна из констант не соответствует константам в **`:::no-loc(case):::`** метках; **`:::no-loc(default):::`** Метка отсутствует. | Элемент управления передается оператору после **`:::no-loc(switch):::`** оператора. |

Если найдено совпадающее выражение, выполнение можно продолжить через более поздние **`:::no-loc(case):::`** или **`:::no-loc(default):::`** метки. [`:::no-loc(break):::`](../cpp/:::no-loc(break):::-statement-cpp.md)Оператор используется для того, чтобы прерывать выполнение и передавать управление оператору после **`:::no-loc(switch):::`** инструкции. Без **`:::no-loc(break):::`** оператора выполняется выполнение всех инструкций из соответствующей **`:::no-loc(case):::`** метки в конец **`:::no-loc(switch):::`** , включая **`:::no-loc(default):::`** . Например:

```cpp
// :::no-loc(switch):::_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, other;
   char c;
   upper:::no-loc(case):::_A = lower:::no-loc(case):::_a = other = 0;

   :::no-loc(while)::: ( c = *buffer++ )   // Walks buffer until NULL
   {
      :::no-loc(switch)::: ( c )
      {
         :::no-loc(case)::: 'A':
            upper:::no-loc(case):::_A++;
            :::no-loc(break):::;
         :::no-loc(case)::: 'a':
            lower:::no-loc(case):::_a++;
            :::no-loc(break):::;
         :::no-loc(default)::::
            other++;
      }
   }
   printf_s( "\nUpper:::no-loc(case)::: A: %d\nLower:::no-loc(case)::: a: %d\nTotal: %d\n",
      upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, (upper:::no-loc(case):::_A + lower:::no-loc(case):::_a + other) );
}
```

В приведенном выше примере `upper:::no-loc(case):::_A` увеличивается, если `c` является верхним :::no-loc(case)::: `'A'` . **`:::no-loc(break):::`** Инструкция после `upper:::no-loc(case):::_A++` завершает выполнение **`:::no-loc(switch):::`** тела оператора и управление передается в **`:::no-loc(while):::`** цикл. Без **`:::no-loc(break):::`** оператора выполнение перейдет к следующему оператору с меткой, так что `lower:::no-loc(case):::_a` и `other` будет также увеличен. Аналогичное назначение обрабатывается **`:::no-loc(break):::`** оператором для `:::no-loc(case)::: 'a'` . Если значение меньше `c` :::no-loc(case)::: `'a'` , `lower:::no-loc(case):::_a` то увеличивается и **`:::no-loc(break):::`** оператор завершает **`:::no-loc(switch):::`** тело оператора. Если `c` не является `'a'` или `'A'` , **`:::no-loc(default):::`** выполняется инструкция.

**Visual Studio 2017 и более поздние версии:** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` атрибут указан в стандарте c++ 17. Его можно использовать в **`:::no-loc(switch):::`** операторе. Это подсказка для компилятора или любой, кто читает код, это пошаговое поведение является намеренным. Компилятор Microsoft C++ в настоящее время не предупреждает о поведении fallthrough, поэтому этот атрибут не влияет на поведение компилятора. В этом примере атрибут применяется к пустой инструкции в незавершенном операторе с меткой. Иными словами, необходимо поставить точку с запятой.

```cpp
int main()
{
    int n = 5;
    :::no-loc(switch)::: (n)
    {

    :::no-loc(case)::: 1:
        a();
        :::no-loc(break):::;
    :::no-loc(case)::: 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    :::no-loc(case)::: 3:
        c();
        :::no-loc(break):::;
    :::no-loc(default)::::
        d();
        :::no-loc(break):::;
    }

    return 0;
}
```

**Visual Studio 2017 версии 15,3 и более поздних** версий (доступно в [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)). **`:::no-loc(switch):::`** Оператор может содержать *`init-statement`* предложение, которое заканчивается точкой с запятой. Он вводит и инициализирует переменную, область которой ограничена блоком **`:::no-loc(switch):::`** оператора:

```cpp
    :::no-loc(switch)::: (Gadget gadget(args); auto s = gadget.get_status())
    {
    :::no-loc(case)::: status::good:
        gadget.zip();
        :::no-loc(break):::;
    :::no-loc(case)::: status::bad:
        throw BadGadget();
    };
```

Внутренний блок **`:::no-loc(switch):::`** инструкции может содержать определения с инициализаторами, если они *достижимы*, то есть не обходятся всеми возможными путями выполнения. Имена, добавленные с помощью этих объявлений, имеют локальную область видимости. Например:

```cpp
// :::no-loc(switch):::_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    :::no-loc(switch):::( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    :::no-loc(case)::: 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        :::no-loc(break):::;

    :::no-loc(case)::: 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        :::no-loc(break):::;

    :::no-loc(default)::::
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        :::no-loc(break):::;
    }
}
```

**`:::no-loc(switch):::`** Оператор может быть вложенным. При вложении **`:::no-loc(case):::`** метки или **`:::no-loc(default):::`** связываются с ближайшим **`:::no-loc(switch):::`** оператором, в котором они заключены.

### <a name="microsoft-specific-behavior"></a>Поведение, характерное для Майкрософт

Microsoft C++ не ограничивает количество **`:::no-loc(case):::`** значений в **`:::no-loc(switch):::`** операторе. Это число ограничивается только объемом доступной памяти.

## <a name="see-also"></a>См. также статью

[Инструкции выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
