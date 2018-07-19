---
title: _gcvt | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gcvt
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
- _gcvt
dev_langs:
- C++
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d824d42a102aee68619d602044c39f398af177dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400984"
---
# <a name="gcvt"></a>_gcvt

Преобразует значение с плавающей запятой в строку и сохраняет ее в буфер. Существует более безопасная версия этой функции; см. раздел [_gcvt_s](gcvt-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_gcvt(
   double value,
   int digits,
   char *buffer
);
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Преобразуемое значение.

*digits*<br/>
Количество значащих цифр хранятся.

*buffer*<br/>
Место хранения результата.

## <a name="return-value"></a>Возвращаемое значение

**_gcvt** возвращает указатель на строку знаков.

## <a name="remarks"></a>Примечания

**_Gcvt** функция преобразования с плавающей запятой *значение* в символьную строку (которая включает десятичной запятой и возможности входа байта) и сохраняет строки в *буфера*. *Буфера* должно быть достаточно большим, чтобы вместить преобразованное значение плюс завершающий нуль-символ, который добавляется автоматически. Если размер буфера *цифр* + 1 используется, функция перезаписывает конца буфера. Это связано с тем, что преобразованная строка включает символ десятичной запятой и может содержать данные о знаке и степени. Ситуация переполнения не обрабатывается. **_gcvt** пытается создать *цифр* разрядов в десятичном формате. Если не удается, он создает *цифр* цифр в экспоненциальном формате. Нули в конце могут исключаться из преобразования.

Объект *буфера* длины **_CVTBUFSIZE** достаточно для любого числа с плавающей запятой.

Эта функция проверяет свои параметры. Если *буфера* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **NULL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_gcvt.c
// compile with: /W3
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   char buffer[_CVTBUFSIZE];
   double value = -1234567890.123;
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );
   _gcvt( value, 12, buffer ); // C4996
   // Note: _gcvt is deprecated; consider using _gcvt_s instead
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );

   printf( "\n" );
   value = -12.34567890123;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
}
```

```Output
The following numbers were converted by _gcvt(value,12,buffer):
buffer: '-1234567890.12' (14 chars)
buffer: '-12345678901.2' (14 chars)
buffer: '-123456789012' (13 chars)
buffer: '-1.23456789012e+012' (19 chars)

buffer: '-12.3456789012' (14 chars)
buffer: '-1.23456789012' (14 chars)
buffer: '-0.123456789012' (15 chars)
buffer: '-1.23456789012e-002' (19 chars)
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
