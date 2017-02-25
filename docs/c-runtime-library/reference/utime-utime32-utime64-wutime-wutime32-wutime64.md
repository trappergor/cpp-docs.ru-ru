---
title: "_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_utime64"
  - "_utime"
  - "_wutime"
  - "_wutime64"
  - "_wutime32"
  - "_utime32"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tutime"
  - "_utime64"
  - "wutime"
  - "utime32"
  - "wutime64"
  - "_utime"
  - "wutime32"
  - "_wutime"
  - "utime"
  - "utime64"
  - "_wutime64"
  - "_utime32"
  - "_tutime64"
  - "_wutime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция tutime"
  - "Функция utime32"
  - "Функция utime64"
  - "Функция _utime"
  - "Функция _tutime32"
  - "время [C++], изменение файла"
  - "Функция wutime"
  - "Функция _wutime"
  - "Функция _wutime32"
  - "Функция _tutime64"
  - "Функция _tutime"
  - "файлы [C++], время изменения"
  - "Функция _wutime64"
  - "Функция _utime32"
  - "Функция utime"
  - "Функция _utime64"
  - "Функция wutime64"
  - "Функция wutime32"
  - "Функция tutime64"
  - "Функция tutime32"
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задают время изменения файла.  
  
## Синтаксис  
  
```  
int _utime(  
   const char *filename,  
   struct _utimbuf *times   
);  
int _utime32(  
   const char *filename,  
   struct __utimbuf32 *times   
);  
int _utime64(  
   const char *filename,  
   struct __utimbuf64 *times   
);  
int _wutime(  
   const wchar_t *filename,  
   struct _utimbuf *times   
);  
int _wutime32(  
   const wchar_t *filename,  
   struct __utimbuf32 *times   
);  
int _wutime64(  
   const wchar_t *filename,  
   struct __utimbuf64 *times   
);  
```  
  
#### Параметры  
 `filename`  
 Указатель на строку, содержащую путь или имя файла.  
  
 `times`  
 Указатель на сохраненные значения времени.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает 0, если время изменения файла было изменено. Возвращаемое значение \-1 означает ошибку. Если передан недопустимый параметр вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают –1 и устанавливают параметр `errno` в одно из следующих значений:  
  
 `EACCES`  
 Путь указывает каталог или файл, доступный только для чтения  
  
 `EINVAL`  
 Недопустимый аргумент `times`  
  
 `EMFILE`  
 Слишком много открытых файлов \(чтобы изменить время изменения файла, файл необходимо открыть\)  
  
 `ENOENT`  
 Путь или имя файла не найдены  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Дату файла можно изменить, если дата изменения лежит в диапазоне от полуночи 1\-го января 1970 года до конечной даты используемой функции. В функциях `_utime` и `_wutime` используется 64\-разрядное значение времени, поэтому конечная дата 23:59:59 31\-го декабря 3000 года, время в формате UTC. Если `_USE_32BIT_TIME_T` определен для принудительного использования старого поведения, конечная дата — 23:59:59 18 января 2038 года, UTC. Функции `_utime32` и `_wutime32` используют 32\-разрядный тип времени независимо от того, определена ли директива `_USE_32BIT_TIME_T`, и всегда имеют более раннюю конечную дату. Функции `_utime64` и `_wutime64` всегда используют 64\-разрядный тип времени, поэтому эти функции всегда поддерживают более позднюю конечную дату.  
  
## Заметки  
 `_utime` Функция задает время изменения для файла, указанного в `filename`*.* Для изменения времени процесс должен иметь разрешение на запись в файл. В операционной системе Windows можно изменить время доступа и время изменения в структуре `_utimbuf`. Если `times` является указателем `NULL`, для времени изменения устанавливается текущее время. В противном случае переменная `times` должна указывать на структуру типа `_utimbuf`, определенную в SYS\\UTIME.H.  
  
 Структура `_utimbuf` хранит время доступа к файлу и время изменения файла, которые используются функцией `_utime` для изменения времени изменения файла. Структура содержит следующие поля, оба из которых имеют тип `time_t`:  
  
 `actime`  
 Время доступа к файлу  
  
 `modtime`  
 Время изменения файла  
  
 Конкретные версии структуры `_utimbuf` \(`_utimebuf32` и `__utimbuf64`\) задаются с 32\- и 64\-разрядными версиями типа времени. Они используются в 32\- и 64\-разрядных версиях этой функции. По умолчанию в структуре `_utimbuf` используется 64\-разрядное время, если только не определена директива `_USE_32BIT_TIME_T`.  
  
 Функция `_utime` идентична функции `_futime`, но аргумент `filename` функции `_utime` представляет собой имя файла или путь к файлу, а не дескриптор открытого файла.  
  
 `_wutime` — это версия `_utime` с расширенными символами; аргумент `filename` для `_wutime` — строка расширенных символов. В остальном эти функции ведут себя одинаково.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## Требования  
  
|Подпрограмма|Обязательные заголовки|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`_utime`, `_utime32`, `_utime64`|\<sys\/utime.h\>|\<errno.h\>|  
|`_utime64`|\<sys\/utime.h\>|\<errno.h\>|  
|`_wutime`|\<utime.h\> или \<wchar.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Эта программа использует функцию `_utime`, чтобы задать для времени изменения файла текущее время.  
  
```  
// crt_utime.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/utime.h>  
#include <time.h>  
  
int main( void )  
{  
   struct tm tma = {0}, tmm = {0};  
   struct _utimbuf ut;  
  
   // Fill out the accessed time structure  
   tma.tm_hour = 12;  
   tma.tm_isdst = 0;  
   tma.tm_mday = 15;  
   tma.tm_min = 0;  
   tma.tm_mon = 0;  
   tma.tm_sec = 0;  
   tma.tm_year = 103;  
  
   // Fill out the modified time structure  
   tmm.tm_hour = 12;  
   tmm.tm_isdst = 0;  
   tmm.tm_mday = 15;  
   tmm.tm_min = 0;  
   tmm.tm_mon = 0;  
   tmm.tm_sec = 0;  
   tmm.tm_year = 102;  
  
   // Convert tm to time_t  
   ut.actime = mktime(&tma);  
   ut.modtime = mktime(&tmm);  
  
   // Show file time before and after  
   system( "dir crt_utime.c" );  
   if( _utime( "crt_utime.c", &ut ) == -1 )  
      perror( "_utime failed\n" );  
   else  
      printf( "File time modified\n" );  
   system( "dir crt_utime.c" );  
}  
```  
  
## Пример результатов выполнения  
  
```  
Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/09/2003  05:38 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
File time modified  
 Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/15/2002  12:00 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [\_futime, \_futime32, \_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [Функции \_stat, \_wstat](../../c-runtime-library/reference/stat-functions.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)