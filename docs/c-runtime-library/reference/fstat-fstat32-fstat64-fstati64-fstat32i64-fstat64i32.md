---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
ms.date: 11/04/2016
apiname:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
ms.openlocfilehash: 2cec64e408b326dccc7b950656d0aa699c084f83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677790"
---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

Получает сведения об открытом файле.

## <a name="syntax"></a>Синтаксис

```C
int _fstat(
   int fd,
   struct _stat *buffer
);
int _fstat32(
   int fd,
   struct __stat32 *buffer
);
int _fstat64(
   int fd,
   struct __stat64 *buffer
);
int _fstati64(
   int fd,
   struct _stati64 *buffer
);
int _fstat32i64(
   int fd,
   struct _stat32i64 *buffer
);
int _fstat64i32(
   int fd,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор открытого файла.

*buffer*<br/>
Указатель на структуру для хранения результатов.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Возвращаемое значение-1 указывает на ошибку. Если дескриптор файла является недопустимым или *буфера* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **значение EBADF**, в случае недопустимого дескриптора файла, или к **EINVAL**, если *буфера* — **NULL**.

## <a name="remarks"></a>Примечания

**_Fstat** функция получает сведения о открытого файла, связанного с *fd* и сохраняет их в структуре, на которые указывают *буфера*. **_Stat** структура, определенная в SYS\Stat.h, включает следующие поля.

|Поле|Значение|
|-|-|
**st_atime**|Время последнего доступа к файлу.
**st_ctime**|Время создания файла.
**st_dev**|Если устройство, *fd*; в противном случае — 0.
**st_mode**|Битовая маска для информации о файловом режиме. **_S_IFCHR** бит устанавливается в том случае, если *fd* ссылается на устройство. **_S_IFREG** бит устанавливается в том случае, если *fd* ссылается на обычный файл. Биты чтения/записи устанавливаются в соответствии с режимом разрешений файла. **_S_IFCHR** и другие константы определены в файле SYS\Stat.h.
**st_mtime**|Время последнего изменения файла.
**st_nlink**|Всегда имеет значение 1 в файловых системах, отличных от NTFS.
**st_rdev**|Если устройство, *fd*; в противном случае — 0.
**st_size**|Размер файла в байтах.

Если *fd* ссылается на устройство, **st_atime**, **st_ctime**, **st_mtime**, и **st_size** поля не применяется.

Так как STAT.H использует тип [_dev_t](../../c-runtime-library/standard-types.md), который определен в Types.h, в коде необходимо включить Types.h перед Stat.h.

**_fstat64**, которая использует **__stat64** структуры, поддерживает даты создания файла можно выразить через 23:59:59 31 декабря 3000 года в формате UTC; при этом функция других функций представляет даты только до 23:59:59 18 января 2038 ГОДА В ФОРМАТЕ UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.

Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные размеры файлов. Первый числовой суффикс (**32** или **64**) указывает размер времени используется тип; второй суффикс **i32** или **i64**, указывающее, представлен ли размер файла как 32-разрядная или 64-разрядное целое число.

**_fstat** эквивалентен **_fstat64i32**, и **структуры** **_stat** содержит 64-разрядное время. Это значение true, если не **_USE_32BIT_TIME_T** задана, в этом случае старое поведение. **_fstat** использует 32-разрядное время, и **структуры** **_stat** содержит 32-разрядное время. То же самое касается **_fstati64**.

### <a name="time-type-and-file-length-type-variations-of-stat"></a>Варианты типов времени и типов длины файлов в функции _stat

|Функции|Определена ли директива _USE_32BIT_TIME_T?|Тип времени|Тип длины файла|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Не определено|64-разрядная версия|32-разрядная версия|
|**_fstat**|Определено|32-разрядная|32-разрядная версия|
|**_fstat32**|Не затрагивается определением макроса|32-разрядная|32-разрядная версия|
|**_fstat64**|Не затрагивается определением макроса|64-разрядная версия|64-разрядная версия|
|**_fstati64**|Не определено|64-разрядная|64-разрядная версия|
|**_fstati64**|Определено|32-разрядная версия|64-разрядная версия|
|**_fstat32i64**|Не затрагивается определением макроса|32-разрядная версия|64-разрядная версия|
|**_fstat64i32**|Не затрагивается определением макроса|64-разрядная версия|32-разрядная версия|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fstat**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat32**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstati64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat32i64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat64i32**|\<sys/stat.h> и \<sys/types.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fstat.c
// This program uses _fstat to report
// the size of a file named F_STAT.OUT.

#include <io.h>
#include <fcntl.h>
#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <errno.h>
#include <share.h>

int main( void )
{
   struct _stat buf;
   int fd, result;
   char buffer[] = "A line to output";
   char timebuf[26];
   errno_t err;

   _sopen_s( &fd,
             "f_stat.out",
             _O_CREAT | _O_WRONLY | _O_TRUNC,
             _SH_DENYNO,
             _S_IREAD | _S_IWRITE );
   if( fd != -1 )
      _write( fd, buffer, strlen( buffer ) );

   // Get data associated with "fd":
   result = _fstat( fd, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      if (errno == EBADF)
        printf( "Bad file descriptor.\n" );
      else if (errno == EINVAL)
        printf( "Invalid argument to _fstat.\n" );
   }
   else
   {
      printf( "File size     : %ld\n", buf.st_size );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid argument to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
   _close( fd );
}
```

```Output
File size     : 16
Time modified : Wed May 07 15:25:11 2003
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[_stat, _wstat Functions](stat-functions.md)<br/>
