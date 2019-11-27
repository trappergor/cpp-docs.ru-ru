---
title: C++файлы заголовков стандартной библиотеки
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: 807e65c69e55d8790b77a493e4ae1878aa740557
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305408"
---
# <a name="c-standard-library-header-files"></a>C++файлы заголовков стандартной библиотеки

Файлы заголовков C++ для стандартной библиотеки и расширений по категориям.

## <a name="headers-by-category"></a>Заголовки по категориям

::: moniker range=">=vs-2017"

| Категория | Заголовки |
| - | - |
| [Алгоритмы](../cpp/algorithms-modern-cpp.md) | [> алгоритма\<](algorithm.md), [\<cstdlib >](cstdlib.md), [\<numeric >](numeric.md) |
| Атомарные операции |  [\<atomic >](atomic.md)<sup>11</sup> |
| Оболочки библиотек C | [\<кассерт >](cassert.md), [\<ccomplex >](ccomplex.md)<sup>11 a b</sup>, [\<cctype >](cctype.md), [\<cerrno >](cerrno.md), [\<cfenv >](cfenv.md)<sup>11</sup>, [\<cfloat >](cfloat.md), [\<cinttypes >](cinttypes.md)<sup>11</sup>, [\<ciso646 >](ciso646.md)<sup>b</sup>,\<климитс [>](climits.md), [\<CLocale >](clocale.md), [\<cmath >](cmath.md), [\<ксетжмп >](csetjmp.md), [\<ксигнал >](csignal.md), [\<cstdalign >](cstdalign.md)<sup>11 a b</sup>, [\<кстдарг >](cstdarg.md), [\<кстдбул >](cstdbool.md)<sup>11 а b</sup>, [\<кстддеф >](cstddef.md),\<cstdint [>](cstdint.md)<sup>11</sup>, [\<cstdio](cstdio.md)>, [\<cstdlib](cstdlib.md)>, [\<CString >](cstring.md), [\<ctgmath >](ctgmath.md)<sup>11 a b</sup>, [\<CTime >](ctime.md), [\<Кучар >](cuchar.md)<sup>11</sup> , [\<cwchar >](cwchar.md), [\<cwctype >](cwctype.md) |
| Концепции | Основные понятия \<><sup>20</sup> |
| [Контейнеры](../cpp/containers-modern-cpp.md) | |
| Контейнеры последовательности | [\<массив >](array.md)<sup>11</sup>, [\<deque >](deque.md), [\<forward_list >](forward-list.md)<sup>11</sup>,\<[List >](list.md), [\<Vector >](vector.md) |
| Упорядоченные ассоциативные контейнеры| [\<map>](map.md), [\<set>](set.md) |
| Неупорядоченные ассоциативные контейнеры | [\<unordered_map >](unordered-map.md)<sup>11</sup> [\<unordered_set >](unordered-set.md)<sup>11</sup> |
| Переходники контейнеров | [\<queue>](queue.md), [\<stack>](stack.md) |
| Представления контейнеров | \<span ><sup>20</sup> |
| [Ошибки и обработка исключений](../cpp/errors-and-exception-handling-modern-cpp.md) | [\<кассерт >](cassert.md), [\<exception >](exception.md), [\<stdexcept >](stdexcept.md), [\<system_error >](system-error.md)<sup>11</sup> |
| Общие служебные программы | \<любой ><sup>17</sup>, [\<битовом массиве >](bitset.md), \<чарконв ><sup>17</sup>, [\<cstdlib >](cstdlib.md), \<выполнения ><sup>17</sup>, [\<функциональных >](functional.md), [\<памяти >](memory.md) [, \<](ratio.md)<sup>memory_resource ></sup><sup>11</sup>, \<> [\<](scoped-allocator.md)<sup>11</sup><sup>, ></sup> [кортеж\<](tuple.md)<sup>11</sup>, [\<type_traits >](type-traits.md)<sup>11</sup> [\<typeindex >](typeindex.md)<sup>11</sup>, [\<Utility](utility.md)>, \<Variant ><sup>17</sup>\< |
| [Ввод-вывод и форматирование](../text/string-and-i-o-formatting-modern-cpp.md) | [\<cinttypes >](cinttypes.md)<sup>11</sup>, [\<cstdio >](cstdio.md), [\<FileSystem](filesystem.md)><sup>17</sup>, [\<fstream >](fstream.md), [\<iomanip >](iomanip.md), [\<IOS >](ios.md), [\<иосфвд >](iosfwd.md), [\<iostream >](iostream.md),\<[IStream](istream.md)>,\<ostream [>](ostream.md), [\<sstream >](sstream.md), [\<streambuf >](streambuf.md), [\<strstream >](strstream.md)<sup>c </sup>, \<синкстреам ><sup>20</sup> |
| Итераторы | [\<iterator>](iterator.md) |
| Языковая поддержка | [\<cfloat >](cfloat.md), [\<климитс >](climits.md), [\<codecvt >](codecvt.md)<sup>11 a</sup>, \<сравнить ><sup>20</sup>, \<контракта ><sup>20</sup>, \<[ксигнал >](csignal.md)<sup>20</sup>, [\<ксетжмп >](csetjmp.md),\<, [> кстдарг\<](cstdarg.md), [> кстддеф\<](cstddef.md), [> cstdint\<](cstdint.md)<sup>11</sup>, [> cstdlib\<](cstdlib.md), [> Exception\<](exception.md) , [\<initializer_list >](initializer-list.md)<sup>11</sup>, [\<ограничения >](limits.md), [\<new >](new.md), [\<TypeInfo >](typeinfo.md), \<версии ><sup>20</sup> |
| Локализация | [\<clocale >](clocale.md), [\<codecvt >](codecvt.md)<sup>11 a</sup>, [\<CVT/вбуффер >](cvt-wbuffer.md), [\<cvt/wstring >](cvt-wstring.md),\<[языкового стандарта >](locale.md) |
| Математические и числовые значения | \<bit ><sup>20</sup>, [\<cfenv >](cfenv.md)<sup>11</sup>, [\<cmath >](cmath.md), [\<сложный >](complex.md), [\<cstdlib >](cstdlib.md), [\<ограничения >](limits.md), [\<числовой >](numeric.md), [\<случайный >](random.md)<sup>11</sup>, [отношение\<>](ratio.md)<sup>11</sup>, [\<valarray >](valarray.md) |
| [Управление памятью](../cpp/smart-pointers-modern-cpp.md) | [\<распределительы >](allocators-header.md), [\<> памяти](memory.md), \<memory_resource ><sup>17</sup>, [\<New >](new.md), [\<scoped_allocator](scoped-allocator.md)><sup>11</sup> |
| Многопоточность | [\<atomic >](atomic.md)<sup>11</sup>, [\<CONDITION_VARIABLE >](condition-variable.md)<sup>11</sup>, [\<будущие >](future.md)<sup>11</sup>, [\<мьютекс >](mutex.md)<sup>11</sup>, [\<shared_mutex >](shared-mutex.md)<sup>14</sup>, [\<Thread >](thread.md)<sup>11</sup> |
| Диапазоны | диапазоны \<><sup>20</sup> |
| Регулярные выражения | [\<regex >](regex.md)<sup>11</sup> |
| Строки и символьные данные | [\<cctype >](cctype.md), [\<cstdlib >](cstdlib.md), [\<cstring >](cstring.md), [\<Кучар >](cuchar.md)<sup>11</sup>, [\<cwchar >](cwchar.md), [\<cwctype >](cwctype.md), [\<Regex >](regex.md)<sup>11</sup>, [\<String >](string.md), [\<string_view >](string-view.md)<sup>17</sup> |
| Время | [\<chrono >](chrono.md)<sup>11</sup> [\<CTime >](ctime.md) |

