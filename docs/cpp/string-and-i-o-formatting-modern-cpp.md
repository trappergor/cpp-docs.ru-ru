---
title: Строка и ввод вывод форматирование (современный C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: 816eb71dae011f853a6e7ade1a1a2a8144a457c5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326190"
---
# <a name="string-and-io-formatting-modern-c"></a>Форматирование строк и ввода-вывода (современный C++)

C++ [iostreams](../standard-library/iostream.md) способны форматированную строку ввода-вывода. Например приведенный ниже показано, как задать cout для форматирования целого числа для вывода в шестнадцатеричном формате, сначала сохранив отключенное текущее состояние и затем перезадав его, так как после форматирование состояния передано для cout, оно остается таким образом, пока не будет изменено, не только для одной строки кода.

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

Это может быть слишком громоздким во многих случаях. Кроме того можно использовать Boost.Format из библиотек Boost C++, несмотря на то, что он является нестандартным. Вы можете скачать Любая библиотека поддержки из [Boost](http://www.boost.org/) веб-сайта.

Ниже приведены некоторые преимущества Boost.Format:

- Безопасность: Типобезопасный и создает исключение для ошибок, например, спецификация слишком мало или слишком много элементов.

- Расширяемый: Работает для любого типа, который может передаваться.

- Удобство: Стандартный Posix и подобные строки формата.

Хотя Boost.Format основывается на C++ [iostreams](../standard-library/iostream-programming.md), которые являются безопасными и расширяемыми, они не оптимизированная. При необходимости оптимизации производительности, необходимо учитывать C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) и [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), которые быстро и легко в использовании. Тем не менее они не являются расширяемыми или безопасными от уязвимостей. (Безопасные версии существуют, но они подлежат небольшое уменьшение производительности. Дополнительные сведения см. в разделе [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) и [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

Следующий код демонстрирует некоторые из функций поддержки форматирования.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)