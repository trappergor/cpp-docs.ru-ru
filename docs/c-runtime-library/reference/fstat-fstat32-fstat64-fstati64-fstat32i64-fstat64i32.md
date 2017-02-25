---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fstat32"
  - "_fstat64"
  - "_fstati64"
  - "_fstat"
  - "_fstat64i32"
  - "_fstat32i64"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstat32i64"
  - "fstat"
  - "fstat64i32"
  - "_fstat64"
  - "_fstati64"
  - "fstat64"
  - "_fstat32"
  - "fstat32i64"
  - "fstati64"
  - "_fstat"
  - "fstat32"
  - "_fstat64i32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstat64 - функция"
  - "fstati64 - функция"
  - "_fstat64i32 - функция"
  - "_fstat32i64 - функция"
  - "_fstat32 - функция"
  - "сведения о файлах"
  - "fstat64i32 - функция"
  - "fstat32 - функция"
  - "fstat - функция"
  - "fstat64 - функция"
  - "_fstat - функция"
  - "_fstati64 - функция"
  - "fstat32i64 - функция"
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает сведения о открытого файла.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `fd`  
 Дескриптор открытого файла.  
  
 `buffer`  
 Указатель на структуру, для хранения результатов.  
  
## Возвращаемое значение  
 Возвращает 0, если получены сведения о состоянии файла. Возвращаемое значение \-1 означает ошибку. Если дескриптор файла является недопустимым или `buffer` — `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, `errno` имеет значение `EBADF`, в случае с недопустимым дескриптором файла, а также к `EINVAL`, если `buffer` является `NULL`.  
  
## Заметки  
 `_fstat` Функция получает информацию о открыть файл, связанный с `fd` и сохраняет его в структуре, на который указывает `buffer`.`_stat` Структура, определенная в SYS\\Stat.h, содержит следующие поля.  
  
 `st_atime`  
 Время последнего доступа к файлу.  
  
 `st_ctime`  
 Время создания файла.  
  
 `st_dev`  
 Если устройство, `fd`; в противном случае — 0.  
  
 `st_mode`  
 Битовая маска для информации о файловом режиме.`_S_IFCHR` Бит устанавливается в том случае, если `fd` ссылается на устройство.`_S_IFREG` Бит устанавливается в том случае, если `fd` ссылается на обычный файл. Биты чтения\/записи устанавливаются в соответствии с режимом разрешений файла.`_S_IFCHR` и другие константы определены в SYS\\Stat.h.  
  
 `st_mtime`  
 Время последнего изменения файла.  
  
 `st_nlink`  
 Всегда имеет значение 1 в файловых системах, отличных от NTFS.  
  
 `st_rdev`  
 Если устройство, `fd`; в противном случае — 0.  
  
 `st_size`  
 Размер файла в байтах.  
  
 Если `fd` ссылается на устройство, `st_atime`, `st_ctime`, `st_mtime`, и `st_size` поля не имеют смысла.  
  
 Поскольку Stat.h использует [\_dev\_t](../../c-runtime-library/standard-types.md) тип, который определен в Types.h, в коде необходимо включить Types.h перед Stat.h.  
  
 `_fstat64`, которая использует `__stat64` структуры, позволяет даты создания файла может быть представлена до 23:59:59, 31 декабря 3000 года в формате UTC, тогда как другие функции представляет даты только до 23:59:59 18 января 2038 года, UTC. Полуночи 1 января 1970 года — нижняя граница диапазона дат для этих функций.  
  
 Варианты этих функций поддерживают типы 32\-разрядной или 64\-разрядных времени и длину 32\-разрядной или 64\-разрядных файлов. Первый числовой суффикс \(`32` или `64`\) указывает размер используемого типа времени; второй суффикс `i32` или `i64` показывает, представлен ли размер файла как 32\- или 64\-разрядное целое число.  
  
 `_fstat` эквивалентно `_fstat64i32`, и `struct``_stat` содержит 64\-разрядное время. Это значение true, если `_USE_32BIT_TIME_T` определен, в этом случае старое поведение действует; `_fstat` использует 32\-разрядное время, и `struct``_stat` содержит 32\-разрядное время. То же самое верно для `_fstati64`.  
  
### Варианты типов времени и типов длины файлов в функции \_stat  
  
|Функции|Определена ли директива \_USE\_32BIT\_TIME\_T?|Тип времени|Тип длины файла|  
|-------------|----------------------------------------------------|-----------------|---------------------|  
|`_fstat`|Не определено|64\-разрядная|32\-разрядная версия|  
|`_fstat`|Определено|32\-разрядная|32\-разрядная версия|  
|`_fstat32`|Не затрагивается определением макроса|32\-разрядная|32\-разрядная версия|  
|`_fstat64`|Не затрагивается определением макроса|64\-разрядная|64\-разрядная|  
|`_fstati64`|Не определено|64\-разрядная|64\-разрядная|  
|`_fstati64`|Определено|32\-разрядная|64\-разрядная|  
|`_fstat32i64`|Не затрагивается определением макроса|32\-разрядная|64\-разрядная|  
|`_fstat64i32`|Не затрагивается определением макроса|64\-разрядная|32\-разрядная|  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fstat`|\< sys\/stat.h \> и \< sys\/types.h \>|  
|`_fstat32`|\< sys\/stat.h \> и \< sys\/types.h \>|  
|`_fstat64`|\< sys\/stat.h \> и \< sys\/types.h \>|  
|`_fstati64`|\< sys\/stat.h \> и \< sys\/types.h \>|  
|`_fstat32i64`|\< sys\/stat.h \> и \< sys\/types.h \>|  
|`_fstat64i32`|\< sys\/stat.h \> и \< sys\/types.h \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
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
Размер файла: изменения 16: 07 мая среда 15:25:11 2003  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [Функции \_stat, \_wstat](../../c-runtime-library/reference/stat-functions.md)