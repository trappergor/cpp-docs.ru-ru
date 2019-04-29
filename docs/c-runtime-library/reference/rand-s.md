---
title: rand_s
ms.date: 1/02/2018
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: d196a6f5d7483deb9a7e1b8d7fa929532b6197db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358129"
---
# <a name="rands"></a>rand_s

Создает псевдослучайное число. Это более безопасная версия функции [rand](rand.md), с усовершенствованной безопасностью, как описано в разделе [функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Параметры

*randomValue*<br/>
Указатель на целое число для хранения созданного значения.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки. Если входной указатель _randomValue_ является пустым указателем, функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **EINVAL** и задает **errno** для **EINVAL**. Если функция завершается с ошибкой по другой причине, *_randomValue_ имеет значение 0.

## <a name="remarks"></a>Примечания

**Rand_s** функция записывает псевдослучайное целое число в диапазоне от 0 до **UINT_MAX** в указатель ввода. **Rand_s** функция использует операционную систему для создания криптографически безопасных случайных чисел. Она не использует начальное значение, созданное [srand](srand.md) функции, и влияет на последовательность случайных чисел, используемый [rand](rand.md).

**Rand_s** функция требует, чтобы константа **_CRT_RAND_S** определяться до оператора включения функции быть объявлено, как показано в следующем примере:

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** зависит от [— RtlGenRandom](/windows/desktop/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API, который является только в Windows XP и более поздних версий.

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

### <a name="sample-output"></a>Пример результатов выполнения

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

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
[srand](srand.md)<br/>
