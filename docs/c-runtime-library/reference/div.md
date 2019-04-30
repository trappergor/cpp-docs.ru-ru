---
title: элемент DIV, ldiv, lldiv
ms.date: 04/05/2018
apiname:
- div
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
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 0ee1b3b6a5d7b15470ffe1e667b4077d1f9581e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339264"
---
# <a name="div-ldiv-lldiv"></a>элемент DIV, ldiv, lldiv

Вычисляет частное и остаток от деления двух целочисленных значений.

## <a name="syntax"></a>Синтаксис

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>Параметры

*Число добавлений*<br/>
Числитель.

*denom*<br/>
Знаменатель.

## <a name="return-value"></a>Возвращаемое значение

**div** вызванная с использованием аргументов типа **int** возвращает структуру типа **div_t**, который состоит из частное и остаток. Возвращаемое значение с аргументами типа **long** — **ldiv_t**и возвращаемое значение с аргументами типа **long** **long** является **lldiv_t**. **div_t**, **ldiv_t**, и **lldiv_t** определяются в \<stdlib.h >.

## <a name="remarks"></a>Примечания

**Div** функция делит *числа* по *denom* и тем самым Вычисляет частное и остаток. [Div_t](../../c-runtime-library/standard-types.md) структура содержит частное, **quot**и остаток, **rem**. Знак частного совпадает со знаком математического частного. Его абсолютное значение представляет собой наибольшее целое число, которое меньше абсолютного значения математического частного. Если знаменатель равен 0, выполнение программы прекратится и появится сообщение об ошибке.

Перегрузки **div** , принимающие аргументы типа **long** или **long** **long** доступны только для кода C++. Типы возврата [ldiv_t](../../c-runtime-library/standard-types.md) и [lldiv_t](../../c-runtime-library/standard-types.md) содержит члены **quot** и **rem**, которые имеют те же смысловые значения, что и члены **div_t**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
