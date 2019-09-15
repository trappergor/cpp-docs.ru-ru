---
title: _set_SSE2_enable
ms.date: 04/05/2018
api_name:
- _set_SSE2_enable
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
- _set_SSE2_enable
- set_SSE2_enable
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
ms.openlocfilehash: 8838282db851c6811a3f24c75a03b31c5870e6d3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948362"
---
# <a name="_set_sse2_enable"></a>_set_SSE2_enable

Включает или отключает использование инструкций Streaming SIMD Extensions 2 (SSE2) в математических подпрограммых CRT. (Эта функция недоступна для архитектур x64, поскольку набор инструкций SSE2 включен по умолчанию.)

## <a name="syntax"></a>Синтаксис

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Параметры

*RAS*<br/>
1 для включения реализации SSE2; 0 для отключения реализации SSE2. По умолчанию реализация SSE2 включена для процессоров, которые ее поддерживают.

## <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если реализация SSE2 включена; ноль, если реализация SSE2 отключена.

## <a name="remarks"></a>Примечания

Следующие функции имеют реализации SSE2, которые можно включить с помощью **_set_SSE2_enable**:

- [atan](atan-atanf-atanl-atan2-atan2f-atan2l.md)

- [ceil](ceil-ceilf-ceill.md)

- [exp](exp-expf.md)

- [floor](floor-floorf-floorl.md)

- [log](log-logf-log10-log10f.md)

- [log10](log-logf-log10-log10f.md)

- [modf](modf-modff-modfl.md)

- [pow](pow-powf-powl.md)

SSE2-реализации этих функций могут предоставлять результаты, немного отличающиеся от результатов реализаций по умолчанию, поскольку промежуточными значениями SSE2 являются 64-разрядные числа с плавающей запятой, а промежуточные значения реализаций по умолчанию — 80-разрядные числа с плавающей запятой.

> [!NOTE]
> Если для компиляции проекта используется параметр компилятора [/Oi (создание встроенных функций)](../../build/reference/oi-generate-intrinsic-functions.md) , может показаться, что **_set_SSE2_enable** не оказывает никакого влияния. Параметр компилятора **/Oi** дает компилятору право использовать встроенные функции для замены вызовов CRT; Это поведение переопределяет результат **_set_SSE2_enable**. Если вы хотите гарантировать, что **/Oi** не переопределит **_set_SSE2_enable**, используйте **/ОИ-** для компиляции проекта. Это также может оказаться хорошей практикой при использовании других параметров компилятора, которые подразумевают **/Oi**.

Реализация SSE2 используется только в том случае, если все исключения маскированы. Используйте [_control87, _controlfp](control87-controlfp-control87-2.md) для маскирования исключений.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_SSE2_enable**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_set_SSE2_enable.c
// processor: x86
#include <math.h>
#include <stdio.h>

int main()
{
   int i = _set_SSE2_enable(1);

   if (i)
      printf("SSE2 enabled.\n");
   else
      printf("SSE2 not enabled; processor does not support SSE2.\n");
}
```

```Output
SSE2 enabled.
```

## <a name="see-also"></a>См. также

[Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md)<br/>
