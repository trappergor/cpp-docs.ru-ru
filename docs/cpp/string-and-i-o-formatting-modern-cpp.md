---
title: Строки и вводом выводом форматирование (современный C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 391648d71fa3d38a0f704a014c163b7f8b102e40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422388"
---
# <a name="string-and-io-formatting-modern-c"></a>Форматирование строк и ввода-вывода (современный C++)
C++ [iostreams](../standard-library/iostream.md) способны форматированную строку ввода-вывода. Например ниже демонстрируется задание cout для форматирования целое число для вывода в шестнадцатеричном формате, сначала сохранить текущее состояние off и повторно параметру после этого, так как после форматирования состояния передается cout, он остается таким образом, пока не будут изменены, а не только для одной строки из кода.  
  
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
  
 Это может быть полностью слишком громоздким, во многих случаях. В качестве альтернативы можно использовать Boost.Format из библиотек Boost C++, несмотря на то, что он является нестандартным. Можно загрузить любой библиотеки Boost из [повышение](http://www.boost.org/) веб-сайта.  
  
 Ниже приведены некоторые преимущества Boost.Format.  
  
-   Safe: Строго типизированным и создает исключение для ошибок, например, спецификация слишком мало или слишком много элементов.  
  
-   Расширяемый: Работает для любого типа, который может передаваться.  
  
-   Удобство: Стандартные Posix и аналогичные строки формата.  
  
 Несмотря на то, что Boost.Format основана на C++ [iostreams](../standard-library/iostream-programming.md), относящихся к надежным и расширяемые, они не являются оптимизации производительности. Когда потребуется, чтобы оптимизировать производительность, рассмотрите возможность C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) и [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), которые являются быстрый и простой в использовании. Тем не менее они не являются расширяемой или от уязвимостей. (Существует безопасные версии, но они создают небольшое уменьшение производительности. Дополнительные сведения см. в разделе [printf_s _printf_s_l, wprintf_s _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) и [sprintf_s _sprintf_s_l, swprintf_s _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).  
  
 В следующем коде показано некоторые возможности форматирования повышение.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## <a name="see-also"></a>См. также  
 [Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)   
 [\<iostream >](../standard-library/iostream.md)   
 [\<ограничения >](../standard-library/limits.md)   
 [\<iomanip>](../standard-library/iomanip.md)
