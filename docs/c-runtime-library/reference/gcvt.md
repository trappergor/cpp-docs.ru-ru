---
title: _gcvt
ms.date: 4/2/2020
api_name:
- _gcvt
- _o__gcvt
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
- _gcvt
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
ms.openlocfilehash: f161256c6dc86a045f49111cde3651bea08ead11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345318"
---
# <a name="_gcvt"></a>_gcvt

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

*value*<br/>
Преобразуемое значение.

*digits*<br/>
Количество значащих цифр хранятся.

*Буфера*<br/>
Место хранения результата.

## <a name="return-value"></a>Возвращаемое значение

**_gcvt** возвращает указатель в строку цифр.

## <a name="remarks"></a>Remarks

Функция **_gcvt** преобразует *значение* плавающей точки в строку символа (которая включает десятичную точку и возможный знак байт) и хранит строку в *буфере.* *Буфер* должен быть достаточно большим, чтобы вместить преобразованное значение плюс прекращающийся нулевой символ, который придатится автоматически. Если используется размер буфера *цифр* No 1, функция перезаписывает конец буфера. Это связано с тем, что преобразованная строка включает символ десятичной запятой и может содержать данные о знаке и степени. Ситуация переполнения не обрабатывается. **_gcvt** попытки производить *цифры* в десятичном формате. Если он не может, он производит *цифры* в экспоненциальном формате. Нули в конце могут исключаться из преобразования.

*Буфер* длины **_CVTBUFSIZE** достаточен для любого плавающего значения точки.

Эта функция проверяет свои параметры. Если *буфер* **NULL,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** **к EINVAL** и возвращает **NULL**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
