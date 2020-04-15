---
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: a017ed58b962520793d5b10b088793dbc9b8a83d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347427"
---
# <a name="_fcvt"></a>_fcvt

Преобразует число с плавающей запятой в строку. Существует более безопасная версия этой функции, см. раздел [_fcvt_s](fcvt-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_fcvt(
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
Число разрядов после десятичной запятой.

*Декабря*<br/>
Указатель на сохраненную позицию десятичной запятой.

*Знак*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

**_fcvt** возвращает указатель в строку цифр, **NULL** по ошибке.

## <a name="remarks"></a>Remarks

Функция **_fcvt** преобразует номер плавающей точки в строку символов с нулевым завершением. Параметр *значения* — это номер плавающей точки, который должен быть преобразован. **_fcvt** хранит цифры *ценности* в виде строки и придатки нулевой символ (''0'). Параметр *подсчета* определяет количество цифр, которые будут храниться после десятичной точки. Избыточные цифры округлены для *подсчета* мест. Если количество *точного* количества меньше, строка набивается нулями.

Общее количество цифр, возвращенных **_fcvt,** не превысит **_CVTBUFSIZE.**

В строке сохраняются только цифры. Положение десятичной точки и знак *значения* могут быть получены с *декабря* и знака после вызова. Параметр *dec* указывает на величину всей сделки; это значение рядом дает положение десятичной точки по отношению к началу строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. *Знак* параметра указывает на несколько с указанием знака *значения.* Целый ряд устанавливается до 0, если *значение* положительное и устанавливается на ненулевое число, если *значение* отрицательное.

Разница между **_ecvt** и **_fcvt** заключается в интерпретации параметра *подсчета.* **_ecvt** интерпретирует *значение* как общее число цифр в строке вывода, в то время как **_fcvt** интерпретирует *значение* как число цифр после десятичной точки.

**_ecvt** и **_fcvt** использовать для преобразования единый статически выделенный буфер. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

Эта функция проверяет свои параметры. Если *dec* или *знак* **NULL**, или *количество* 0, недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **eINVAL** и **NULL** возвращается.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
