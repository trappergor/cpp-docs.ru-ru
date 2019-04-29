---
title: _fcvt
ms.date: 04/05/2018
apiname:
- _fcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: ae9323e3bb629fd61b35a8c844b00bfcc73235bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334844"
---
# <a name="fcvt"></a>_fcvt

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

*dec*<br/>
Указатель на сохраненную позицию десятичной запятой.

*sign*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

**_fcvt** возвращает указатель на строку разрядов или **NULL** в случае ошибки.

## <a name="remarks"></a>Примечания

**_Fcvt** функция преобразует число с плавающей запятой в строку символов с завершающим нулем. *Значение* параметром является номер с плавающей запятой для преобразования. **_fcvt** сохраняет цифры *значение* как строку и добавляет нуль-символ («\0»). *Число* указывает количество цифр, сохраняемых после десятичной запятой. Избыточные цифры округляются до *число* помещает. Если доступно менее *число* запятой, строка дополняется нулями.

Общее число разрядов, возвращаемое **_fcvt** не может превышать **_CVTBUFSIZE**.

В строке сохраняются только цифры. Положение десятичной запятой и знак *значение* можно получить из *dec* и sign после вызова. *Dec* параметр указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *входа* указывает на целое число, определяющее знак *значение*. Целое число имеет значение 0, если *значение* положительно и ненулевое значение, если задано значение *значение* является отрицательным.

Разница между **_ecvt** и **_fcvt** в интерпретацию *число* параметра. **_ecvt** интерпретирует *число* как общее число цифр в выходной строке, тогда как **_fcvt** интерпретирует *число* как количество цифр после десятичной запятой.

**_ecvt** и **_fcvt** используют для преобразования один статически выделенный буфер. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

Эта функция проверяет свои параметры. Если *dec* или *входа* — **NULL**, или *число* равно 0, вызывается обработчик недопустимого параметра, как описано в разделе [параметр Проверка](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и **NULL** возвращается.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
