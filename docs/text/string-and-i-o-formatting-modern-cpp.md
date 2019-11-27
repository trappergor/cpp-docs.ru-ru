---
title: Форматирование строк и ввода-вывода (современный C++)
description: Варианты форматированной строки ввода-вывода, доступные в C++современных.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: facb0b62cc1e92ed09a9ba729d766e5db7404282
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74308189"
---
# <a name="string-and-io-formatting-modern-c"></a>Форматирование строк и ввода-вывода (современный C++)

C++[\<iostream >](../standard-library/iostream.md) классы, функции и операторы поддерживают форматированные строковые операции ввода-вывода. Например, в следующем коде показано, как задать `cout` для форматирования целого числа в шестнадцатеричном формате. Во-первых, он сохраняет текущее состояние, чтобы сбросить его впоследствии, так как после передачи состояния формата в `cout`оно остается таким образом, пока оно не изменится. Он не просто применяется к одной строке кода.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex
        << uppercase
        << setw(8)
        << setfill('0')
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

Этот подход является типобезопасным и расширяемым, но он также является сложным и подробным.

## <a name="alternative-format-options"></a>Альтернативные параметры формата

В качестве альтернативы можно использовать `Boost.Format` из библиотек Boost C++ , даже если это нестандартное. Вы можете скачать любую библиотеку Boost с веб-сайта [Boost](https://www.boost.org/) .

Некоторые преимущества `Boost.Format`:

- Безопасность: строго типизированный и вызывает исключение для ошибок, например спецификацию слишком мало или слишком много элементов.

- Расширяемый: работает для любого типа, который может быть потоковым.

- Удобно: стандартные POSIX и строки формата.

Хотя `Boost.Format` основан на C++ [\<ах > iostream](../standard-library/iostream-programming.md) , которые являются надежными и расширяемыми, они не оптимизированы для производительности. При необходимости оптимизации производительности рассмотрите возможность использования функций [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) и [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), которые быстро и просты в использовании. Однако они не являются расширяемыми и не защищены от уязвимостей. (Безопасность версий существует, но они приводят к незначительному снижению производительности. Дополнительные сведения см. в разделе [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) и [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

В следующем коде показаны некоторые функции форматирования, повышающие эффективность.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>См. также:

[Добро пожаловать обратно вC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
