---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 01/31/2019
apiname:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
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
ms.openlocfilehash: 4270d8366686ea282a4dd37741d9f8e37991b88f
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702665"
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

**Erf** функции возвращают Гаусса функция ошибок от *x*. **Erfc** функции возвращают взаимодополняющие Гаусса функция ошибок от *x*.

## <a name="remarks"></a>Примечания

**Erf** функции вычисляют функцией ошибок Гаусса из *x*, который определен как:

![Функция ошибок от x](media/crt_erf_formula.PNG "функция ошибок от x")

Функция Гаусса ошибок определяется как 1 - erf(x). **Erf** функции возвращают значение в диапазоне от -1.0 до версии 1.0. Ошибка не возвращается. **Erfc** функции возвращают значение в диапазоне от 0 до 2. Если *x* слишком велик для **erfc**, **errno** переменной присваивается **ERANGE**.

Так как C++ допускает перегрузку, можно вызывать перегрузки **erf** и **erfc** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **erf** и **erfc** всегда принимают и возвращают **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
