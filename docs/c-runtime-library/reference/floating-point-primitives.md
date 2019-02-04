---
title: С плавающей запятой примитивы
ms.date: 01/31/2019
apiname:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: 230d0def145bcb443437b59303b2b36e348da2bb
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703482"
---
# <a name="floating-point-primitives"></a>С плавающей запятой примитивы

Характерные для Майкрософт простые функции, которые используются для реализации некоторых стандартных C функциям библиотеки времени выполнения (CRT) с плавающей запятой. Вы здесь для полноты информации, но не рекомендуется использовать. Ниже приведены некоторые из этих функций указано как неиспользуемый, так как они известны проблемы в точности, обработки исключений и соответствия спецификациям стандарта IEEE-754 поведение. Они существуют в библиотеке только в целях обратной совместимости. Для правильного поведения переносимость и строгое соблюдение стандартов, предпочтение отдается стандартные функции с плавающей запятой этих функций.

## <a name="dclass-ldclass-fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой реализовать версии C макрос CRT [fpclassify](fpclassify.md) для типов с плавающей запятой. Классификацию для аргумента *x* возвращается в виде одной из этих констант, определенных в math.h:

|Значение|Описание:|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное subnormal (денормализованные) значение |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Дополнительные сведения можно использовать характерные для Майкрософт [_fpclass, _fpclassf](fpclass-fpclassf.md) функции. Используйте [fpclassify](fpclassify.md) макроса или функции, для обеспечения переносимости.

## <a name="dsign-ldsign-fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей запятой.

### <a name="remarks"></a>Примечания

Реализация следующих примитивов с плавающей запятой [signbit](signbit.md) макрос или функцию в CRT. Они возвращают ненулевое значение, если бит знака в значащей части числа (мантиссы) аргумента *x*и 0, если бит знака не задано.

## <a name="dpcomp-ldpcomp-fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Аргументы функции с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают два аргумента, *x* и *y*и возвращает значение, которое показывает их связь упорядочивания, выраженный как побитовое или из этих констант, определенных в math.h:

| Значение | Описание: |
|------------|-----------------|
| **_FP_LT** | *x* можно считать меньше, чем *y* |
| **_FP_EQ** | *x* могут считаться равным *y* |
| **_FP_GT** | *x* можно считать больше, чем *y* |

Эти примитивы реализовать [isgreater isgreaterequal, isless, islessequal, islessgreater и isunordered](floating-point-ordering.md) макросы и функции в CRT.

## <a name="dtest-ldtest-fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Параметры

*px*<br/>
Указатель на аргумент с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой реализации C++ версии функции CRT, [fpclassify](fpclassify.md) для типов с плавающей запятой. Аргумент *x* вычисляется и возвращается как один из этих констант, определенных в math.h классификации:

|Значение|Описание:|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное subnormal (денормализованные) значение |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Дополнительные сведения можно использовать характерные для Майкрософт [_fpclass, _fpclassf](fpclass-fpclassf.md) функции. Используйте [fpclassify](fpclassify.md) функции для обеспечения переносимости.

## <a name="dint-ldint-fdint"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Параметры

*px*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Показатель степени как целочисленный тип.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают указатель на значение с плавающей запятой *px* и значение экспоненты *exp*и удалите дробная часть значения с плавающей запятой, ниже заданного показатель степени, если это возможно . Возвращаемое значение является результатом **fpclassify** над входным значением в *px* в случае значением NaN или бесконечностью, а также на выходное значение в *px* в противном случае.

## <a name="dscale-ldscale-fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Параметры

*px*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Показатель степени как целочисленный тип.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают указатель на значение с плавающей запятой *px* и значение экспоненты *exp*, и масштабировать его в *px* 2<sup> *exp*</sup>, если это возможно. Возвращаемое значение является результатом **fpclassify** над входным значением в *px* в случае значением NaN или бесконечностью, а также на выходное значение в *px* в противном случае. Для обеспечения переносимости, предпочитать [ldexp, ldexpf и ldexpl](ldexp.md) функции.

## <a name="dunscale-ldunscale-fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Параметры

*pexp*<br/>
Указатель на показатель степени как целочисленный тип.

