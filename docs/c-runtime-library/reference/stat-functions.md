---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
ms.date: 4/2/2020
api_name:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
- _o__stat32
- _o__stat32i64
- _o__stat64
- _o__stat64i32
- _o__wstat32
- _o__wstat32i64
- _o__wstat64
- _o__wstat64i32
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
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
ms.openlocfilehash: 32a96a93eb8a18e366ac7a075b414dbca732fb61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355419"
---
# <a name="_stat-_stat32-_stat64-_stati64-_stat32i64-_stat64i32-_wstat-_wstat32-_wstat64-_wstati64-_wstat32i64-_wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

Получает сведения о состоянии файла.

## <a name="syntax"></a>Синтаксис

```C
int _stat(
   const char *path,
   struct _stat *buffer
);
int _stat32(
   const char *path,
   struct __stat32 *buffer
);
int _stat64(
   const char *path,
   struct __stat64 *buffer
);
int _stati64(
   const char *path,
   struct _stati64 *buffer
);
int _stat32i64(
   const char *path,
   struct _stat32i64 *buffer
);
int _stat64i32(
   const char *path,
   struct _stat64i32 *buffer
);
int _wstat(
   const wchar_t *path,
   struct _stat *buffer
);
int _wstat32(
   const wchar_t *path,
   struct __stat32 *buffer
);
int _wstat64(
   const wchar_t *path,
   struct __stat64 *buffer
);
int _wstati64(
   const wchar_t *path,
   struct _stati64 *buffer
);
int _wstat32i64(
   const wchar_t *path,
   struct _stat32i64 *buffer
);
int _wstat64i32(
   const wchar_t *path,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>Параметры

*Путь*<br/>
Указатель на строку, содержащую путь к существующему файлу или каталогу.

*Буфера*<br/>
Указатель на структуру, в которой хранятся результаты.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Значение возврата -1 указывает на ошибку, и в этом случае **errno** устанавливается **на ENOENT,** указывая, что имя файла или путь не может быть найдено. Значение возврата **EINVAL** указывает на недействительный параметр; **errno** также установлен на **EINVAL** в этом случае.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

Штамп даты на файле может быть представлен, если он находится позднее полуночи, 1 января 1970 года, и до 23:59:59, 31 декабря 3000, UTC, если вы не используете **_stat32** или **_wstat32,** или определили **_USE_32BIT_TIME_T**, и в этом случае дата может быть представлена только до 23:59:59 18 января 2038, UTC.

## <a name="remarks"></a>Remarks

Функция **_stat** получает информацию о файле или каталоге, указанном *по пути,* и хранит ее в структуре, указанной *буфером.* **_stat** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтовым кодом, который используется в настоящее время.

**_wstat** является широкохарактерным вариантом **_stat;** *аргумент пути* к **_wstat** является широкохарактерной строкой. **_wstat** и **_stat** ведут себя одинаково, за исключением того, что **_wstat** не обрабатывает строки с мультибайт-символами.

Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные значения длины файлов. Первый численный суффикс **(32** или **64)** указывает размер используемого типа времени; второй суффикс — это **i32** или **i64,** указывающий на то, представлен ли размер файла как 32-битный или 64-разрядный целый ряд.

**_stat** эквивалентен **_stat64i32,** а **_stat структурируется,** **_stat** содержит 64-битное время. Это верно, если **_USE_32BIT_TIME_T** не определена, и в этом случае старое поведение действует; **_stat** использует 32-битное время, а **_stat структурировать** **содержит** 32-битное время. То же самое верно и для **_stati64**.

> [!NOTE]
> **_wstat** не работает с Windows Vista символические ссылки. В этих случаях **_wstat** всегда будете сообщать о размере файла 0. **_stat** работает правильно с символическими ссылками.

Эта функция проверяет свои параметры. Если *какой-либо путь* или *буфер* **NULL,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md)

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>Варианты типов времени и типов длины файлов в функции _stat

|Функции|Определена ли директива _USE_32BIT_TIME_T?|Тип времени|Тип длины файла|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|Не определено|64-разрядная|32-битная|
|**_stat**, **_wstat**|Определено|32-битная|32-битная|
|**_stat32**, **_wstat32**|Не затрагивается определением макроса|32-битная|32-битная|
|**_stat64**, **_wstat64**|Не затрагивается определением макроса|64-разрядная|64-разрядная|
|**_stati64**, **_wstati64**|Не определено|64-разрядная|64-разрядная|
|**_stati64**, **_wstati64**|Определено|32-битная|64-разрядная|
|**_stat32i64**, **_wstat32i64**|Не затрагивается определением макроса|32-битная|64-разрядная|
|**_stat64i32**, **_wstat64i32**|Не затрагивается определением макроса|64-разрядная|32-битная|

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

Структура **_stat,** определяемая в SYS-STAT. H, включает в себя следующие поля.

|Поле||
|-|-|
| **st_gid** | Числовой идентификатор группы, которой принадлежит файл (только для UNIX). В системах Windows это поле всегда равно нулю. Перенаправленный файл классифицируется как файл Windows. |
| **st_atime** | Время последнего доступа к файлу. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT. |
| **st_ctime** | Время создания файла. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT. |
| **st_dev** | Номер диска диска, содержащий файл (так же, как **st_rdev).** |
| **st_ino** | Номер информационного узла **(inode)** для файла (специфический UNIX). В файловых системах UNIX **inode** описывает дату и временные штампы, разрешения и содержимое. Когда файлы тесно связаны друг с другом, они имеют один и тот же **inode**. **Inode**, и, **следовательно, st_ino**, не имеет смысла в FAT, HPFS, или NTFS файловых систем. |
| **st_mode** | Битовая маска для информации о файловом режиме. Бит **_S_IFDIR** устанавливается, если *путь* определяет каталог; **_S_IFREG** бит устанавливается, если *путь* определяет обычный файл или устройство. Пользовательские биты чтения/записи устанавливаются в соответствии с режимом разрешений файла; пользовательские биты выполнения устанавливаются согласно расширению имени файла. |
| **st_mtime** | Время последнего изменения файла. |
| **st_nlink** | Всегда имеет значение 1 в файловых системах, отличных от NTFS. |
| **st_rdev** | Номер диска диска, содержащий файл (так же, как **st_dev).** |
| **st_size** | Размер файла в байтах; 64-битный ряд для вариаций с суффиксом **i64.** |
| **st_uid** | Числовой идентификатор пользователя, который владеет файлом (только для UNIX). В системах Windows это поле всегда будет равно нулю. Перенаправленный файл классифицируется как файл Windows. |

Если *путь* относится к устройству, **то st_size,** различные поля времени, **st_dev**и **st_rdev** поля в **структуре _stat** бессмысленны. Поскольку STAT.H использует тип [_dev_t](../../c-runtime-library/standard-types.md), который определен в TYPES.H, в коде необходимо включить TYPES.H перед STAT.H.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_stat,** **_stat32,** **_stat64,** **_stati64,** **_stat32i64,** **_stat64i32**|\<sys/types.h>, затем \<sys/stat.h>|\<errno.h>|
|**_wstat,** **_wstat32,** **_wstat64,** **_wstati64,** **_wstat32i64,** **_wstat64i32**|\<sys/types.h>, затем \<sys/stat.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_stat.c
// This program uses the _stat function to
// report information about the file named crt_stat.c.

#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
   struct _stat buf;
   int result;
   char timebuf[26];
   char* filename = "crt_stat.c";
   errno_t err;

   // Get data associated with "crt_stat.c":
   result = _stat( filename, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      perror( "Problem getting information" );
      switch (errno)
      {
         case ENOENT:
           printf("File %s not found.\n", filename);
           break;
         case EINVAL:
           printf("Invalid parameter to _stat.\n");
           break;
         default:
           /* Should never be reached. */
           printf("Unexpected error in _stat.\n");
      }
   }
   else
   {
      // Output some of the statistics:
      printf( "File size     : %ld\n", buf.st_size );
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid arguments to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
}
```

```Output
File size     : 732
Drive         : C:
Time modified : Thu Feb 07 14:39:36 2002
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
