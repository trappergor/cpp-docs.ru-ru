---
title: "_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
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
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c84ed9e6ad7edab34dc80a4d2b446b7333f95c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
Получает сведения о состоянии файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Указатель на строку, содержащую путь к существующему файлу или каталогу.  
  
 `buffer`  
 Указатель на структуру, в которой хранятся результаты.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Возвращаемое значение-1 указывает на ошибку в этом случае `errno` равно `ENOENT`, указывающее, что имя файла или путь не найден. Возвращаемое значение `EINVAL` указывает на недопустимый параметр; в этом случае параметр `errno` также принимает значение `EINVAL` .  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .  
  
 Отметка даты в файле может быть представлена, если она позже полуночи 1-го января 1970 года и раньше 23:59:59 31-го декабря 3000 года по UTC, если только не используется функция `_stat32` или `_wstat32` или не определена директива `_USE_32BIT_TIME_T` — в этом случае дата может быть представлена только до 23:59:59 18-го января 2038 года по UTC.  
  
## <a name="remarks"></a>Примечания  
 Функция `_stat` получает сведения о файле или каталоге, указанном параметром `path` , и сохраняет их в структуре, указанной в параметре `buffer`. Функция`_stat` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей.  
  
 `_wstat` — это версия `_stat`с расширенными символами; аргумент `path` для `_wstat` — строка расширенных символов. В остальных отношениях поведение функций`_wstat` и `_stat` идентично, за исключением того, что функция `_wstat` does not hиle multibyte-character strings.  
  
 Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные значения длины файлов. Первый числовой суффикс (`32` или `64`) указывает размер используемого типа времени; второй суффикс `i32` или `i64`показывает, представлен ли размер файла как 32- или 64-разрядное целое число.  
  
 `_stat` эквивалентна функции `_stat64i32`, и `struct _stat` содержит 64-разрядное время. Это верно, если не задана директива `_USE_32BIT_TIME_T` ; в противном случае действует старое поведение: функция `_stat` использует 32-разрядное время, и `struct _stat` содержит 32-разрядное время. Это же справедливо и для `_stati64`.  
  
> [!NOTE]
>  Функция `_wstat` не работает с символьными ссылками [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. В таких случаях функция `_wstat` всегда возвращает размер файла, равный 0. Функция`_stat` правильно работает с символьными ссылками.  
  
 Эта функция проверяет свои параметры. Если параметр `path` или `buffer` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в [Parameter Validation](../../c-runtime-library/parameter-validation.md).  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>Варианты типов времени и типов длины файлов в функции _stat  
  
|Функции|Определена ли директива _USE_32BIT_TIME_T?|Тип времени|Тип длины файла|  
|---------------|------------------------------------|---------------|----------------------|  
|`_stat`, `_wstat`|Не определено|64-разрядная версия|32-разрядная версия|  
|`_stat`, `_wstat`|Определено|32-разрядная|32-разрядная версия|  
|`_stat32`, `_wstat32`|Не затрагивается определением макроса|32-разрядная|32-разрядная версия|  
|`_stat64`, `_wstat64`|Не затрагивается определением макроса|64-разрядная версия|64-разрядная версия|  
|`_stati64`, `_wstati64`|Не определено|64-разрядная|64-разрядная версия|  
|`_stati64`, `_wstati64`|Определено|32-разрядная версия|64-разрядная версия|  
|`_stat32i64`, `_wstat32i64`|Не затрагивается определением макроса|32-разрядная версия|64-разрядная версия|  
|`_stat64i32`, `_wstat64i32`|Не затрагивается определением макроса|64-разрядная версия|32-разрядная|  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 Структура `_stat` , определенная в SYS\STAT.H, включает следующие поля.  
  
 `st_gid`  
 Числовой идентификатор группы, которой принадлежит файл (только для UNIX). В системах Windows это поле всегда равно нулю. Перенаправленный файл классифицируется как файл Windows.  
  
 `st_atime`  
 Время последнего доступа к файлу. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT.  
  
 `st_ctime`  
 Время создания файла. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT.  
  
 `st_dev`  
 Номер диска, содержащего файл (то же, что и `st_rdev`).  
  
 `st_ino`  
 Номер узла информации ( `inode`) для файла (только для UNIX). В файловых системах UNIX параметр `inode` описывает отметки даты и времени файла, разрешения и содержимое. Если файлы связаны жесткими ссылками друг с другом, они имеют один и тот же параметр `inode`. Параметр `inode`и, следовательно, параметр `st_ino`не имеют смысла в файловых системах FAT, HPFS и NTFS.  
  
 `st_mode`  
 Битовая маска для информации о файловом режиме. Бит `_S_IFDIR` устанавливается, если параметр `path` задает каталог; бит `_S_IFREG` устанавливается, если параметр `path` задает обычный файл или устройство. Пользовательские биты чтения/записи устанавливаются в соответствии с режимом разрешений файла; пользовательские биты выполнения устанавливаются согласно расширению имени файла.  
  
 `st_mtime`  
 Время последнего изменения файла.  
  
 `st_nlink`  
 Всегда имеет значение 1 в файловых системах, отличных от NTFS.  
  
 `st_rdev`  
 Номер диска, содержащего файл (то же, что и `st_dev`).  
  
 `st_size`  
 Размер файла в байтах; 64-разрядное целое число для вариантов с суффиксом `i64` suffix**.**  
  
 `st_uid`  
 Числовой идентификатор пользователя, который владеет файлом (только для UNIX). В системах Windows это поле всегда будет равно нулю. Перенаправленный файл классифицируется как файл Windows.  
  
 Если параметр `path` ссылается на устройство, поле `st_size`, различные поля времени, поля `st_dev`и `st_rdev` в структуре `_stat` не имеют смысла. Поскольку STAT.H использует тип [_dev_t](../../c-runtime-library/standard-types.md), который определен в TYPES.H, в коде необходимо включить TYPES.H перед STAT.H.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys/types.h>, затем \<sys/stat.h>|\<errno.h>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys/types.h>, затем \<sys/stat.h> или \<wchar.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)