*px*<br/>
Указатель на аргумент с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой разбить значение с плавающей запятой, на который ссылается *px* в значащей части числа (мантиссы) и показатель степени, если это возможно. Значащая масштабируется таким образом, абсолютное значение больше или равно 0,5 и меньше 1,0. Значение экспоненты *n*, где исходное значение с плавающей запятой равно масштабированное значащей части числа раз 2<sup>*n*</sup>. Этот показатель степени целого числа *n* хранится в расположении, указанном *pexp*. Возвращаемое значение является результатом **fpclassify** над входным значением в *px* в случае значением NaN или бесконечностью, а также на выходное значение в противном случае. Для обеспечения переносимости, предпочитать [frexp, frexpf, frexpl](frexp.md) функции.

## <a name="dexp-ldexp-fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Параметры

*y*<br/>
Аргумент функции с плавающей запятой.

*px*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Показатель степени как целочисленный тип.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой составить значение с плавающей запятой в расположении, на который ссылается *px* равным *y* * 2<sup>*exp*</sup>. Возвращаемое значение является результатом **fpclassify** над входным значением в *y* в случае значением NaN или бесконечностью, а также на выходное значение в *px* в противном случае. Для обеспечения переносимости, предпочитать [ldexp, ldexpf и ldexpl](ldexp.md) функции.

## <a name="dnorm-fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Параметры

*PS*<br/>
Указатель на побитовое представление значения с плавающей запятой, выраженное как массив **без знака** **короткие**.

### <a name="remarks"></a>Примечания

Эти примитива с плавающей запятой дробная часть значения с плавающей запятой underflowed нормализовать и настроить *характеристика*, или смещенной показатель степени, в соответствии с. Значение, передаваемое как побитовое представление типа с плавающей запятой, преобразуется в массив **без знака** **короткие** через `_double_val`, `_ldouble_val`, или `_float_val` типа punning union, объявленные в math.h. Возвращаемое значение является результатом **fpclassify** над входным значением с плавающей запятой, если он является значением NaN или бесконечностью, а также на выходное значение в противном случае.

## <a name="dpoly-ldpoly-fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей запятой.

*table*<br/>
Указатель на таблицу с коэффициентами константы для полинома.

*n*<br/>
Порядок полинома для оценки.

### <a name="remarks"></a>Примечания

Эти примитива с плавающей запятой возвращают вычисления *x* в полинома заказа *n* , коэффициенты представлены соответствующие значения констант в *таблицы*. Например, если *таблицы*\[0] = 3.0 *таблицы*\[1] = 4.0, *таблицы*\[2] = 5.0, и *n* = 2, он представляет полиномиальной 5.0 x<sup>2</sup> + 4.0 x + 3.0. Если этот полинома вычисляется для *x* 2.0, результатом является 31.0. Эти функции не используются внутренне.

## <a name="dlog-dlog-dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей запятой.

*base_flag*<br/>
Флаг, который определяет основание, 0 для базового *e* и ненулевой идентификатор для по основанию 10.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой возвращают натуральный логарифм от *x*, ln (*x*) или журнал<sub>*e*</sub>(*x*), Когда *base_flag* равно 0. Они возвращают журнал основанию 10 от *x*, или в журнале<sub>10</sub>(*x*), когда *base_flag* имеет ненулевое значение. Эти функции не используются внутренне. Для обеспечения переносимости, предпочитать функции [log, logf, logl, log10, log10f и log10l](log-logf-log10-log10f.md).

## <a name="dsin-ldsin-fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей запятой.

*четверти*<br/>
Квадрант смещение 0, 1, 2 или 3, чтобы использовать для создания `sin`, `cos`, `-sin`, и `-cos` результаты.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой возвращают синус *x* смещения по *квадранте* по модулю 4. Фактически, они возвращают синус, косинус, - синус и - косинус *x* при *квадранте* по модулю 4 — 0, 1, 2 или 3, соответственно. Эти функции не используются внутренне. Для обеспечения переносимости, предпочитать [sin, sinf, sinl](sin-sinf-sinl.md), [cos, cosf и cosl](cos-cosf-cosl.md) функции.

## <a name="requirements"></a>Требования

Заголовок: \<math.h >

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка плавающей запятой](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, ldexpf и ldexpl](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
