---
title: erf, erff, erfl, erfc, erfcf, erfcl | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- erff
- erfl
- erf
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
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7ab1448c3f1d77ab79266858a19d822b1cdb4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

**Erf** функции возвращают Гаусса ошибок *x*. **Erfc** функции возвращают взаимодополняющие Гаусса ошибок *x*.

## <a name="remarks"></a>Примечания

**Erf** функции вычисляют функцию Гаусса ошибок из *x*, определяется как:

![Функция ошибок от x](media/crt_erf_formula.PNG "CRT_erf_formula")

Функция Гаусса ошибок определяется как 1 - erf(x). **Erf** функции возвращают значение в диапазоне от -1,0 до 1,0. Ошибка не возвращается. **Erfc** функции возвращают значение в диапазоне от 0 до 2. Если *x* слишком велик для **erfc**, **errno** присваивается переменной **ERANGE**.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **erf** и **erfc** , принимающие и возвращающие **float** и **длинные** **двойные** типов. В программе на языке C **erf** и **erfc** всегда принимают и возвращают **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
