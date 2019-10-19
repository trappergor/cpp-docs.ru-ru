---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 01/31/2019
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: df724ed056c02d79b5b51f97ae4aaf8ae267fde5
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "70937618"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Вычисляет функцию ошибок или дополнительную функцию ошибок значения.

## <a name="syntax"></a>Синтаксис

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **Фош** возвращают функцию Гаусса Error типа *x*. Функции **ерфк** возвращают дополняющую функцию ошибки Гаусса *x*.

## <a name="remarks"></a>Заметки

Функции **Фош** вычисляют функцию Гаусса Error *x*, которая определяется следующим образом:

![Функция Error объекта x](media/crt_erf_formula.PNG "Функция ошибок от x")

Функция дополнения Гаусса Error определяется как 1-Фош (x). Функции **Фош** возвращают значение в диапазоне от-1,0 до 1,0. Ошибка не возвращается. Функции **ерфк** возвращают значение в диапазоне от 0 до 2. Если *x* слишком велико для **ерфк**, то для переменной « **No** » задано значение **ERANGE**.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Фош** и **ерфк** , которые принимают и возвращают типы **float** и **Long** **Double** . В программе на языке C **Фош** и **ерфк** всегда принимают и возвращают **Двойное**значение.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**Фош**, **erff**, **ерфл**, **ерфк**, **ерфкф**, **ерфкл**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
