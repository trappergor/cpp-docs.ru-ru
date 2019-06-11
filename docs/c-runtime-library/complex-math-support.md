---
title: Поддержка операций с комплексными числами в C
ms.date: 05/14/2019
f1_keywords:
- c.complex
helpviewer_keywords:
- complex numbers, math routines
- math routines
- complex numbers
ms.openlocfilehash: 493886fcf1dbfd3dc16487dd8650206c428bb06d
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "66186095"
---
# <a name="c-complex-math-support"></a>Поддержка операций с комплексными числами в C

Библиотека среды выполнения Microsoft C (CRT) предоставляет функции библиотеки для работы с комплексными числами, включая все функции, предусмотренные стандартом ISO C99. Компилятор не поддерживает ключевое слово **complex** или **_Complex** напрямую, поэтому в реализации Майкрософт для представления комплексных чисел используются типы-структуры.

Эти функции предназначены для балансировки производительности и правильности. Так как получение правильно округленного результата может оказаться неоправданно дорогим, эти функции позволяют получить значение, максимально приближенное к правильно округленному результату. В большинстве случаев результат будет соответствовать правильно округленному значению +/–1 ULP, хотя в некоторых случаях погрешность может быть выше.

В основе процедур для работы с комплексными числами лежат функции библиотеки математических операций для обработки чисел с плавающей запятой. Эти функции имеют различные реализации для различных архитектур ЦП. Например, в 32-разрядных CRT x86 могут использоваться не такие реализации, как в 64-разрядных CRT x64. Кроме того, некоторые функции могут содержать сразу несколько реализаций заданной архитектуры ЦП. Наиболее эффективная реализация выбирается в среде выполнения динамически в зависимости от того, какие наборы инструкций поддерживает ЦП. Например, в 32-разрядных CRT x86 некоторые функции включают сразу две реализации — x87 и SSE2. При работе на ЦП, который поддерживает SSE2, используется более быстрая реализация SSE2. При работе на ЦП, который не поддерживает SSE2, используется более медленная реализация x87. Так как различные реализации функций математической библиотеки могут использовать для получения результатов различные инструкции ЦП и разнообразные алгоритмы, эти функции могут давать различные результаты на разных ЦП. В большинстве случаев результаты находятся в пределах +/–1 ULP от правильно округленного результата, но фактические результаты могут отличаться в зависимости от ЦП.

## <a name="types-used-in-complex-math"></a>Типы, используемые в операциях с комплексными числами

В реализованном Майкрософт файле заголовка complex.h в качестве эквивалентов для стандартных встроенных типов для работы с комплексными числами C99 определены следующие типы.

|Стандартный тип|Тип Майкрософт|
|-|-|
|**float complex** или **float _Complex**|**_Fcomplex**|
|**double complex** или **double _Complex**|**_Dcomplex**|
|**long double complex** или **long double _Complex**|**_Lcomplex**|

В файле заголовка math.h определен отдельный тип **struct _complex**, используемый для функции [_cabs](../c-runtime-library/reference/cabs.md). Тип **struct _complex** не используется в эквивалентных функциях для работы с комплексными числами [cabs, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md).

## <a name="complex-constants-and-macros"></a>Комплексные константы и макросы

**I** определяется в качестве комплексного типа **_Fcomplex** (для типа **float**), который инициализируется `{ 0.0f, 1.0f }`.

## <a name="trigonometric-functions"></a>Тригонометрические функции

|Функция|Описание|
|-|-|
|[cacos, cacosf, cacosl](../c-runtime-library/reference/cacos-cacosf-cacosl.md)|Вычисляет комплексный арккосинус комплексного числа|
|[casin, casinf, casinl](../c-runtime-library/reference/casin-casinf-casinl.md)|Вычисляет комплексный арксинус комплексного числа|
|[catan, catanf, catanl](../c-runtime-library/reference/catan-catanf-catanl.md)|Вычисляет комплексный арктангенс комплексного числа|
|[ccos, ccosf, ccosl](../c-runtime-library/reference/ccos-ccosf-ccosl.md)|Вычисляет комплексный косинус комплексного числа|
|[csin, csinf, csinl](../c-runtime-library/reference/csin-csinf-csinl.md)|Вычисляет комплексный синус комплексного числа|
|[ctan, ctanf, ctanl](../c-runtime-library/reference/ctan-ctanf-ctanl.md)|Вычисляет комплексный тангенс комплексного числа|

