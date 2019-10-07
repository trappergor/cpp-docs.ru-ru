---
title: fmin, fminf, fminl
ms.date: 04/05/2018
api_name:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: df01f2205291920b8c0519db622c93048278beb1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957093"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

Определяет наименьшее из двух указанных значений.

## <a name="syntax"></a>Синтаксис

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Первое сравниваемое значение.

*y*<br/>
Второе сравниваемое значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает меньшее значение *x* или *y*.

|Ввод|Результат|
|-----------|------------|
|*x* является NaN|*y*|
|*y* — NaN|*x*|
|*x* и *y* — это NaN|NaN|

Функция не вызывает вызов [_matherr](matherr.md) , приводит к возникновению исключений с плавающей запятой или изменению значения «ошибка **».**

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **фмин** , которые принимают и возвращают типы **float** и **Long** **Double** . В программе на языке C **фмин** всегда принимает и возвращает значение **типа Double**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**фмин**, **фминф**, **фминл**|C: \<math.h><br />C++: \<math.h> или \<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
