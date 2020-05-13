---
title: Форматирование строк и ввода-вывода (современный C++)
description: Выбор форматированных строк ВВ/О доступен в современном СЗ.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: a3fc93b0baf414759eb50c787c4057fb85dcb370
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375774"
---
# <a name="string-and-io-formatting-modern-c"></a>Форматирование строк и ввода-вывода (современный C++)

>классов, функций и операторов поддержки отформатированных строк вв/осек. [ \<](../standard-library/iostream.md) Например, в следующем коде `cout` показано, как установить для форматирования рядового вывода в гексадецималь. Во-первых, это экономит текущее состояние, чтобы сбросить его `cout`потом, потому что как только состояние формата передается, он остается таким образом, пока не изменится. Это относится не только к одной строке кода.

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

Этот подход является типобезопасным и расширяемым, но он также является сложным и многословным.

## <a name="alternative-format-options"></a>Альтернативные варианты формата

В качестве альтернативы можно `Boost.Format` использовать библиотеки Boost C, даже если это нестандартно. Вы можете скачать любую библиотеку Boost с веб-сайта [Boost.](https://www.boost.org/)

Некоторые `Boost.Format` преимущества:

- Безопасный: Тип-безопасный, и бросает исключение для ошибок, например, спецификация слишком мало или слишком много элементов.

- Расширяемый: Работает для любого типа, который может передаваться.

- Удобно: Стандартный POSIX и аналогичные строки формата.

Несмотря `Boost.Format` на то, [ \<](../standard-library/iostream-programming.md) что она построена на>объектов, которые являются безопасными и расширяемыми, они не оптимизированы для повышения производительности. Если требуется оптимизация производительности, рассмотрим C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) и [sprintf,](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)которые быстро и просты в использовании. Тем не менее, они не расширяемы или защищены от уязвимостей. (Безопасные версии существуют, но они несут небольшое наказание производительности. Для получения дополнительной информации [см. printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) и [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l).](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)

Следующий код демонстрирует некоторые функции форматирования Boost.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>См. также раздел

[Добро пожаловать обратно в СЗ](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Языковая справка к СЗ](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека СЗ](../standard-library/cpp-standard-library-reference.md)<br/>
[\<>йострим](../standard-library/iostream.md)<br/>
[\<ограничения>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