<sup>11</sup> добавлена в стандарт c++ 11.
<sup>14</sup> Добавлено в стандарт c++ 14.
<sup>17</sup> добавлен в стандарт c++ 17.
<sup>20</sup> Добавлено в черновике c++ 20 Standard.
<sup>нерекомендуемый в</sup> стандарте c++ 17.
<sup>b</sup> удалено в черновике c++ 20 Standard.
в языке <sup>c</sup> не рекомендуется использовать в стандарте c++ 98.

::: moniker-end

::: moniker range="vs-2015"

|Категория|Заголовки|
|-|-|
|[Алгоритмы](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|Оболочки библиотек C|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[Контейнеры](../cpp/containers-modern-cpp.md)||
|Контейнеры последовательности|[\<массива >](array.md), [\<deque >](deque.md), [\<forward_list >](forward-list.md),\<[List >](list.md), [\<Vector >](vector.md)|
|Упорядоченные ассоциативные контейнеры| [\<map>](map.md), [\<set>](set.md)|
|Неупорядоченные ассоциативные контейнеры|[\<unordered_map >](unordered-map.md) [\<unordered_set](unordered-set.md) >|
|Контейнеры адаптера|[\<queue>](queue.md), [\<stack>](stack.md)|
|[Ошибки и обработка исключений](../cpp/errors-and-exception-handling-modern-cpp.md)|[\<> исключений](exception.md), [\<stdexcept >](stdexcept.md), [\<system_error >](system-error.md)|
|[Ввод-вывод и форматирование](../text/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|Итераторы|[\<iterator>](iterator.md)|
|Локализация|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|Математические и числовые значения|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[Управление памятью](../cpp/smart-pointers-modern-cpp.md)|[\<распределительы >](allocators-header.md), [\<> памяти](memory.md), [\<новый >](new.md)\<[scoped_allocator](scoped-allocator.md)|
|Многопоточность|[\<atomic >](atomic.md), [\<condition_variable >](condition-variable.md), [\<будущие >](future.md), [\<мьютекс >](mutex.md), [\<shared_mutex >](shared-mutex.md), [\<Thread >](thread.md)|
|Другие служебные программы|[\<битовом массиве >](bitset.md), [\<chrono >](chrono.md), [\<функциональная >](functional.md), [\<initializer_list >](initializer-list.md), [\<кортеж >](tuple.md), [\<type_traits >](type-traits.md), [\<TypeInfo >](typeinfo.md), [\<typeindex >](typeindex.md), [\<Utility](utility.md) >|
|Строки и символьные данные|[\<regex >](regex.md), [\<строки >](string.md), [\<string_view >](string-view.md)

::: moniker-end

## <a name="see-also"></a>См. также:

[Использование C++ заголовков библиотеки](using-cpp-library-headers.md)\
[C++Стандартная библиотека](cpp-standard-library-reference.md)
