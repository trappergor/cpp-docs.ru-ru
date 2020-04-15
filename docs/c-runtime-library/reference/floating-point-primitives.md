---
title: Примитивы с плавающей запятой
ms.date: 4/2/2020
api_name:
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
- _o__d_int
- _o__dclass
- _o__dlog
- _o__dnorm
- _o__dpcomp
- _o__dpoly
- _o__dscale
- _o__dsign
- _o__dsin
- _o__dtest
- _o__dunscale
- _o__fd_int
- _o__fdclass
- _o__fdexp
- _o__fdlog
- _o__fdpcomp
- _o__fdpoly
- _o__fdscale
- _o__fdsign
- _o__fdsin
- _o__ld_int
- _o__ldclass
- _o__ldexp
- _o__ldlog
- _o__ldpcomp
- _o__ldpoly
- _o__ldscale
- _o__ldsign
- _o__ldsin
- _o__ldtest
- _o__ldunscale
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: d861fbf2b71d557354a60f65b8a76dc24ca1dd13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346712"
---
# <a name="floating-point-primitives"></a>Примитивы с плавающей запятой

Примитивные функции Microsoft, которые используются для реализации некоторых стандартных функций библиотеки времени выполнения C (CRT) с плавающей точкой. Они задокументированы здесь для полноты, но не рекомендуются для использования. Некоторые из этих функций отмечены как неиспользованные, потому что они, как известно, имеют проблемы в точности, обработке исключений и соответствии с iEEE-754 поведения. Они существуют в библиотеке только для обратной совместимости. Для правильного поведения, переносимости и соблюдения стандартов отдавайте предпочтение стандартным функциям плавающей точки над этими функциями.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции плавающей точки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки реализуют C-версии [макроfpclassify](fpclassify.md) CRT для типов плавающих точек. Классификация аргумента *x* возвращается в качестве одной из этих констант, определяемой в math.h:

|Значение|Описание|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное субнормальное (денормированное) значение |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Для получения дополнительной информации можно использовать функции [_fpclass, _fpclassf](fpclass-fpclassf.md) microsoft. Используйте [макрос fpclassify](fpclassify.md) или функцию для переносимости.

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции плавающей точки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки реализуют макрос [signbit](signbit.md) или функцию в CRT. Они возвращают ненулевое значение, если бит знака установлен в significand (mantissa) *аргумента x,* и 0, если бит знака не установлен.

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Аргументы функции плавающей точки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки принимают два аргумента, *x* и *y*, и вернуть значение, которое показывает их упорядочения отношения, выраженные как bitwise или этих констант, определенных в math.h:

| Значение | Описание |
|------------|-----------------|
| **_FP_LT** | *х* можно считать менее *y* |
| **_FP_EQ** | *х* можно считать равным *y* |
| **_FP_GT** | *х* можно считать больше, чем *у* |

Эти примитивы реализуют [isgreater, isgreaterequal, isless, islessequal, islessgreater, и isunordered](floating-point-ordering.md) макросов и функций в CRT.

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Параметры

*Px*<br/>
Указатель на аргумент плавающей точки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки реализуют версии функции CRT [fpclassify](fpclassify.md) для типов плавающих точек. Аргумент *x* оценивается и классификация возвращается как одна из этих констант, определяемая в math.h:

|Значение|Описание|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное субнормальное (денормированное) значение |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Для получения дополнительной информации можно использовать функции [_fpclass, _fpclassf](fpclass-fpclassf.md) microsoft. Используйте функцию [fpclassify](fpclassify.md) для переносимости.

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Параметры

*Px*<br/>
Указатель на аргумент плавающей точки.

*Exp*<br/>
Экспонент как интегральный тип.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки принимают указатель на плавающей точки значение *px* и экспоненциальное значение *exp*, и удалить дробную часть плавающей точки значение ниже данного экспонента, если это возможно. Возвратное значение является результатом **fpclassify** на вхотворное значение в *px,* если это NaN или бесконечность, и на выходное значение в *px* в противном случае.

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Параметры

*Px*<br/>
Указатель на аргумент плавающей точки.

*Exp*<br/>
Экспонент как интегральный тип.

### <a name="remarks"></a>Remarks

