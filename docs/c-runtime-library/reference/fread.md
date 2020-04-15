---
title: fread
ms.date: 4/2/2020
api_name:
- fread
- _o_fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 26ffd56072f1a5fddc3131a42cd47c145e437b60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346056"
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

*Буфера*<br/>
Место хранения данных.

*Размер*<br/>
Размер элемента в байтах.

*count*<br/>
Максимальное число читаемых элементов.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fread** возвращает количество полных элементов на самом деле читать, что может быть меньше, чем *рассчитывать,* если ошибка происходит или если конец файла встречается до достижения *кол.* Используйте функцию **feof** или **ferror,** чтобы отличить ошибку чтения от состояния конца файла. Если *размер* или *количество 0,* **fread** возвращает сярвые 0 и содержимое буфера неизменны. Если *поток* или *буфер* является нулевой указатель, **fread** вызывает недействительным обработчик параметров, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает 0.

Смотрите [ \_ \_doserrno, errno,\_sys \_errlist,\_и sys nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) для получения дополнительной информации об этих кодах ошибок.

## <a name="remarks"></a>Remarks

Функция **fread** считывает *элементы* *размербайсовых* байтов из входному *потока* и хранит их в *буфере.* Указатель файла, связанный с *потоком* (если он есть) увеличивается на количество байтов на самом деле читать. Если данный поток открыт в [текстовом режиме,](../../c-runtime-library/text-and-binary-mode-file-i-o.md)новые линии в стиле Windows преобразуются в newlines в стиле Unix. То есть пары каретной линии возврата (CRLF) заменяются символами подачи одной линии (LF). Замена не влияет на указатель файла или возвращаемое значение. В случае ошибки позиция указателя файла будет неопределенной. Значение частично считанного элемента не может быть определено.

При использовании в потоке текстового режима, если объем запрошенных данных (т.е. *количество* *размеров)* \* больше или равен внутреннему размеру буфера **FILE** \* (по умолчанию это 4096 байтов, настраиваемый с помощью [setvbuf),](../../c-runtime-library/reference/setvbuf.md)данные потока копируются непосредственно в предоставленный пользователем буфер, и преобразование новой строки выполняется в этом буфере. Так как преобразованные данные могут быть короче, чем данные потока, скопированные в буфер, данные, прошедшие *с буфера*\[*return_value* \* *размер*(где *return_value* значение возврата от **fread)** могут содержать неконвертированные данные из файла. По этой причине мы рекомендуем вам данные символов с нулевым завершением *в*\[буфере*return_value* \* *размер,* если цель буфера состоит в том, чтобы выступать в качестве строки C-стиля. Смотрите [fopen](fopen-wfopen.md) для получения подробной информации о последствиях текстового режима и двоичного режима.

Эта функция блокирует работу других потоков. Если вам нужна незапирирующая версия, используйте **_fread_nolock**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fread**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Текст и двоичный файл вв/o](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
