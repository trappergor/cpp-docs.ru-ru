---
title: ceil, ceilf, ceill
ms.date: 04/05/2018
api_name:
- ceilf
- ceil
- ceill
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
- ntdll.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ceil
- ceilf
- ceill
helpviewer_keywords:
- calculating value ceilings
- ceill function
- ceil function
- ceilf function
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
ms.openlocfilehash: 0be81354c19da646fa96f6eb58fbc7c76eeddb33
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943190"
---
# <a name="ceil-ceilf-ceill"></a>ceil, ceilf, ceill

Рассчитывает верхний предел значения.

## <a name="syntax"></a>Синтаксис

```C
double ceil(
   double x
);
float ceil(
   float x
);  // C++ only
long double ceil(
   long double x
);  // C++ only
float ceilf(
   float x
);
long double ceill(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **ceil** возвращают значение с плавающей запятой, представляющее наименьшее целое число, которое больше или равно *x*. Ошибка не возвращается.

|Ввод|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **КНАН**, **С**|none|**_DOMAIN**|

**ceil** имеет реализацию, использующую Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничениях на ее использование см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ceil** , которые принимают типы **float** или **Long** типа **Double** . В программе на языке C **ceil** всегда принимает и возвращает значение **типа Double**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ceil**, **ceilf**, **цеилл**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [floor](floor-floorf-floorl.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
