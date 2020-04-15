---
title: clearerr
ms.date: 4/2/2020
api_name:
- clearerr
- _o_clearerr
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clearerr
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
ms.openlocfilehash: 174c94136cdc8b603416ff1dd239703489925bae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350029"
---
# <a name="clearerr"></a>clearerr

Сбрасывает индикатор ошибки для потока. Существует более безопасная версия этой функции, см. раздел [clearerr_s](clearerr-s.md).

## <a name="syntax"></a>Синтаксис

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="remarks"></a>Remarks

Функция **clearerr** сбрасывает индикатор ошибки и индикатор конца файла для *потока.* Индикаторы ошибки не очищаются автоматически; как только индикатор ошибки для указанного потока установлен, операции в этом потоке продолжают возвращать значение ошибки до тех пор, пока не будет вызван **осекретание,** [fseek,](fseek-fseeki64.md) **fsetpos**или [перемотка назад.](rewind.md)

Если *поток* **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает. Для получения дополнительной информации о **errno** и коды ошибок, см [Errno Констанс](../../c-runtime-library/errno-constants.md).

Существует более безопасная версия этой функции, см. раздел [clearerr_s](clearerr-s.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

### <a name="input"></a>Входные данные

```Input
n
```

### <a name="output"></a>Выходные данные

```Output
Write error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>См. также раздел

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