## <a name="hyperbolic-functions"></a>Гиперболические функции

|Функция|Описание|
|-|-|
|[cacosh, cacoshf, cacoshl](../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)|Вычисляет комплексный гиперболический арккосинус комплексного числа|
|[casinh, casinhf, casinhl](../c-runtime-library/reference/casinh-casinhf-casinhl.md)|Вычисляет комплексный гиперболический арксинус комплексного числа|
|[catanh, catanhf, catanhl](../c-runtime-library/reference/catanh-catanhf-catanhl.md)|Вычисляет комплексный гиперболический арктангенс комплексного числа|
|[ccosh, ccoshf, ccoshl](../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)|Вычисляет комплексный гиперболический косинус комплексного числа|
|[csinh, csinhf, csinhl](../c-runtime-library/reference/csinh-csinhf-csinhl.md)|Вычисляет комплексный гиперболический синус комплексного числа|
|[ctanh, ctanhf, ctanhl](../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)|Вычисляет комплексный гиперболический тангенс комплексного числа|

## <a name="exponential-and-logarithmic-functions"></a>Экспоненциальные и логарифмические функции

|Функция|Описание|
|-|-|
|[cexp, cexpf, cexpl](../c-runtime-library/reference/cexp-cexpf-cexpl.md)|Вычисляет комплексную экспоненту комплексного числа с основанием *e*|
|[clog, clogf, clogl](../c-runtime-library/reference/clog-clogf-clogl.md)|Вычисляет комплексный натуральный (по основанию *e*) логарифм комплексного числа|
|[clog10, clog10f, clog10l](../c-runtime-library/reference/clog10-clog10f-clog10l.md)|Вычисляет комплексный логарифм комплексного числа по основанию 10|

## <a name="power-and-absolute-value-functions"></a>Функции возведения в степень и вычисления абсолютного значения

|Функция|Описание|
|-|-|
|[cabs, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md)|Вычисляет комплексное абсолютное значение (также называемое нормой, модулем или порядком величины) комплексного числа|
|[cpow, cpowf, cpowl](../c-runtime-library/reference/cpow-cpowf-cpowl.md)|Возводит комплексное число в степень x<sup>y</sup>|
|[csqrt, csqrtf, csqrtl](../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)|Вычисляет комплексный квадратный корень комплексного числа|

## <a name="manipulation-functions"></a>Функции для манипуляции с комплексными числами

|Функция|Описание|
|-|-|
|[_Cbuild, _FCbuild, _LCbuild](../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)|Формирует комплексное число из вещественной и мнимой частей|
|[carg, cargf, cargl](../c-runtime-library/reference/carg-cargf-cargl.md)|Вычисляет аргумент комплексного числа (также называемый фазовым углом)|
|[cimag, cimagf, cimagl](../c-runtime-library/reference/cimag-cimagf-cimagl.md)|Вычисляет мнимую часть комплексного числа|
|[conj, conjf, conjl](../c-runtime-library/reference/conj-conjf-conjl.md)|Вычисляет комплексно сопряженную величину комплексного числа|
|[cproj, cprojf, cprojl](../c-runtime-library/reference/cproj-cprojf-cprojl.md)|Вычисляет проекцию комплексного числа на сферу Римана|
|[creal, crealf, creall](../c-runtime-library/reference/creal-crealf-creall.md)|Вычисляет вещественную часть комплексного числа|
|[norm, normf, norml](../c-runtime-library/reference/norm-normf-norml1.md)|Вычисляет абсолютное значение комплексного числа в квадрате|

## <a name="operation-functions"></a>Функции арифметических операций

Так как комплексные числа не относятся к собственным типам компилятора Майкрософт, для них не определены стандартные арифметические операторы. Для удобства представлены следующие библиотечные функции, которые позволяют выполнять некоторые операции с комплексными числами в пользовательском коде.

|Функция|Описание|
|-|-|
|[_Cmulcc, _FCmulcc, _LCmulcc](../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)|Произведение двух комплексных чисел|
|[_Cmulcr, _FCmulcr, _LCmulcr](../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)|Умножает комплексное число на число с плавающей запятой|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
