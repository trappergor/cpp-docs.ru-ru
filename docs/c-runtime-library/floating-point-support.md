---
title: Поддержка математических функций для чисел с плавающей запятой
ms.date: 01/31/2019
f1_keywords:
- c.math
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
ms.openlocfilehash: a0ee21378a6feb7ada39dc00f0e181672470e231
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821516"
---
# <a name="math-and-floating-point-support"></a>Поддержка математических функций для чисел с плавающей запятой

Универсальная библиотека среды выполнения C (UCRT) предоставляет множество математических функций с плавающей точкой, включая все функции, предусмотренные ISO C99. Функции с плавающей запятой предназначены для балансировки производительности и правильности. Так как получение правильно округленного результата может оказаться неоправданно дорогим, эти функции позволяют получить значение, максимально приближенное к правильно округленному результату. В большинстве случаев результат будет соответствовать правильно округленному значению +/–1 ULP, хотя в некоторых случаях погрешность может быть выше.

Во многих функциях математической библиотеки с плавающей точкой используются различные реализации разной архитектуры ЦП. Например, в 32-разрядных CRT x86 могут использоваться не такие реализации, как в 64-разрядных CRT x64. Кроме того, некоторые функции могут содержать сразу несколько реализаций заданной архитектуры ЦП. Наиболее эффективная реализация выбирается в среде выполнения динамически в зависимости от того, какие наборы инструкций поддерживает ЦП. Например, в 32-разрядных CRT x86 некоторые функции включают сразу две реализации — x87 и SSE2. При работе на ЦП, который поддерживает SSE2, используется более быстрая реализация SSE2. При работе на ЦП, который не поддерживает SSE2, используется более медленная реализация x87. Так как различные реализации функций математической библиотеки могут использовать для получения результатов различные инструкции ЦП и разнообразные алгоритмы, эти функции могут давать различные результаты на разных ЦП. В большинстве случаев результаты находятся в пределах +/–1 ULP от правильно округленного результата, но фактические результаты могут отличаться в зависимости от ЦП.

В предыдущих 16-разрядных версиях Microsoft C/C++ и Microsoft Visual C++ тип **long double** поддерживался как тип данных с плавающей точкой 80-битной точности. В более поздних версиях Visual C++ тип данных **long double** представляет собой тип данных с плавающей запятой 64-битной точности, идентичный типу **double**. Компилятор трактует типы **long double** и **double** как разные типы, но функции для типа **long double** идентичны соответствующим функциям для типа **double**. Для обеспечения совместимости с исходным кодом ISO C99 в библиотеке CRT предоставляются версии математических функций для типа **long double**, но следует иметь в виду, что двоичное представление этих функций может быть не таким, как в других компиляторах.

## <a name="supported-math-and-floating-point-routines"></a>Поддерживаемые математические функции для чисел с плавающей запятой

