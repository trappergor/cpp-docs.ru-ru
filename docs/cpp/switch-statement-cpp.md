---
title: Оператор switch (C++)
ms.date: 05/06/2019
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 6b09c0eac939f7ca6a12b68ce5deb3fb83ad27c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160818"
---
# <a name="switch-statement-c"></a>Оператор switch (C++)

Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.

## <a name="syntax"></a>Синтаксис

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>Remarks

*Выражение* должно иметь целочисленный тип или тип класса, для которого неоднозначное преобразование в целочисленный тип. Целочисленное повышение выполняется, как описано в разделе [стандартные преобразования](standard-conversions.md).

Текст оператора **switch** состоит из ряда меток **вариантов** и необязательной метки **по умолчанию** . В операторах **case** нет двух константных выражений, которые могут иметь одно и то же значение. Метка **по умолчанию** может отображаться только один раз. Помеченные операторы не являются синтаксическими требованиями, но оператор **switch** не имеет смысла.   Оператор по умолчанию не всегда стоит в конце; он может отображаться в любой части оператора switch. Метка case или default может отображаться только внутри оператора switch.

*Константное выражение* в каждой метке **case** преобразуется в тип *выражения* и сравнивается с *выражением* для проверки на равенство. Управление передается в инструкцию, в которой *константное выражение* **case** соответствует значению *Expression*. Поведение, полученное в результате, показано в следующей таблице.

### <a name="switch-statement-behavior"></a>Поведение оператора switch

|Условие|Действие|
|---------------|------------|
|Преобразованное значение соответствует значению выражения управления с повышенным уровнем.|Управление передается оператору, следующему за этой меткой.|
|Ни одна из констант не соответствует константам в метках **case** . имеется метка **по умолчанию** .|Элемент управления передается в метку **по умолчанию** .|
|Ни одна из констант не соответствует константам в метках **case** . метка **по умолчанию** отсутствует.|Элемент управления передается в инструкцию после оператора **switch** .|

Если найдено совпадающее выражение, управление не задается последующими **вариантами** или метками **по умолчанию** . Оператор [break](../cpp/break-statement-cpp.md) используется, чтобы остановить выполнение и передавать управление оператору после оператора **switch** . Без оператора **break** выполняется выполнение всех инструкций из соответствующей метки **case** до конца **переключателя**, включая значение **по умолчанию**. Пример:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

В предыдущем примере `capa` увеличивается инкрементно, если `c` — `A` в верхнем регистре. Инструкция **break** после `capa++` завершает выполнение тела оператора **switch** и управление передается в цикл **while** . Без инструкции **break** выполнение перейдет к следующему оператору с меткой, чтобы `lettera` и `nota` также были увеличены. Аналогичное назначение обрабатывается оператором **break** для `case 'a'`. Если `c` является строчной `a`, то `lettera` увеличивается, а оператор **break** завершает тело оператора **switch** . Если `c` не является `a` или `A`, выполняется инструкция **по умолчанию** .

**Visual Studio 2017 и более поздние версии:** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)) атрибут `[[fallthrough]]` указан в стандарте c++ 17. Его можно использовать в операторе **switch** как подсказку для компилятора (или любому пользователю, читающему код), что является пошаговым поведением. Компилятор Майкрософт C++ в настоящее время не предупреждает о поведении fallthrough, поэтому этот атрибут не влияет на поведение компилятора. Обратите внимание, что атрибут применяется к пустому оператору в операторе с меткой. Иными словами, необходимо поставить точку с запятой.

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

**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно в [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): оператор switch может ввести и инициализировать переменную, область которой ограничена блоком оператора switch:

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

Внутренний блок оператора **switch** может содержать определения с инициализациями, если они достижимы, то есть не обходятся всеми возможными путями выполнения. Имена, добавленные с помощью этих объявлений, имеют локальную область видимости. Пример:

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

Оператор **switch** может быть вложенным. В таких случаях метки **case** или **Default** связываются с ближайшим оператором **switch** , который их заключает.

**Блок, относящийся только к системам Microsoft**

Microsoft C не ограничивает число значений Case в операторе **switch** . Это число ограничивается только объемом доступной памяти. ANSI C требует, чтобы в операторе **switch** было разрешено по крайней мере 257 меток case.

В Microsoft C расширения Microsoft по умолчанию включены. Чтобы отключить эти расширения, используйте параметр компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