Эти плавающей точки примитивы принять указатель на плавающей точки значение *px* и экспоненциативное значение *exp*, и масштабировать значение в *px* на 2<sup>*exp*</sup>, если это возможно. Возвратное значение является результатом **fpclassify** на вхотворное значение в *px,* если это NaN или бесконечность, и на выходное значение в *px* в противном случае. Для переносимости отчими функций [ldexp, ldexpf и ldexpl.](ldexp.md)

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Параметры

*pexp*<br/>
Указатель на показатель как интегральный тип.

*Px*<br/>
Указатель на аргумент плавающей точки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки разбивают значение плавающей точки, на который указывает *px,* на significand (mantissa) и показатель, если это возможно. Значение масштабируется таким образом, что абсолютное значение больше или равно 0,5 и менее 1,0. Экспонентом является значение *n*, где первоначальное значение плавающей точки равно масштабированным significand раз 2<sup>*n*</sup>. Этот integer экспонент *n* хранится в месте, указал на *pexp*. Возвратное значение является результатом **fpclassify** на вхотворное значение в *px,* если это NaN или бесконечность, и на выходное значение в противном случае. Для переносимости, предпочитают [frexp, frexpf, frexpl](frexp.md) функции.

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Параметры

*Y*<br/>
Аргумент функции плавающей точки.

*Px*<br/>
Указатель на аргумент плавающей точки.

*Exp*<br/>
Экспонент как интегральный тип.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки построить плавающей точки значение в месте, указал на *px* равна *у* 2<sup>*exp*</sup>. Возвратное значение является результатом **fpclassify** на вхоточении в *y,* если это NaN или бесконечность, и на выходное значение в *px* в противном случае. Для переносимости отчими функций [ldexp, ldexpf и ldexpl.](ldexp.md)

## <a name="_dnorm-_fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Параметры

*Ps*<br/>
Указатель на бикерное представление значения плавающей точки, выраженного как массив **неподписанных** **коротких.**

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки нормализуют дробную часть недополнейшей плавающей точки и корректируют *характеристику*или предвзятое экспонента, чтобы соответствовать. Значение передается как битовое представление типа плавающей точки, преобразованного в массив `_double_val` `_ldouble_val` **неподписанных** **коротких** через , или `_float_val` тип punning союз, объявленный в math.h. Значение возврата является результатом **fpclassify** на значение входиной плавающей точки, если это NaN или бесконечность, и на выходное значение в противном случае.

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции плавающей точки.

*Таблице*<br/>
Указатель на таблицу постоянных коэффициентов для полиномиала.

*n*<br/>
Порядок полиномиальной оценки.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки возвращают оценку *x* в полиномиальный порядок *n,* коэффициенты которого представлены соответствующими постоянными значениями в *таблице.* Например, если *таблица*\[0", *таблица*\[1, таблица 1, *таблица*\[2, 5,0 и *n* No 2, она представляет собой полиномиальный 5,0x<sup>2</sup> и 4,0x 3,0. Если этот полиномиальный оценивается *в* 2,0 х, результат 31,0. Эти функции не используются внутри компании.

## <a name="_dlog-_dlog-_dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции плавающей точки.

*base_flag*<br/>
Флаг, который контролирует базу для использования, 0 для базы *e* и ненулевой для базы 10.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки возвращают естественный журнал *x,* ln (*x)* или log<sub>*e*</sub>*(x),* когда *base_flag* 0. Они возвращают базу журнала 10 *х,* или журнал<sub>10</sub>*(x),* когда *base_flag* не является нулевым. Эти функции не используются внутри компании. Для переносимости отчесть [журнал функций, журнал, журнал, журнал, журнал10, журнал10f и log10l.](log-logf-log10-log10f.md)

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции плавающей точки.

*Квадрант*<br/>
Квадрант смещения 0, 1, 2, `-sin`или `-cos` 3 для использования для производства `sin`, `cos`, и результаты.

### <a name="remarks"></a>Remarks

Эти примитивы плавающей точки возвращают синус *х,* смещенный *квадрантом* модуло 4. Фактически, они возвращают синус, cosine, -sine, и -cosine *x* когда *quadrant* modulo 4 0, 1, 2, или 3, соответственно. Эти функции не используются внутри компании. Для переносимости, предпочитают [грех, грех, грех,](sin-sinf-sinl.md) [потому что, cosf, и cosl](cos-cosf-cosl.md) функций.

## <a name="requirements"></a>Требования

Заголовок: \<math.h>

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка плавающей точки](../floating-point-support.md)<br/>
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
