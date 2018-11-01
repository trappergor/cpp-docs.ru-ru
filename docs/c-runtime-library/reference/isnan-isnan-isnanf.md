---
title: isnan, _isnan, _isnanf
ms.date: 04/05/2018
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
ms.openlocfilehash: ce111569b7caee9d0c7b8f35352c395571ad08b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650870"
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf

Проверяет, является ли значение с плавающей запятой нечисловым значением (NAN).

## <a name="syntax"></a>Синтаксис

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

В языке C **isnan** макрос и **_isnan** и **_isnanf** функции возвращают ненулевое значение, если аргумент *x* имеет значение NAN; в противном случае они Возвращает значение 0.

В C++ **isnan** шаблона функции возвращают **true** Если аргумент *x* является значением NAN в противном случае они возвращают **false**.

## <a name="remarks"></a>Примечания

C **isnan** макрос и **_isnan** и **_isnanf** функции проверяют значение с плавающей запятой *x*, возвращают ненулевое значение, если *x* не является числом (NAN) значение. Значение NAN получается в том случае, если результат операции с плавающей запятой не удается представить в формате IEEE-754 с плавающей запятой для указанного типа. Сведения о том, как значение NaN представляется для вывода, см. в разделе [printf](printf-printf-l-wprintf-wprintf-l.md).

При компиляции как C++, **isnan** макрос не определен и **isnan** вместо этого определяется функция-шаблон. Он возвращает значение типа **bool** вместо integer.

**_Isnan** и **_isnanf** функции только к системам Майкрософт. **_Isnanf** функция доступна только при компиляции для x64.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**isNaN**, **_isnanf**|\<math.h>|\<math.h> или \<cmath>|
|**_isnan**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
