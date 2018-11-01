---
title: clog10, clog10f, clog10l
ms.date: 11/04/2016
apiname:
- clog10
- clog10f
- clog10l
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
- clog10
- clog10f
- clog10l
- complex/clog10
- complex/clog10f
- complex/clog10l
helpviewer_keywords:
- clog10 function
- clog10f function
- clog10l function
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
ms.openlocfilehash: 195f4be80f0320e83cc9455a598185ce281bbf59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506916"
---
# <a name="clog10-clog10f-clog10l"></a>clog10, clog10f, clog10l

Извлекает десятичный логарифм комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex clog10( _Dcomplex z );
_Fcomplex clog10f( _Fcomplex z );
_Lcomplex clog10l( _Lcomplex z );
```

```cpp
_Fcomplex clog10( _Fcomplex z );  // C++ only
_Lcomplex clog10( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Параметры

*z*<br/>
Основание логарифма.

## <a name="return-value"></a>Возвращаемое значение

Возможны следующие возвращаемые значения:

|параметр z|Возвращаемое значение|
|-----------------|------------------|
|Положительное число|Десятичный логарифм z|
|Нуль|- ∞|
|Отрицательное число|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **clog10** , принимающие и возвращающие **_Fcomplex** и **_Lcomplex** значения. В программе на языке C **clog10** всегда принимает и возвращает **_Dcomplex** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**clog10**, **clog10f**, **clogl**|\<complex.h>|\<ccomplex>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
