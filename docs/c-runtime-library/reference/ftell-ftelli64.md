---
title: ftell, _ftelli64
ms.date: 11/04/2016
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: cc76ad0776ae82637b95d32cdc6254d3c40da5b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660529"
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64

Получает текущее положение указателя файла.

## <a name="syntax"></a>Синтаксис

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Целевой объект **ФАЙЛ** структуры.

## <a name="return-value"></a>Возвращаемое значение

**ftell** и **_ftelli64** возвращают текущее положение в файле. Значение, возвращенное **ftell** и **_ftelli64** может не отражать физическое смещение в байтах для потоков, открытых в текстовом режиме, так как в текстовом режиме производится преобразование перевода строки возврата каретки. Используйте **ftell** с [fseek](fseek-fseeki64.md) или **_ftelli64** с [_fseeki64](fseek-fseeki64.md) для правильного возврата к расположениям в файлах. В случае ошибки **ftell** и **_ftelli64** вызывают обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают – 1 L и устанавливают **errno** к одному из двух констант, определенных в ERRNO. З. **Значение EBADF** означает, что константа *поток* аргумента значение не является допустимым файлом указателя или не ссылается на открытый файл. **EINVAL** означает, что указан недопустимый *поток* аргумент, переданный в функцию. Неспособно выполнять поиск (например, терминалы и принтеры) или когда *поток* не ссылается на открытый файл, возвращаемое значение не определено.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Ftell** и **_ftelli64** функции извлекают текущую позицию указателя файла (если таковые имеются), связанные с *поток*. Позиция представляется как смещение относительно начала потока.

Обратите внимание, что когда файл открыт для добавления данных, текущее положение в файле определяется последней операцией ввода-вывода, а не тем, где должна быть произведена следующая запись. Например, если файл открыт для добавления и последней операцией было чтение, положением в файле является место, где должна начинаться следующая операция чтения, а не следующая операция записи. (Если файл открыт для добавления, положение в файле перемещается в конец файла перед любой операцией записи.) Если в открытом для добавления файле еще не производилась ни одна операция ввода-вывода, то положением в файле является начало файла.

В текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения/записи **fopen** и все связанные с ней подпрограммы наличие CTRL + Z в конце файла и удалите его, если это возможно. Это делается потому, что использование сочетания функций **ftell** и [fseek](fseek-fseeki64.md) или **_ftelli64** и [_fseeki64](fseek-fseeki64.md)для перемещения в файле, который заканчивается на CTRL + Z может привести к **ftell** или **_ftelli64** неправильное поведение ближе к концу файла.

Во время выполнения функция блокирует вызывающий поток, поэтому она потокобезопасна. Описание неблокирующей версии см. в разделе **_ftell_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательные заголовки|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