|Подпрограмма|Использование|
|-|-|
[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Вычисляет абсолютное значение целого числа
[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Вычисляет арккосинус
[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|Вычисляет гиперболический арккосинус
[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Вычисляет арксинус
[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|Вычисляет гиперболический арксинус
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Вычисляет арктангенс
[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|Вычисляет гиперболический арктангенс
[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Преобразует строку, определяемую языковым стандартом, в тип **double**
[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразует строку в тип **double**
[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Преобразует строку, определяемую языковым стандартом, в тип **float** или **long double**
[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Вычисляет кубический корень
[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Вычисляет с округлением вверх
[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Вычисляет аддитивную инверсию
[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Получает и сбрасывает реестр состояния блока операций с плавающей запятой
[_control87, \__control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|Получает и задает управляющее слово блока операций с плавающей запятой
[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|Безопасная версия **_controlfp**
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Возвращает значение, которое имеет абсолютное значение одного аргумента и знак другого
[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Вычисляет синус
[cosh, coshf, coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Вычисляет гиперболический синус
[div, ldiv, lldiv](../c-runtime-library/reference/div.md)|Вычисляет частное и остаток от деления двух целочисленных значений
[_ecvt](../c-runtime-library/reference/ecvt.md), [ecvt](../c-runtime-library/reference/posix-ecvt.md)|Преобразует тип **double** в строку
[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Безопасная версия **_ecvt**
[erf, erff, erfl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Вычисляет функцию ошибок
[erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Вычисляет дополнительную функцию ошибок
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)|Вычисляет экспоненту *e*<sup>x</sup>
[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)|Вычисляет экспоненту 2<sup>x</sup>
[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)|Вычисляет *e*<sup>x</sup>-1
[fabs, fabsf, fabsl](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Вычисляет абсолютное значение типа с плавающей запятой
[_fcvt](../c-runtime-library/reference/fcvt.md), [fcvt](../c-runtime-library/reference/posix-fcvt.md)|Преобразует число с плавающей запятой в строку
[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Безопасная версия **_fcvt**.
[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)|Определяет положительную разность между двумя значениями
[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)|Сбрасывает указанные исключения с плавающей запятой
[fegetenv](../c-runtime-library/reference/fegetenv1.md)|Хранит текущую среду с плавающей запятой
[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)|Получает состояние указанных исключений с плавающей запятой
[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Получает режим округления чисел с плавающей запятой
[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)|Задает безостановочный режим исключений с плавающей запятой
[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)|Вызывает указанные исключения с плавающей запятой
[fesetenv](../c-runtime-library/reference/fesetenv1.md)|Задает текущую среду с плавающей запятой
[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)|Задает флаги состояния указанных чисел с плавающей запятой
[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Задает режим округления указанных чисел с плавающей запятой
[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)|Определяет, какие флаги состояния исключения с плавающей запятой заданы
[feupdateenv](../c-runtime-library/reference/feupdateenv.md)|Восстанавливает среду с плавающей запятой, а затем вызывает предыдущее исключение
[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Вычисляет с округлением вниз
[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)|Вычисляет склеенную операцию умножения-сложения
[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)|Вычисляет максимальное значение аргументов
[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)|Вычисление минимума аргументов
[fmod, fmodf, fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Вычисляет остаток с плавающей запятой
[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)|Возвращает классификацию значения с плавающей запятой
[fpclassify](../c-runtime-library/reference/fpclassify.md)|Возвращает классификацию значения с плавающей запятой
[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|Задает обработчик исключений с плавающей запятой
[_fpreset](../c-runtime-library/reference/fpreset.md)|Сбрасывает среду с плавающей запятой
[frexp, frexpf, frexpl](../c-runtime-library/reference/frexp.md)|Получает мантиссу и показатель степени числа с плавающей запятой
[_gcvt](../c-runtime-library/reference/gcvt.md), [gcvt](../c-runtime-library/reference/posix-gcvt.md)|Преобразует число с плавающей запятой в строку
[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Безопасная версия **_gcvt**
[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)|Получает или задает флаг для использования инструкций FMA3 в 64-разрядной среде
[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Вычисляет гипотенузу
[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)|Вычисляет показатель степени целого числа по основанию 2
[imaxabs](../c-runtime-library/reference/imaxabs.md)|Вычисляет абсолютное значение целого числа
[imaxdiv](../c-runtime-library/reference/imaxdiv.md)|Вычисляет частное и остаток от деления двух целочисленных значений
[isfinite, _finite, _finitef](../c-runtime-library/reference/finite-finitef.md)|Определяет, является ли значение конечным
[isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered](../c-runtime-library/reference/floating-point-ordering.md)|Сравнивает порядок двух значений с плавающей запятой
[isinf](../c-runtime-library/reference/isinf.md)|Определяет, является ли значение с плавающей запятой бесконечным
[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Проверяет значение с плавающей запятой для NaN
[isnormal](../c-runtime-library/reference/isnormal.md)|Проверяет, является ли значение с плавающей запятой конечным и не субнормальным
[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Вычисляет функцию Бесселя
[ldexp, ldexpf, ldexpl](../c-runtime-library/reference/ldexp.md)|Вычисляет x*2<sup>n</sup>
[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)|Вычисляет натуральный логарифм абсолютного значения гамма-функции
[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Округляет значение с плавающей запятой до ближайшего значения **long long**.
[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Округляет значение с плавающей запятой до ближайшего значения **long long**.
[log, logf, logl, log10, log10f, log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Вычисляет натуральный логарифма или логарифм по основанию 10
[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)|Вычисляет натуральный логарифм числа 1+x
[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)|Вычисляет логарифм по основанию 2
[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Возвращает показатель степени значения с плавающей запятой
[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Округляет значение с плавающей запятой до ближайшего значения **long**
[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Чередует целочисленное значение влево или вправо
[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Округляет значение с плавающей запятой до ближайшего значения **long**
[_matherr](../c-runtime-library/reference/matherr.md)|Обработчик математических ошибок по умолчанию
[__max](../c-runtime-library/reference/max.md)|Макрос, который возвращает большее из двух значений
[__min](../c-runtime-library/reference/min.md)|Макрос, который возвращает меньшее из двух значений
[modf, modff, modfl](../c-runtime-library/reference/modf-modff-modfl.md)|Разбивает значение с плавающей запятой на дробную и целую части
[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Возвращает несигнальное значение NaN (QNaN)
[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)|Возвращает округленное значение
[nextafter, nextafterf, nextafterl, _nextafter, _nextafterf](../c-runtime-library/reference/nextafter-functions.md)|Возвращает следующее представимое значение с плавающей запятой
[nexttoward, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)|Возвращает следующее представимое значение с плавающей запятой
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)|Возвращает значение *x*<sup>*y*</sup>
[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)|Вычисляет остаток от частного двух значений с плавающей запятой
[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)|Вычисляет остаток от деления двух целочисленных значений
[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Округляет значение с плавающей запятой
[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Чередует биты в целочисленных типах
[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)|Округляет значение с плавающей запятой
[_scalb, _scalbf](../c-runtime-library/reference/scalb.md)|Масштабирует аргумент по степени числа 2
[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Умножает число с плавающей запятой на целую степень числа **FLT_RADIX**
[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)|Задает управляющее слово блока операций с плавающей запятой
[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)|Включает или отключает инструкции SSE2
[signbit](../c-runtime-library/reference/signbit.md)|Проверяет знаковый бит значения с плавающей запятой
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Вычисляет синус
[sinh, sinhf, sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Вычисляет гиперболический синус
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Вычисляет квадратный корень
[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Получает слово состояния модуля операций с плавающей запятой
[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)|Преобразуют строку в тип **float**
[strtold, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)|Преобразует строку в **длинное** **Двойное** значение
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Вычисляет тангенс
[tanh, tanhf, tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Вычисляет гиперболический тангенс
[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)|Вычисляет гамма-функцию
[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)|Усекает дробную часть
[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразует двухбайтовую строку в **double**
[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Вычисляет функцию Бесселя

## <a name="see-also"></a>См. также:

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Примитивы с плавающей запятой](../c-runtime-library/reference/floating-point-primitives.md)<br/>
