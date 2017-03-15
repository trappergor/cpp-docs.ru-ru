---
title: "_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstat64"
  - "_stati64"
  - "_stat32"
  - "_stat32i64"
  - "_stat"
  - "_wstati64"
  - "_wstat32"
  - "_wstat64i32"
  - "_wstat"
  - "_stat64"
  - "_stat64i32"
  - "_wstat32i64"
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
  - "tstat32"
  - "tstat"
  - "_tstat64i32"
  - "tstati64"
  - "_wstat64"
  - "_wstat32"
  - "wstati64"
  - "tstat64"
  - "_stati64"
  - "_wstat"
  - "wstat64i32"
  - "stat32i64"
  - "tstat32i64"
  - "_tstat"
  - "_wstati64"
  - "_tstati64"
  - "_wstat32i64"
  - "wstat32"
  - "_wstat64i32"
  - "_stat"
  - "_tstat32"
  - "stat64i32"
  - "wstat64"
  - "stat"
  - "_stat32i64"
  - "_stat32"
  - "stati64"
  - "wstat"
  - "_stat64i32"
  - "stat32"
  - "_tstat32i64"
  - "tstat64i32"
  - "_tstat64"
  - "_stat64"
  - "stat/_stat"
  - "stat/_stat32"
  - "stat/_stat64"
  - "stat/_stati64"
  - "stat/_stat32i64"
  - "stat/_stat64i32"
  - "stat/_wstat"
  - "stat/_wstat32"
  - "stat/_wstat64"
  - "stat/_wstati64"
  - "stat/_wstat32i64"
  - "stat/_wstat64i32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "файлы [C++], сведения о состоянии"
  - "Функция _stat"
  - "Функция _wstat"
  - "Функция _stat64i32"
  - "Функция tstat"
  - "Функция _tstat64i32"
  - "Функция _stati64"
  - "Функция _stat64"
  - "Функция tstati64"
  - "Функция wstati64"
  - "Функция wstat64"
  - "Функция _wstat64i32"
  - "Функция _tstat32i64"
  - "Функция _stat32i64"
  - "Функция stat"
  - "статус файлов"
  - "Функция _tstat32"
  - "Функция tstat64"
  - "Функция _wstat64"
  - "Функция _tstat"
  - "Функция _stat32"
  - "Функция wstat"
  - "Функция _wstat32i64"
  - "Функция _tstati64"
  - "Функция _wstat32"
  - "Функция stat64"
  - "Функция stati64"
  - "Функция _wstati64"
  - "Функция _tstat64"
  - "файлы [C++], получение сведений о состоянии"
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает сведения о состоянии файла.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `path`  
 Указатель на строку, содержащую путь к существующему файлу или каталогу.  
  
 `buffer`  
 Указатель на структуру, в которой хранятся результаты.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает 0, если получена информация о состоянии файла. Возвращаемое значение –1 указывает на ошибку, при этом для параметра `errno` устанавливается значение `ENOENT`, которое указывает, что невозможно найти имя файла или путь. Возвращаемое значение `EINVAL` указывает на недопустимый параметр; в этом случае параметр `errno` также принимает значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Отметка даты в файле может быть представлена, если она позже полуночи 1 января 1970 года и до 23:59:59, 31 декабря 3000 года в формате UTC, если не используется `_stat32` или `_wstat32`, или были заданы `_USE_32BIT_TIME_T`, в этом случае дата может быть представлена только до 23:59:59 18 января 2038 года, UTC.  
  
## Заметки  
 Функция `_stat` получает сведения о файле или каталоге, указанном параметром `path`, и сохраняет их в структуре, указанной в параметре `buffer`. Функция `_stat` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей.  
  
 `_wstat` — это версия `_stat` с расширенными символами; аргумент `path` для `_wstat` — строка расширенных символов. В остальных отношениях поведение функций `_wstat` и `_stat` идентично, за исключением того, что функция `_wstat` не обрабатывает многобайтовые строки.  
  
 Варианты этих функций поддерживают 32\- или 64\-разрядные типы времени и 32\- или 64\-разрядные значения длины файлов. Первый числовой суффикс \(`32` или `64`\) указывает размер используемого типа времени; второй суффикс `i32` или `i64` показывает, представлен ли размер файла как 32\- или 64\-разрядное целое число.  
  
 `_stat` эквивалентно `_stat64i32`, и `struct``_stat` содержит 64\-разрядное время. Это значение true, если `_USE_32BIT_TIME_T` определен, в этом случае старое поведение действует; `_stat` использует 32\-разрядное время, и `struct``_stat` содержит 32\-разрядное время. Это же справедливо и для `_stati64`.  
  
