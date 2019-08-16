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
ms.openlocfilehash: 7a2c57713d4b455971f24b64dc124862749e927a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499553"
---
# <a name="rand_s"></a>rand_s

Создает псевдослучайное число. Это более безопасная версия функции [Rand](rand.md)с улучшенной безопасностью, как описано в разделе [функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Параметры

*рандомвалуе*<br/>
Указатель на целое число, в котором хранится созданное значение.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки. Если входной указатель _рандомвалуе_ является пустым указателем, функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **еинвал** и устанавливает значение переводится в **еинвал**. Если функция завершается ошибкой по какой-либо другой причине, *_рандомвалуе_ имеет значение 0.

## <a name="remarks"></a>Примечания

Функция **rand_s** Записывает целое число псевдослучайное в диапазоне от 0 до **UINT_MAX** в указатель ввода. Функция **rand_s** использует операционную систему для создания криптографически защищенных случайных чисел. Оно не использует начальное значение, созданное функцией [srand](srand.md) , и не влияет на последовательность случайных чисел, используемую [СЛЧИС](rand.md).

Функция **rand_s** требует, чтобы константа **_CRT_RAND_S** была определена перед инструкцией включения для объявления функции, как показано в следующем примере:

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** зависит от API [RtlGenRandom](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) , который доступен только в Windows XP и более поздних версиях.

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
