---
title: "_futime, _futime32, _futime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_futime64"
  - "_futime32"
  - "_futime"
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
  - "futime"
  - "_futime"
  - "futime64"
  - "_futime64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_futime - функция"
  - "futime32 - функция"
  - "futime64 - функция"
  - "время изменения файла [C++]"
  - "_futime64 - функция"
  - "futime - функция"
  - "_futime32 - функция"
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _futime, _futime32, _futime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает время изменения открытого файла.  
  
## Синтаксис  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### Параметры  
 `fd`  
 Дескриптор открытого файла.  
  
 `filetime`  
 Указатель на структуру, содержащую новую дату изменения.  
  
## Возвращаемое значение  
 Возвращает значение в случае успеха.  Если возникает ошибка, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает \-1 и задает `errno` значение `EBADF`, указывающее на недопустимый идентификатор файла, или значение `EINVAL`, указывающее на недопустимый параметр.  
  
## Заметки  
 Процедура `_futime` задает дату изменения и обращения к открытому файлу, связанному с `fd`*.* `_futime` идентична [\_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md), за исключением того, что её аргумент \- это дескриптор открытого файла, а не имя файла или путь к нему.  Структура `_utimbuf` содержит поля для новых дат изменения файла и доступа к нему.  Оба поля должны содержать допустимые значения.  `_utimbuf32` и `_utimbuf64` идентичны `_utimbuf`, за исключением того, что они используют 32 и 64 разрядные типы времени соответственно.  `_futime` и `_utimbuf` используют 64\-разрядный тип времени, и `_futime` идентична своим поведением функции `_futime64`.  Если необходимо использовать старое поведение, укажите `_USE_32BIT_TIME_T`.  Это приведёт к тому, что поведение `_futime` будет совпадать с поведением `_futime32`, а также к тому, что структура `_utimbuf` будет использовать 32\-разрядный тип времени, что сделает ее эквивалентной `__utimbuf32`.  
  
 `_futime64`, которая использует структуру `__utimbuf64`, может считывать и изменять даты файлов до 23:59:59, 31\-е декабря 3000, время в формате UTC; в то время как вызов `_futime32` завершается неудачей, если дата в файле позже 19:14:07 18\-го января 2038, время в формате UTC.  Полночь 1\-ого января 1970 года \- нижняя граница диапазона дат для этих функций.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_futime`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime32`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime64`|\<sys\/utime.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## Input: crt\_futime.c\_input  
  
```  
Arbitrary file contents.  
```  
  
### Пример результатов выполнения  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)  
  
-   [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)  
  
-   [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)