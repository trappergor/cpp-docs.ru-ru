---
title: fread
ms.date: 11/28/2018
apiname:
- fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 4f9cb6940d1708dffd5d5ca03fac28397f1db846
ms.sourcegitcommit: 53bfb772c43319d49686c167f492606348ad362b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2018
ms.locfileid: "52819700"
---
# <a name="fread"></a>fread

Считывает данные из потока.

## <a name="syntax"></a>Синтаксис

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения данных.

*size*<br/>
Размер элемента в байтах.

*count*<br/>
Максимальное число читаемых элементов.

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fread** возвращает число полных элементов фактически считанных, которые могут быть меньше, чем *число* при возникновении ошибки или если достигнут конец файла, до достижения *число*. Используйте **feof** или **ferror** функции, чтобы отличить ошибку чтения от условием окончания файла. Если *размер* или *число* равно 0, **fread** возвращает 0, а содержимое буфера не изменяются. Если *поток* или *буфера* является пустым указателем, **fread** вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает значение 0.

См. в разделе [ \_doserrno, errno, \_sys\_errlist, и \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Дополнительные сведения о эти коды ошибок.

## <a name="remarks"></a>Примечания

**Fread** функция считывает до *число* элементы *размер* байт из входного *поток* и хранит их в *буфера* . Файловый указатель, связанный с *поток* (если таковой имеется) увеличивается на число фактически считанных байтов. Если заданный поток открыт в [текстовый режим](../../c-runtime-library/text-and-binary-mode-file-i-o.md), новые строки в стиле Windows преобразуются в символы новой строки в стиле Unix. То есть пар каретки return-перевода строки (CRLF) заменяются символом перевода строки (LF). Замена не влияет на указатель файла или возвращаемое значение. В случае ошибки позиция указателя файла будет неопределенной. Значение частично считанного элемента не может быть определено.

При использовании в текстовый поток режим, если запрошенный объем данных (то есть *размер* \* *число*) больше или равным внутреннему **ФАЙЛ** \*размер буфера (по умолчанию это 4096 байт, можно настроить с помощью [setvbuf](../../c-runtime-library/reference/setvbuf.md)), потоковая передача данных копируется непосредственно в предоставляемый пользователем буфер, и выполняется преобразование символа новой строки в данном буфере. Так как преобразованные данные могут быть короче, чем поток данные, скопированные в буфер, последние данные *буфера*\[*return_value* \* *размер*] () где *return_value* является возвращаемым значением из **fread**) может содержать непреобразованных данные из файла. По этой причине мы рекомендуем вы завершите символьные данные в *буфера*\[*return_value* \* *размер*] Если предполагалось буфера в качестве строки в стиле C. См. в разделе [fopen](fopen-wfopen.md) Дополнительные сведения о последствиях текстовый режим и двоичном режиме.

Эта функция блокирует работу других потоков. Если вам нужна неблокирующей версии, используйте **_fread_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fread**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Ввод-вывод текста и двоичных файлов](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br />
[fopen](fopen-wfopen.md)<br />
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
