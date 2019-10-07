---
title: nan, nanf, nanl
ms.date: 01/31/2019
api_name:
- nanf
- nan
- nanl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- nan
- nanl
- nanf
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
ms.openlocfilehash: 9574eb0382f3bb7fc3c51d504aba9e29d0692c09
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951423"
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl

Возвращает несигнальное значение NaN (QNaN).

## <a name="syntax"></a>Синтаксис

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>Параметры

*входной*<br/>
Строковое значение.

## <a name="return-value"></a>Возвращаемое значение

Функции **NaN** возвращают нетихом значение NaN.

## <a name="remarks"></a>Примечания

Функции **NaN** возвращают значение с плавающей запятой, соответствующее скрытому типу NaN (без сигнализации). *Входное* значение игнорируется. Сведения о том, как значение NaN представляется для вывода, см. в разделе [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**NaN**, **nanf**, **нанл**|\<math.h>|\<cmath> или \<math.h>|

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
