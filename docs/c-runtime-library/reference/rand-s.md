---
title: rand_s
ms.date: 4/2/2020
api_name:
- rand_s
- _o_rand_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand_s
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: b11a40dd9dc58964df77330767a55aa95a179319
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338192"
---
# <a name="rand_s"></a>rand_s

Создает псевдослучайное число. Это более безопасная версия функции [ранд](rand.md), с улучшениями безопасности, как описано в [функциях безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Параметры

*случайноезначение*<br/>
Указатель на ряд, чтобы удерживать генерируемое значение.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки. Если указатель ввода _randomValue_ является нулевой указателем, функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращает **EINVAL** и устанавливает **errno** **в EINVAL.** Если функция выходит из строя по какой-либо другой причине, случайное_значение_ устанавливается до 0.

## <a name="remarks"></a>Remarks

Функция **rand_s** пишет псевдослучайный целый ряд в диапазоне от 0 до **UINT_MAX** указателя на ввод. Функция **rand_s** использует операционную систему для генерации криптографически безопасных случайных чисел. Он не использует семена, генерируемые функцией [srand,](srand.md) и не влияет на последовательность случайных чисел, используемых [рандом.](rand.md)

**Функция rand_s** требует, чтобы постоянная **_CRT_RAND_S** быть определена до оператора включения для заявления функции, как в следующем примере:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** зависит от [API RtlGenRandom,](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) который доступен только в Windows XP и позже.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>Пример выходных данных

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Рэнд](rand.md)<br/>
[srand](srand.md)<br/>
