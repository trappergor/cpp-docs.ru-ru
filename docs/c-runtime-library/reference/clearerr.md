---
title: clearerr
ms.date: 11/04/2016
api_name:
- clearerr
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
ms.openlocfilehash: 9fd2f7e7dfcf272e806a887b356418b7555913f5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942952"
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

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="remarks"></a>Примечания

Функция **клеарерр** сбрасывает индикатор ошибки и индикатор конца файла для *Stream*. Индикаторы ошибок не очищаются автоматически; После того как индикатор ошибки для указанного потока установлен, операции в этом потоке продолжают возвращать значение ошибки до тех пор, пока не будет вызван **клеарерр**, [fseek](fseek-fseeki64.md), **fsetpos**или [Rewind](rewind.md) .

Если *Stream* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **еинвал** и возвращает. Дополнительные **сведения о кодах ошибок и код** ошибки см. в разделе " [константы](../../c-runtime-library/errno-constants.md)".

Существует более безопасная версия этой функции, см. раздел [clearerr_s](clearerr-s.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

### <a name="input"></a>Ввод

```Input
n
```

### <a name="output"></a>Вывод

```Output
Write error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>См. также

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
