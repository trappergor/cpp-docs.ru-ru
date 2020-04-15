---
title: rand
ms.date: 4/2/2020
api_name:
- rand
- _o_rand
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 944c512d0102b459afc2924ef7515311e46cd43c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338161"
---
# <a name="rand"></a>rand

Генерирует псевдослучайный номер с помощью хорошо известного и полностью воспроизводимого алгоритма. Доступна более программно безопасная версия этой функции; увидеть [rand_s](rand-s.md). Номера, генерируемые **рандом,** не являются криптографически безопасными. Для более криптографически безопасного генерации случайных чиче, используйте [rand_s](rand-s.md) или функции, заявленные в [ \< ](../../standard-library/random.md)Стандартной библиотеке СЗ в случайном>.

## <a name="syntax"></a>Синтаксис

```C
int rand( void );
```

## <a name="return-value"></a>Возвращаемое значение

**ранд** возвращает псевдослучайное число, как описано выше. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

Функция **ранда** возвращает псевдослучайный целый ряд в диапазоне от 0 до **RAND_MAX** (32767). Используйте функцию [srand](srand.md) для семени генератора псевдослучайного числа перед вызовом **ранда.**

Функция **ранда** генерирует хорошо известную последовательность и не подходит для использования в качестве криптографической функции. Для более криптографически безопасного генерации случайных чиче, используйте [rand_s](rand-s.md) или функции, заявленные в [ \< ](../../standard-library/random.md)Стандартной библиотеке СЗ в случайном>. Для получения информации о том, \<что случилось с **рандом** [rand Considered Harmful](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)и как случайные> устраняет эти недостатки, см.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Рэнд**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
