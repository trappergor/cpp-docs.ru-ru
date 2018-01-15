---
title: "rand_s | Документы Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rand_s
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
f1_keywords: rand_s
dev_langs: C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5fde51ee8fb65426166d9d5d2e7d6e5873dd6e8
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="rands"></a>rand_s

Создает псевдослучайное число. Это более безопасные версии функции [rand](../../c-runtime-library/reference/rand.md), с усовершенствованной безопасностью, как описано в [средства безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md). 

## <a name="syntax"></a>Синтаксис

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Параметры

*randomValue*  
Указатель на целое число для хранения сформированное значение.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки. Если входной указатель _randomValue_ является пустым указателем, функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает `EINVAL` и устанавливает для параметра `errno` значение `EINVAL`. Если функция завершается с ошибкой по другой причине, *_randomValue_ имеет значение 0.

## <a name="remarks"></a>Примечания

Функция `rand_s` записывает псевдослучайное целое число в диапазоне от 0 до `UINT_MAX` в указатель ввода. Функция `rand_s` использует операционную систему для создания криптографически безопасных случайных чисел. Функция не использует начальное значение, созданное функцией [srand](../../c-runtime-library/reference/srand.md), и не влияет на последовательность случайных чисел, которая используется `rand`.

Функция `rand_s` требует, чтобы константа `_CRT_RAND_S` была определена до объявления оператора включения для этой функции, как показано в следующем примере:

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

`rand_s` зависит от API [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694), который доступен только в Windows XP и более поздних версиях.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`rand_s`|\<stdlib.h>|

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

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
[srand](../../c-runtime-library/reference/srand.md)  
