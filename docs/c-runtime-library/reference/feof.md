---
title: feof
ms.date: 11/04/2016
api_name:
- feof
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
- feof
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
ms.openlocfilehash: cf6cfdb63689f5d69cc45dd407ecc6b08a7a7a73
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941133"
---
# <a name="feof"></a>feof

Определяет окончание файла в потоке.

## <a name="syntax"></a>Синтаксис

```C
int feof(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Функция **feof** возвращает ненулевое значение, если операция чтения попыталась прочитать после конца файла. в противном случае возвращается 0. Если указатель потока имеет **значение NULL**, функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** задается значение, а **feof** возвращает 0.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Подпрограммы **feof** (реализованные как функция и как макрос) определяют, был ли передан конец *потока* . После передачи конца файла операции чтения возвращают индикатор конца файла до закрытия потока или до тех пор, пока не будет закрыт поток или [пока не](rewind.md)будут вызваны **fsetpos**, [fseek](fseek-fseeki64.md)или **клеарерр** .

Например, если файл содержит 10 байт и вы читаете 10 байт из файла, **feof** возвратит 0, так как, даже если указатель файла находится в конце файла, вы не пытались прочитать его после конца. **Feof** возвращает ненулевое значение, только если вы попытаетесь прочитать 11-й байт.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**feof**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_feof.c
// This program uses feof to indicate when
// it reaches the end of the file CRT_FEOF.TXT. It also
// checks for errors with ferror.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int  count, total = 0;
   char buffer[100];
   FILE *stream;

   fopen_s( &stream, "crt_feof.txt", "r" );
   if( stream == NULL )
      exit( 1 );

   // Cycle until end of file reached:
   while( !feof( stream ) )
   {
      // Attempt to read in 100 bytes:
      count = fread( buffer, sizeof( char ), 100, stream );
      if( ferror( stream ) )      {
         perror( "Read error" );
         break;
      }

      // Total up actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   fclose( stream );
}
```

## <a name="input-crt_feoftxt"></a>Входные данные: crt_feof.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Number of bytes read = 19
```

## <a name="see-also"></a>См. также

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
