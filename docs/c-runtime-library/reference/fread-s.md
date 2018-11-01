---
title: fread_s
ms.date: 11/04/2016
apiname:
- fread_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fread_s
- stdio/fread_s
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
ms.openlocfilehash: 898e813c19fd53cfdacd536c2e9819743a62a8da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519825"
---
# <a name="freads"></a>fread_s

Считывает данные из потока. Это версия функции [fread](fread.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
size_t fread_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения данных.

*BufferSize*<br/>
Размер буфера назначения в байтах.

*elementSize*<br/>
Размер читаемого элемента в байтах.

*count*<br/>
Максимальное число читаемых элементов.

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fread_s** возвращает число (целое) элементы, которые были считаны в буфер, который может быть меньше, чем *число* возникали ли ошибки чтения или конец файла перед *число* достижения. Используйте **feof** или **ferror** функции, чтобы отличить ошибку от условием окончания файла. Если *размер* или *число* равно 0, **fread_s** возвращает 0, а содержимое буфера не изменяются. Если *поток* или *буфера* является пустым указателем, **fread_s** вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает значение 0.

Дополнительные сведения об этих кодах ошибки см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Fread_s** функция считывает до *число* элементы *elementSize* байт из входного *поток* и сохраняет их в *буфера*.  Указатель файла, с которым связан *поток* (если таковой имеется) увеличивается на число фактически считанных байтов. Если заданный поток открыт в текстовом режиме, пары "return-перевода строки каретки заменяются символом перевода строки. Замена не влияет на указатель файла или возвращаемое значение. В случае ошибки позиция указателя файла будет неопределенной. Значение частично считанного элемента не может быть определено.

Эта функция блокирует работу других потоков. Если требуется неблокирующей версии используйте **_fread_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fread_s**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// crt_fread_s.c
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c
//
// This program opens a file that's named FREAD.OUT and
// writes characters to the file. It then tries to open
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

#define BUFFERSIZE 30
#define DATASIZE 22
#define ELEMENTCOUNT 2
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)
#define FILENAME "FREAD.OUT"

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   for ( i = 0; i < DATASIZE; i++ )
      list[i] = (char)('z' - i);
   list[DATASIZE] = '\0'; // terminal null so we can print it

   // Open file in text mode:
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )
   {
      // Write DATASIZE characters to stream
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );
      printf( "Wrote %d items\n\n", numwritten );
      fclose( stream );
   } else {
      printf( "Problem opening the file\n" );
      return -1;
   }

   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {
      // Attempt to read in characters in 2 blocks of 11
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );
      printf( "Contents of buffer after write/read:\n\t%s\n", list );
      fclose( stream );
   } else {
      printf( "File could not be opened\n" );
      return -1;
   }
}
```

```Output
Contents of buffer before write/read:
        zyxwvutsrqponmlkjihgfe

Wrote 22 items

Number of 11-byte elements read = 2

Contents of buffer after write/read:
        zyxwvutsrqponmlkjihgfe
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
