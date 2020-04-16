---
title: switchвыписка (СЗ)
description: Ссылка на заявление switch «Стандарт Ная» в microsoft Visual Studio C.
ms.date: 04/15/2020
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
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 1f65d4699423d74be9c75a9be47e543a9a1256e2
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480823"
---
# <a name="opno-locswitch-statement-c"></a>switchвыписка (СЗ)

Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.

## <a name="syntax"></a>Синтаксис

> **`switch (`**\[ *инициализация* **`;`** и *выражение***`)`**\
> **`{`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**`case`***заявление* *о постоянном выражении* **`:`**\
> &nbsp;&nbsp;&nbsp;&nbsp;\[**`default :`***выписка* \
> **`}`**

## <a name="remarks"></a>Примечания

*Выражение* должно иметь интегральный тип или быть типом класса, который имеет однозначное преобразование в интегральный тип. Интегральное продвижение происходит, как описано в [стандартных конверсиях.](standard-conversions.md)

Тело **switch** оператора состоит из **case** серии этикеток и дополнительной **default** этикетки. В совокупности операторы, которые следуют за метками, называются *помеченными* операторами. Помеченные операторы не являются синтаксические **switch** требования, но заявление не имеет смысла без них. Никакие два постоянных выражения в **case** заявлениях не могут оценить одно и то же значение. Метка **default** может появиться только один раз. Заявление **default** часто помещается в конце, но оно может появиться в любом месте тела **switch** оператора. А **case** **default** или метка может **switch** отображаться только внутри оператора.

*Постоянное выражение* в **case** каждой этикетке преобразуется в тип *выражения.* Затем его сравнивает с *выражением* равенства. Управление переходит к **case** заявлению, *постоянное выражение* которого соответствует значению *выражения.* Поведение, полученное в результате, показано в следующей таблице.

### <a name="switch-statement-behavior"></a>Поведение оператора переключателя

| Условие | Действие |
|--|--|
| Преобразованное значение соответствует значению выражения управления с повышенным уровнем. | Управление передается оператору, следующему за этой меткой. |
| Ни одна из констант **case** не соответствует константам на этикетках; этикетка **default** присутствует. | Управление передается **default** на этикетку. |
| Ни одна из констант **case** не соответствует константам на этикетках; нет **default** этикетки присутствует. | Контроль передается в выписку **switch** после заявления. |

При обнаружении соответствующего выражения выполнение **case** может **default** продолжаться позже или по этикеткам. Заявление [`break`](../cpp/break-statement-cpp.md) используется для остановки выполнения и передачи **switch** контроля в выписку после заявления. Без **break** оператора выполняется каждая **case** выписка от **switch** соответствующей **default** метки до конца, включая , Пример:

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

В предыдущем примере `uppercase_A` увеличивается инкрементно, если `c` — `'A'` в верхнем регистре. Заявление **break** после `uppercase_A++` прекращения выполнения **switch** тела оператора и управление **while** переходит к циклу. Без **break** этого заявления исполнение "пропадает" до следующего помеченного оператора, так что `lowercase_a` и `other` будет также приравлечено. Аналогичная цель служит **break** заявление `case 'a'`для . Если `c` нижний `'a'`регистр, `lowercase_a` приращен и **break** заявление завершает **switch** тело оператора. Если `c` это не `'a'` `'A'`является **default** или, заявление выполняется.

**Визуальная студия 2017 и позже:** (доступно с `[[fallthrough]]` [/std:c'17](../build/reference/std-specify-language-standard-version.md)) Атрибут указан в стандарте C-17. Вы можете использовать **switch** его в заявлении. Это намек на компилятор, или любой, кто читает код, что падение через поведение является преднамеренным. В настоящее время компилятор Microsoft C's не предупреждает о поведении попадающих сторон, поэтому этот атрибут не влияет на поведение компилятора. В примере атрибут применяется к пустому сообщению в неопределенных обозначенных операторах. Другими словами, запятая необходима.

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

**Visual Studio 2017 версия 15.3 и позже** (доступна с [/std: c-17](../build/reference/std-specify-language-standard-version.md)). Заявление switch может иметь оговорку *о инициализации.* Он вводит и инициализирует переменную, область switch действия которой ограничена блоком оператора:

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

Внутренний блок **switch** оператора может содержать определения с инициализацией до тех пор, пока они *доступны,* то есть не обходят стороной все возможные пути выполнения. Имена, добавленные с помощью этих объявлений, имеют локальную область видимости. Пример:

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

Заявление **switch** может быть вложено. При вложении **case** **default** или метки ассоциируются с ближайшим **switch** утверждением, которое их примыкает.

### <a name="microsoft-specific-behavior"></a>Поведение, конкретное майкрософт

Microsoft C не ограничивает количество **case** значений **switch** в выписке. Это число ограничивается только объемом доступной памяти. ANSI C требует, чтобы **case** в **switch** заявлении было разрешено не менее 257 меток.

Microsoft default C заключается в том, что расширения Майкрософт включены. Для того чтобы отключить эти расширения, используйте опцию компилятора [/Qq.](../build/reference/za-ze-disable-language-extensions.md)

## <a name="see-also"></a>См. также

[Инструкции выбора](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
