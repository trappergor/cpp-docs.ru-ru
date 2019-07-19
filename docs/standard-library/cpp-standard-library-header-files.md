---
title: C++файлы заголовков стандартной библиотеки
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: dc337ef078108d86849aa7b7452512dfb69e6e18
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341122"
---
# <a name="c-standard-library-header-files"></a>C++файлы заголовков стандартной библиотеки

Файлы заголовков C++ для стандартной библиотеки и расширений по категориям.

## <a name="headers-by-category"></a>Заголовки по категориям

::: moniker range=">=vs-2017"

| Категория | Заголовки |
| - | - |
| [Алгоритмы](../cpp/algorithms-modern-cpp.md) | > алгоритмов [ ,\<> cstdlib](cstdlib.md), [ \<числовые >](numeric.md) [ \<](algorithm.md) |
| Атомарные операции |  Атомарная ><sup>11</sup> [ \<](atomic.md) |
| Оболочки библиотек C | [ \<](cfenv.md)<sup></sup> [ \<](cerrno.md) [ \<кассерт >](cctype.md), [ccomplex > 11 a b, cctype >, cerrno >, cfenv > 11, \<](ccomplex.md) [ \<](cassert.md)<sup></sup> [ \<cfloat >](cfloat.md),<sup></sup> [ \<cinttypes >](cinttypes.md)11, [ \<ciso646 >](ciso646.md)<sup>b</sup>, [ \<климитс >](climits.md), [ \<CLocale >](clocale.md) [ cmath\<>](cmath.md), [ ксетжмп>,ксигнал>,cstdalign>11ab,кстдарг>\<](csetjmp.md) [ \<](cstdarg.md) [ \<](csignal.md) [ \<](cstdalign.md)<sup></sup> [ \<кстдбул >](cstdbool.md)<sup>11 a b</sup>, [ \<кстддеф >](cstddef.md), [ \<cstdint >](cstdint.md)<sup>11</sup>, [ \<cstdio >](cstdio.md), [ \<cstdlib >](cstdlib.md) [ CString\<>](cstring.md),<sup></sup> [ \<](ctime.md)<sup></sup> [ \<](cuchar.md) [ \<](cwchar.md) [ ctgmath>11\<](ctgmath.md)a b, CTime >, Кучар > 11, cwchar > [ cwctype\<>](cwctype.md) |
| Основные понятия | \<Основные понятия ><sup>20</sup> |
| [Контейнеры](../cpp/containers-modern-cpp.md) | |
| Контейнеры последовательности | <sup></sup><sup></sup> [ array\<>](array.md)11, [ deque>,forward_list>11,>списка,Vector>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md) |
| Упорядоченные ассоциативные контейнеры| [\<map>](map.md), [\<set>](set.md) |
| Неупорядоченные ассоциативные контейнеры | unordered_map ><sup>11</sup>, [ unordered_set>\<](unordered-set.md)<sup>11</sup> [ \<](unordered-map.md) |
| Переходники контейнеров | [\<queue>](queue.md), [\<stack>](stack.md) |
| Представления контейнеров | \<диапазон ><sup>20</sup> |
| [Ошибки и обработка исключений](../cpp/errors-and-exception-handling-modern-cpp.md) | <sup></sup> [ кассерт\<>](cassert.md) [, >\<исключений](exception.md) [, stdexcept\<>](stdexcept.md) [, system_error\<>](system-error.md)11 |
| Общие служебные программы | \<любой ><sup>17</sup>, [ \<битовом массиве >](bitset.md), \<чарконв ><sup>17</sup>, [ \<cstdlib >](cstdlib.md), \<выполнение ><sup>17</sup>, [ \<функциональный >](functional.md) [ >\<памяти](memory.md), \< [ \<](ratio.md)<sup></sup><sup></sup><sup></sup>memory_resource > 17, необязательно > 17, соотношение > 11, scoped_allocator > \< [ \< ](scoped-allocator.md) <sup>11</sup>,<sup></sup><sup></sup><sup></sup> [ кортеж\<>](tuple.md)11 [, type_traits>11,typeindex>11,служебная>,\<](type-traits.md) [ \<](typeindex.md) [ \<](utility.md) \<вариант ><sup>17</sup> |
| [Ввод-вывод и форматирование](../cpp/string-and-i-o-formatting-modern-cpp.md) | <sup></sup><sup></sup> [ cinttypes\<>](cinttypes.md)11, [ cstdio>,FileSystem>17,FStream>,iomanip>\<](cstdio.md) [ \<](filesystem.md) [ \<](fstream.md) [ \<](iomanip.md) [ iOS\<>](ios.md) [, > иосфвд,iostream>,IStream>,ostream>,sstream>\<](iosfwd.md) [ \<](iostream.md) [ \<](istream.md) [ \<](ostream.md) [ \<](sstream.md) \< [ ,\<streambuf >](streambuf.md) [ ,\<strstream >](strstream.md)<sup>c</sup>, синкстреам ><sup>20</sup> |
| Итераторы | [\<iterator>](iterator.md) |
| Языковая поддержка | \< \< \< <sup></sup><sup></sup><sup></sup> [ cfloat\<>](cfloat.md) [, климитс\<>](climits.md) [, codecvt\<>](codecvt.md)11 a, сравнение > 20, контракт > 20, соподпрограмма ><sup>20</sup>, [ \<ксетжмп >](csetjmp.md), [ \<ксигнал >](csignal.md), [ \<кстдарг >](cstdarg.md), [ \<кстддеф >](cstddef.md), [ \<cstdint > ](cstdint.md) <sup>11</sup><sup></sup> [, cstdlib\<>](cstdlib.md) [, Exception\<>](exception.md) [, initializer_list\<>](initializer-list.md)11 [, ограничения>,\<](limits.md) [ \< новые >](new.md), [ \<TypeInfo >](typeinfo.md), \<Version ><sup>20</sup> |
| Локализация | [ \<](locale.md) <sup></sup> [ CLocale>\<](cvt-wbuffer.md), [codecvt > 11 a, CVT/вбуффер >, CVT/wstring >, языковой стандарт > \<](codecvt.md) [ \<](cvt-wstring.md) [ \<](clocale.md) |
| Математические и числовые значения | \<бит ><sup>20</sup>, [ \<cfenv >](cfenv.md)<sup>11</sup>, [ \<cmath >](cmath.md), [ \<сложные >](complex.md), [ \<cstdlib >](cstdlib.md), [ \<ограничения >](limits.md) [ \<числовой >](numeric.md) [ ,\<случайный >](random.md)<sup>11</sup>, [ \<соотношение >](ratio.md)<sup>11</sup>, [ \<valarray >](valarray.md) |
| [Управление памятью](../cpp/smart-pointers-modern-cpp.md) | \< [ \<](new.md) [ \<](scoped-allocator.md)<sup></sup><sup></sup> [ \<](memory.md)распределительы >, > памяти, memory_resource > 17, New >, scoped_allocator > 11 [ \<](allocators-header.md) |
| Многопоточность | <sup></sup><sup></sup><sup></sup><sup></sup> [ \<](condition-variable.md) [ \<](future.md) [ \<атомарная](mutex.md)> 11, CONDITION_VARIABLE > 11, будущее > 11, мьютекс > 11 [ \<](atomic.md) [ \< shared_mutex >](shared-mutex.md)<sup>14</sup>, [ \<поток >](thread.md)<sup>11</sup> |
| Диапазоны | \<диапазоны ><sup>20</sup> |
| Регулярные выражения | регулярное<sup></sup> выражение [ \<>](regex.md)11 |
| Строки и символьные данные | <sup></sup> [ cctype\<>](cctype.md), [ cstdlib>,CString>,Кучар>11,cwchar>,cwctype\<](cstdlib.md) [ \<](cstring.md) [ \<](cuchar.md) [ \<](cwchar.md) [ \< >](cwctype.md) [ ,\<Regex >](regex.md)<sup>11</sup>, [ \<String >](string.md), [ \<string_view >](string-view.md)<sup>17</sup> |
| Time | Chrono ><sup>11</sup>, [ CTime\<>](ctime.md) [ \<](chrono.md) |

