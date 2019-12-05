---
title: _fpclass, _fpclassf
ms.date: 04/05/2018
api_name:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
ms.openlocfilehash: db95453a44f6a55d4bf98638351dcda4bd8377c9
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857844"
---
# <a name="_fpclass-_fpclassf"></a>_fpclass, _fpclassf

Возвращает значение, указывающее классификацию числа с плавающей запятой для аргумента.

## <a name="syntax"></a>Синтаксис

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **_fpclass** и **_fpclassf** возвращают целочисленное значение, которое указывает на классификацию с плавающей запятой аргумента *x*. Классификация может иметь одно из следующих значений, определенных в \<float.h>.

|{2&gt;Value&lt;2}|Описание|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Сигнальное значение NaN|
|**_FPCLASS_QNAN**|Несигнальное значение NaN|
|**_FPCLASS_NINF**|Отрицательная бесконечность (-INF)|
|**_FPCLASS_NN**|Отрицательное ненулевое нормализованное значение|
|**_FPCLASS_ND**|Отрицательное денормализованное значение|
|**_FPCLASS_NZ**|Отрицательный ноль (-0)|
|**_FPCLASS_PZ**|Положительный 0 (+ 0)|
|**_FPCLASS_PD**|Положительное денормализованное значение|
|**_FPCLASS_PN**|Положительное ненулевое нормализованное значение|
|**_FPCLASS_PINF**|Положительная бесконечность (+INF)|

## <a name="remarks"></a>Заметки

Функции **_fpclass** и **_fpclassf** являются специфичными для Microsoft. Они похожи на [fpclassify](fpclassify.md), но возвращают подробные сведения об аргументе. Функция **_fpclassf** доступна только при компиляции для платформы x64.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также:

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>