> [!NOTE]
>  Функция `_wstat` не работает с символьными ссылками [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. В таких случаях функция `_wstat` всегда возвращает размер файла, равный 0. Функция `_stat` правильно работает с символьными ссылками.  
  
 Эта функция проверяет свои параметры. Если параметр `path` или `buffer` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
### Варианты типов времени и типов длины файлов в функции \_stat  
  
|Функции|Определена ли директива \_USE\_32BIT\_TIME\_T?|Тип времени|Тип длины файла|  
|-------------|----------------------------------------------------|-----------------|---------------------|  
|`_stat`, `_wstat`|Не определено|64\-разрядная|32\-разрядная|  
|`_stat`, `_wstat`|Определено|32\-разрядная|32\-разрядная|  
|`_stat32`, `_wstat32`|Не затрагивается определением макроса|32\-разрядная|32\-разрядная|  
|`_stat64`, `_wstat64`|Не затрагивается определением макроса|64\-разрядная|64\-разрядная|  
|`_stati64`, `_wstati64`|Не определено|64\-разрядная|64\-разрядная|  
|`_stati64`, `_wstati64`|Определено|32\-разрядная|64\-разрядная|  
|`_stat32i64`, `_wstat32i64`|Не затрагивается определением макроса|32\-разрядная|64\-разрядная|  
|`_stat64i32`, `_wstat64i32`|Не затрагивается определением макроса|64\-разрядная|32\-разрядная|  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 Структура `_stat`, определенная в SYS\\STAT.H, включает следующие поля.  
  
 `st_gid`  
 Числовой идентификатор группы, которой принадлежит файл \(только для UNIX\). В системах Windows это поле всегда равно нулю. Перенаправленный файл классифицируется как файл Windows.  
  
 `st_atime`  
 Время последнего доступа к файлу. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT.  
  
 `st_ctime`  
 Время создания файла. Действительно на дисках, отформатированных в файловой системе NTFS, но не в FAT.  
  
 `st_dev`  
 Номер диска, содержащего файл \(то же, что и `st_rdev`\).  
  
 `st_ino`  
 Номер узла информации \(`inode`\) для файла \(только для UNIX\). В файловых системах UNIX параметр `inode` описывает отметки даты и времени файла, разрешения и содержимое. Если файлы связаны жесткими ссылками друг с другом, они имеют один и тот же параметр `inode`. Параметр `inode` и, следовательно, параметр `st_ino` не имеют смысла в файловых системах FAT, HPFS и NTFS.  
  
 `st_mode`  
 Битовая маска для информации о файловом режиме. Бит `_S_IFDIR` устанавливается, если параметр `path` задает каталог; бит `_S_IFREG` устанавливается, если параметр `path` задает обычный файл или устройство. Пользовательские биты чтения\/записи устанавливаются в соответствии с режимом разрешений файла; пользовательские биты выполнения устанавливаются согласно расширению имени файла.  
  
 `st_mtime`  
 Время последнего изменения файла.  
  
 `st_nlink`  
 Всегда имеет значение 1 в файловых системах, отличных от NTFS.  
  
 `st_rdev`  
 Номер диска, содержащего файл \(то же, что и `st_dev`\).  
  
 `st_size`  
 Размер файла в байтах; 64\-разрядное целое число для вариантов с суффиксом `i64`**.**  
  
 `st_uid`  
 Числовой идентификатор пользователя, который владеет файлом \(только для UNIX\). В системах Windows это поле всегда будет равно нулю. Перенаправленный файл классифицируется как файл Windows.  
  
 Если параметр `path` ссылается на устройство, поле `st_size`, различные поля времени, поля `st_dev` и `st_rdev` в структуре `_stat` не имеют смысла. Поскольку STAT.H использует тип [\_dev\_t](../../c-runtime-library/standard-types.md), который определен в TYPES.H, в коде необходимо включить TYPES.H перед STAT.H.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys\/types.h\>, затем \<sys\/stat.h\>|\<errno.h\>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys\/types.h\>, затем \<sys\/stat.h\> или \<wchar.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
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
File size     : 732 Drive         : C: Time modified : Thu Feb 07 14:39:36 2002  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx)  
  
-   [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx)  
  
-   [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx)  
  
-   [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)