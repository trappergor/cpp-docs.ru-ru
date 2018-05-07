---
title: trunc, truncf, truncl | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c179065a6b2c6fc10a4ba6ba87868c8306a2aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

В случае успеха возвращает целочисленное значение *x*, округленные к нулю.

В случае неудачи может возвращать одно из следующих значений:

|Проблеми|Назад|
|-----------|------------|
|*x* = ±INFINITY|x|
|*x* = ±0|x|
|*x* = NaN|NaN|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **trunc** , принимающие и возвращающие **float** и **длинные** **двойные** типов. В программе на языке C **trunc** всегда принимает и возвращает **двойные**.

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