<sup>11</sup> добавлена в стандарт c++ 11.
<sup>14</sup> Добавлено в стандарт c++ 14.
<sup>17</sup> добавлен в стандарт c++ 17.
<sup>20</sup> Добавлено в черновике c++ 20 Standard.
<sup>нерекомендуемый</sup> в стандарте c++ 17.
<sup>b</sup> удалено в черновике c++ 20 Standard.
в языке <sup>c</sup> не рекомендуется использовать в стандарте c++ 98.

::: moniker-end

::: moniker range="vs-2015"

|Категория|Заголовки|
|-|-|
|[Алгоритмы](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|Оболочки библиотек C|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[Контейнеры](../cpp/containers-modern-cpp.md)||
|Контейнеры последовательности|[ >\<массива](array.md), [ >deque,forward_list>,List>,Vector>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md)|
|Упорядоченные ассоциативные контейнеры| [\<map>](map.md), [\<set>](set.md)|
|Неупорядоченные ассоциативные контейнеры|> unordered_map, [ \<](unordered-map.md) [ unordered_set>\<](unordered-set.md)|
|Контейнеры адаптера|[\<queue>](queue.md), [\<stack>](stack.md)|
|[Ошибки и обработка исключений](../cpp/errors-and-exception-handling-modern-cpp.md)|> исключений [, stdexcept>\<](stdexcept.md), [ system_error\<>](system-error.md) [ \<](exception.md)|
|[Ввод-вывод и форматирование](../cpp/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|Итераторы|[\<iterator>](iterator.md)|
|Локализация|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|Математические и числовые значения|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[Управление памятью](../cpp/smart-pointers-modern-cpp.md)|распределительы >, [ \<> памяти](memory.md), [ \<New >](new.md), [ \<scoped_allocator >](scoped-allocator.md) [ \<](allocators-header.md)|
|Многопоточность|[ \<](mutex.md) [ \<](shared-mutex.md)атомарные > [ ,\<> CONDITION_VARIABLE](condition-variable.md), [ \<будущие >](future.md), мьютекс >, shared_mutex >, Thread [ \<](atomic.md) [ \< >](thread.md)|
|Другие служебные программы|[ битовоммассиве\<>](bitset.md), [ Chrono>,функциональные>,>initializer_list,кортеж>,type_traits\<](chrono.md) [ \<](functional.md) [ \<](initializer-list.md) [ \<](tuple.md) [ \< >](type-traits.md) [ ,\<TypeInfo >](typeinfo.md), [ \<typeindex >](typeindex.md), [ \<служебная >](utility.md)|
|Строки и символьные данные|регулярное выражение [ \<>, String >](string.md), [ \<string_view >](string-view.md) [ \<](regex.md)

::: moniker-end

## <a name="see-also"></a>См. также

[Использование C++ заголовков библиотек](using-cpp-library-headers.md)\
[C++Стандартная библиотека](cpp-standard-library-reference.md)
