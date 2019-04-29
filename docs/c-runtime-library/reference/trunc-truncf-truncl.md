---
title: trunc, truncf, truncl
ms.date: 04/05/2018
apiname:
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
ms.openlocfilehash: 6e023b9d894ea1b40a0e056e73b7c32f1e3cbed7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268940"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Определяют ближайшего целое число, которое меньше или равно заданному значению с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double trunc( double x );
float trunc( float x ); //C++ only
long double truncl( long double x );
```

```cpp
long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение для усечения.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает целое значение *x*, округленное в сторону нуля.

В случае неудачи может возвращать одно из следующих значений:

|Проблемы|Назад|
|-----------|------------|
|*x* = ±INFINITY|x|
|*x* =  ±0|x|
|*x* = NaN|NaN|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **trunc** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **trunc** всегда принимает и возвращает **двойные**.

Поскольку наибольшими значениями с плавающей запятой являются целые числа, эта функция не будет переполняться сама по себе. Тем не менее можно вызвать переполнение этой функции, возвращая значение в целочисленный тип.

Можно также округлять в меньшую сторону, выполняя неявное преобразование из типа с плавающей запятой в целочисленный тип; однако это можно делать только со значениями, которые могут храниться в целевом типе.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**TRUNC**, **truncf**, **truncl**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
