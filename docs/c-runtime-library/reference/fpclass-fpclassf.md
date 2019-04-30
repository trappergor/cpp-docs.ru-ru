---
title: _fpclass, _fpclassf
ms.date: 04/05/2018
apiname:
- _fpclass
- _fpclassf
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
ms.openlocfilehash: 987c87cc7a03f4a24e47654ae52e8a2416a15184
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333226"
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf

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

**_Fpclass** и **_fpclassf** функции возвращают целое значение, указывающее классификацию, с плавающей запятой для аргумента *x*. Классификация может иметь одно из следующих значений, определенных в \<float.h>.

|Значение|Описание|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Сигнальное значение NaN|
|**_FPCLASS_QNAN**|Несигнальное значение NaN|
|**_FPCLASS_NINF**|Отрицательная бесконечность (-INF)|
|**_FPCLASS_NN**|Отрицательное ненулевое нормализованное значение|
|**_FPCLASS_ND**|Отрицательное денормализованное значение|
|**_FPCLASS_NZ**|Отрицательный ноль (- 0)|
|**_FPCLASS_PZ**|Положительный 0 (+ 0)|
|**_FPCLASS_PD**|Положительное денормализованное значение|
|**_FPCLASS_PN**|Положительное ненулевое нормализованное значение|
|**_FPCLASS_PINF**|Положительная бесконечность (+INF)|

## <a name="remarks"></a>Примечания

**_Fpclass** и **_fpclassf** функции только к системам Майкрософт. Они похожи на [fpclassify](fpclassify.md), но возвращают подробные сведения об аргументе. **_Fpclassf** функция доступна только при компиляции для x64 платформы.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>