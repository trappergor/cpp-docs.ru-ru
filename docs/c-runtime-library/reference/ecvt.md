---
title: _ecvt
ms.date: 4/2/2020
api_name:
- _ecvt
- _o__ecvt
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 5e1760d5c68e650f6fbf44866d4e368b9d6233b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348028"
---
# <a name="_ecvt"></a>_ecvt

Преобразует **двойное** число в строку. Существует более безопасная версия этой функции, см. раздел [_ecvt_s](ecvt-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Число, которое требуется преобразовать.

*count*<br/>
Сохраненное число разрядов.

*Декабря*<br/>
Сохраненная позиция десятичной запятой.

*Знак*<br/>
Знак преобразованного числа.

## <a name="return-value"></a>Возвращаемое значение

**_ecvt** возвращает указатель в строку цифр; **NULL,** если произошла ошибка.

## <a name="remarks"></a>Remarks

Функция **_ecvt** преобразует номер плавающей точки в строку символов. Параметр *значения* — это номер плавающей точки, который должен быть преобразован. Эта функция хранит до *подсчета* цифр *стоимости* в виде строки и придаткивает нулевой символ (''0'). Если число цифр в *значении* превышает *значение,* цифра низкого порядка округляется. Если цифр меньше числа *подсчетов,* строка набивается нулями.

Общее количество цифр, возвращенных **_ecvt,** не превысит **_CVTBUFSIZE.**

В строке сохраняются только цифры. Положение десятичной точки и знак *значения* могут быть получены с *декабря* и *знака* после вызова. Параметр *dec* указывает на величину, дающую положение десятичной точки по отношению к началу строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *знака* указывает на целый ряд, указывающий на знак преобразованного числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.

Разница между **_ecvt** и **_fcvt** заключается в интерпретации параметра *подсчета.* **_ecvt** интерпретирует *значение* как общее число цифр в строке вывода, в то время как **_fcvt** интерпретирует *значение* как число цифр после десятичной точки.

**_ecvt** и **_fcvt** использовать для преобразования единый статически выделенный буфер. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

Эта функция проверяет свои параметры. Если *dec* или *знак* **NULL**, или *количество* 0, недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **eINVAL** и **NULL** возвращается.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
