---
title: "_chsize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chsize"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_chsize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chsize - функция"
  - "chsize - функция"
  - "файлы [C++], изменение размера"
  - "размер"
  - "размер, изменение файла"
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chsize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер файла.  Доступна более безопасная версия; см. раздел [\_chsize\_s](../../c-runtime-library/reference/chsize-s.md).  
  
## Синтаксис  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### Параметры  
 `fd`  
 Идентификатор файла, ссылающийся на открытый файл.  
  
 `size`  
 Новая длина файла в байтах.  
  
## Возвращаемое значение  
 `_chsize` возвращает значение 0, если размер файла успешно изменен.  Возвращаемое значение, равное \-1, указывает на ошибку: `errno` имеет значение `EACCES`, если указанный файл блокирован для доступа, значение `EBADF`, если указанный файл доступен только для чтения или дескриптор недопустим, значение `ENOSPC` при отсутствии свободного места на устройстве, или значение `EINVAL`, если `size` меньше нуля.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_chsize` расширяет или усекает файл, связанный с `fd`, до длины, указанной в `size`.  Файл должен быть открыт в режиме, который позволяет запись.  В файл добавляются нуль\-символы \('\\0'\), если файл расширяется.  Если файл усекается, все данные от конца сокращенного файла до длины исходного файла теряются.  
  
 Эта функция проверяет свои параметры.  Если `size` меньше нуля, или `fd` \- неправильный дескриптор файла, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_chsize`|\<io.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
  **File length before: 0**  
**Size successfully changed**  
**File length after:  329678**   
## Эквивалент в .NET Framework  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_close](../Topic/_close.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)