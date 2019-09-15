---
title: fegetround, fesetround
ms.date: 04/05/2018
api_name:
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
ms.openlocfilehash: b210dbce3104820f667d4ad0b4421277567b279f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941200"
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround

Получает или задает текущий режим округления с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>Параметры

*round_mode*<br/>
Задаваемый режим округления в виде одного из округляющих макросов. Если значение не равно одному из округляющих макросов с плавающей запятой, режим округления не изменяется.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении **fegetround** Возвращает режим округления в виде одного из значений макроса округления с плавающей точкой. Возвращается отрицательное значение, если текущий режим округления невозможно определить.

При успешном выполнении **fesetround** возвращает 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

Операции с плавающей запятой могут использовать один из нескольких режимов округления. Они управляют направлением, в котором округляются результаты операций с плавающей запятой при сохранении. Это имена и поведение округляющего макроса с плавающей запятой, заданного в \<fenv.h>:

|Макрос|Описание|
|-----------|-----------------|
|FE_DOWNWARD|Округление в сторону отрицательной бесконечности.|
|FE_TONEAREST|Округление в сторону ближайшего целого числа.|
|FE_TOWARDZERO|Округление к нулю.|
|FE_UPWARD|Округление в сторону положительной бесконечности|

Поведение по умолчанию FE_TONEAREST — округление результатов представляемых значений в сторону ближайшего значения с четным (0), наименее значимым битом.

Текущий режим округления затрагивает следующие операции.

- Преобразование строк.

- Результаты арифметических операций с плавающей запятой за пределами константных выражений.

- Функции округления библиотеки, такие как **Печать** и **неарбинт**.

- Значения, возвращаемые из математических функций стандартной библиотеки.

Текущий режим округления не затрагивает следующие операции.

- Функции библиотеки **TRUNC**, **ceil**, **Floor**и **лраунд** .

- Приведения и преобразования с плавающей запятой, которые всегда округляются в сторону нуля.

- Результаты арифметических операторов с плавающей запятой в константных выражениях, которые всегда округляются в сторону ближайшего целого значения.

Чтобы использовать эти функции, необходимо выключить оптимизации с плавающей запятой, которые могут препятствовать доступу, с помощью директивы `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fegetround**, **fesetround**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
