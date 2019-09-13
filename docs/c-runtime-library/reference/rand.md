---
title: rand
ms.date: 01/02/2018
apiname:
- rand
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 407640c5f00ae54c43450abcbbe8c2e3ba0fcf95
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927530"
---
# <a name="rand"></a>rand

Создает псевдослучайное число с помощью хорошо известного и полностью воспроизводимого алгоритма. Доступна более программная безопасная версия этой функции; см. [rand_s](rand-s.md). Числа, созданные функцией **Rand** , не защищаются криптографически. Для более криптографического безопасного создания случайных чисел используйте [rand_s](rand-s.md) или функции, объявленные в C++ стандартной библиотеке в [ \<случайном >](../../standard-library/random.md).

## <a name="syntax"></a>Синтаксис

```C
int rand( void );
```

## <a name="return-value"></a>Возвращаемое значение

Функция **Rand** возвращает псевдослучайное число, как описано выше. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

Функция **Rand** возвращает псевдослучайное целое число в диапазоне от 0 до **RAND_MAX** (32767). Используйте функцию [srand](srand.md) для заполнения генератора псевдослучайное-Number перед вызовом **функции RAND**.

Функция **Rand** создает хорошо известную последовательность и не подходит для использования в качестве криптографической функции. Для более криптографического безопасного создания случайных чисел используйте [rand_s](rand-s.md) или функции, объявленные в C++ стандартной библиотеке в [ \<случайном >](../../standard-library/random.md). Сведения о том, что именно не так с СЛЧИС \<, и о том, как случайная > устраняет эти недостатки, см. в этом видео с подразделом [Rand о вреде](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**rand**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
