---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4bf1e3ad35fb03891f9c861255919752d0403d70
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
Получает сведения об открытом файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `fd`  
 Дескриптор открытого файла.  
  
 `buffer`  
 Указатель на структуру для хранения результатов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Возвращаемое значение-1 указывает на ошибку. Если задан недопустимый дескриптор файла или параметр `buffer` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, `errno` принимает значение `EBADF`, что указывает на недопустимый дескриптор файла, либо `EINVAL`, если параметр `buffer` имеет значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_fstat` получает сведения об открытом файле, который связан с `fd`, и сохраняет их в структуре, указанной в параметре `buffer`. Структура `_stat`, определенная в SYS\Stat.h, включает следующие поля.  
  
 `st_atime`  
 Время последнего доступа к файлу.  
  
 `st_ctime`  
 Время создания файла.  
  
 `st_dev`  
 Для устройства равно `fd`, в противном случае — 0.  
  
 `st_mode`  
 Битовая маска для информации о файловом режиме. Бит `_S_IFCHR` устанавливается в том случае, если `fd` ссылается на устройство. Бит `_S_IFREG` устанавливается в том случае, если `fd` ссылается на обычный файл. Биты чтения/записи устанавливаются в соответствии с режимом разрешений файла. `_S_IFCHR` и другие константы определены в файле SYS\Stat.h.  
  
 `st_mtime`  
 Время последнего изменения файла.  
  
 `st_nlink`  
 Всегда имеет значение 1 в файловых системах, отличных от NTFS.  
  
 `st_rdev`  
 Для устройства равно `fd`, в противном случае — 0.  
  
 `st_size`  
 Размер файла в байтах.  
  
 Если `fd` ссылается на устройство, поля `st_atime`, `st_ctime`, `st_mtime` и `st_size` не содержат значащей информации.  
  
 Так как STAT.H использует тип [_dev_t](../../c-runtime-library/standard-types.md), который определен в Types.h, в коде необходимо включить Types.h перед Stat.h.  
  
 Функция `_fstat64`, которая использует структуру `__stat64`, поддерживает даты создания файла до 23:59:59 31 декабря 3000 года в формате UTC. При этом другие функции представляют даты только до 23:59:59 18 января 2038 года в формате UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.  
  
 Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные размеры файлов. Первый числовой суффикс (`32` или `64`) указывает размер используемого типа времени; второй суффикс `i32` или `i64`показывает, представлен ли размер файла как 32- или 64-разрядное целое число.  
  
 `_fstat` эквивалентна функции `_fstat64i32`, и `struct _stat` содержит 64-разрядное время. Это верно, если не задана директива `_USE_32BIT_TIME_T` ; в противном случае действует старое поведение: функция `_fstat` использует 32-разрядное время, и `struct _stat` содержит 32-разрядное время. Это же справедливо и для `_fstati64`.  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>Варианты типов времени и типов длины файлов в функции _stat  
  
|Функции|Определена ли директива _USE_32BIT_TIME_T?|Тип времени|Тип длины файла|  
|---------------|------------------------------------|---------------|----------------------|  
|`_fstat`|Не определено|64-разрядная|32-разрядная|  
|`_fstat`|Определено|32-разрядная|32-разрядная|  
|`_fstat32`|Не затрагивается определением макроса|32-разрядная|32-разрядная|  
|`_fstat64`|Не затрагивается определением макроса|64-разрядная|64-разрядная|  
|`_fstati64`|Не определено|64-разрядная|64-разрядная|  
|`_fstati64`|Определено|32-разрядная|64-разрядная|  
|`_fstat32i64`|Не затрагивается определением макроса|32-разрядная|64-разрядная|  
|`_fstat64i32`|Не затрагивается определением макроса|64-разрядная|32-разрядная|  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fstat`|\<sys/stat.h> и \<sys/types.h>|  
|`_fstat32`|\<sys/stat.h> и \<sys/types.h>|  
|`_fstat64`|\<sys/stat.h> и \<sys/types.h>|  
|`_fstati64`|\<sys/stat.h> и \<sys/types.h>|  
|`_fstat32i64`|\<sys/stat.h> и \<sys/types.h>|  
|`_fstat64i32`|\<sys/stat.h> и \<sys/types.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_filelength, _filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [_stat, _wstat Functions](../../c-runtime-library/reference/stat-functions.md)
