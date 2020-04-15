---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
ms.date: 4/2/2020
api_name:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
- _o__fstat32
- _o__fstat32i64
- _o__fstat64
- _o__fstat64i32
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 02d297fec2ada545a8b693abacfecc7981149dae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345672"
---
# <a name="_fstat-_fstat32-_fstat64-_fstati64-_fstat32i64-_fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

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

*Fd*<br/>
Дескриптор открытого файла.

*Буфера*<br/>
Указатель на структуру для хранения результатов.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Значение возврата -1 указывает на ошибку. Если дескриптор файла является недействительным или *буфер* **null,** вызовуется обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается на **EBADF**, в случае недействительного дескриптора файла, или **EINVAL**, если *буфер* **NULL.**

## <a name="remarks"></a>Remarks

Функция **_fstat** получает информацию об открытом файле, связанном с *fd,* и хранит его в структуре, на которую указывает *буфер.* Структура **_stat,** определяемая в SYS-Stat.h, содержит следующие поля.

|Поле|Значение|
|-|-|
| **st_atime** | Время последнего доступа к файлу. |
| **st_ctime** | Время создания файла. |
| **st_dev** | Если устройство, *fd*; в противном случае 0. |
| **st_mode** | Битовая маска для информации о файловом режиме. Бит **_S_IFCHR** устанавливается, если *fd* относится к устройству. Бит **_S_IFREG** устанавливается, если *fd* относится к обычному файлу. Биты чтения/записи устанавливаются в соответствии с режимом разрешений файла. **_S_IFCHR** и другие константы определяются в SYS-Stat.h. |
| **st_mtime** | Время последнего изменения файла. |
| **st_nlink** | Всегда имеет значение 1 в файловых системах, отличных от NTFS. |
| **st_rdev** | Если устройство, *fd*; в противном случае 0. |
| **st_size** | Размер файла в байтах. |

Если *fd* относится к устройству, **st_atime,** **st_ctime,** **st_mtime,** и **st_size** поля не имеют смысла.

Так как STAT.H использует тип [_dev_t](../../c-runtime-library/standard-types.md), который определен в Types.h, в коде необходимо включить Types.h перед Stat.h.

**_fstat64**, который использует **__stat64** структуру, позволяет датам создания файлов быть выражены через 23:59:59, 31 декабря 3000, UTC; в то время как другие функции представляют даты только до 23:59:59 18 января 2038, UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.

Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные размеры файлов. Первый численный суффикс **(32** или **64)** указывает размер используемого типа времени; второй суффикс — это **i32** или **i64,** указывающий на то, представлен ли размер файла как 32-битный или 64-разрядный целый ряд.

**_fstat** эквивалентно **_fstat64i32,** а **_stat структурируется,** **_stat** содержит 64-битное время. Это верно, если **_USE_32BIT_TIME_T** не определена, и в этом случае старое поведение действует; **_fstat** использует 32-битное время, а **_stat структурировать** **содержит** 32-битное время. То же самое относится и к **_fstati64**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>Варианты типов времени и типов длины файлов в функции _stat

|Функции|Определена ли директива _USE_32BIT_TIME_T?|Тип времени|Тип длины файла|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Не определено|64-разрядная|32-битная|
|**_fstat**|Определено|32-битная|32-битная|
|**_fstat32**|Не затрагивается определением макроса|32-битная|32-битная|
|**_fstat64**|Не затрагивается определением макроса|64-разрядная|64-разрядная|
|**_fstati64**|Не определено|64-разрядная|64-разрядная|
|**_fstati64**|Определено|32-битная|64-разрядная|
|**_fstat32i64**|Не затрагивается определением макроса|32-битная|64-разрядная|
|**_fstat64i32**|Не затрагивается определением макроса|64-разрядная|32-битная|

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fstat**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat32**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstati64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat32i64**|\<sys/stat.h> и \<sys/types.h>|
|**_fstat64i32**|\<sys/stat.h> и \<sys/types.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[Функции _stat, _wstat](stat-functions.md)<br/>
