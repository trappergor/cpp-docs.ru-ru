---
title: imaxabs
description: Справочник по API для имаксабс, который вычисляет абсолютное значение целого числа любого размера.
ms.date: 04/05/2018
api_name:
- imaxabs
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- imaxabs
helpviewer_keywords:
- imaxabs function
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
ms.openlocfilehash: 599e8a0cb20f24bda24201be40fa1acc0ade993c
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555505"
---
# <a name="imaxabs"></a>imaxabs

Вычисляет абсолютное значение целого числа любого размера.

## <a name="syntax"></a>Синтаксис

```C
intmax_t imaxabs(
   intmax_t n
);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целое значение.

## <a name="return-value"></a>Возвращаемое значение

Функция **имаксабс** возвращает абсолютное значение аргумента. Ошибки не возвращаются.

> [!NOTE]
> Так как диапазон отрицательных целых чисел, которые могут быть представлены с помощью **intmax_t** , больше, чем диапазон положительных целых чисел, которые могут быть представлены, можно указать аргумент для **имаксабс** , который невозможно преобразовать. Если абсолютное значение аргумента не может быть представлено типом возвращаемого значения, поведение **имаксабс** не определено.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**imaxabs**|\<inttypes.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_imaxabs.c
// Build using: cl /W3 /Tc crt_imaxabs.c
// This example calls imaxabs to compute an
// absolute value, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x = LLONG_MIN + 2;

   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));
}
```

```Output
The absolute value of -9223372036854775806 is 9223372036854775806
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
