---
title: "_eof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_eof"
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
  - "_eof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_eof - функция"
  - "конец файла"
  - "конец файла, тестирование на"
  - "eof - функция"
  - "файлы [C++], конец"
  - "проверка, для конца файла"
ms.assetid: 265703f4-d07e-4005-abf3-b1d0cdd9e0b0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _eof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет наличие конца файла \(EOF\).  
  
## Синтаксис  
  
```  
int _eof(   
   int fd   
);  
```  
  
#### Параметры  
 `fd`  
 Дескриптор файла, ссылающийся на открытый файл.  
  
## Возвращаемое значение  
 `_eof` возвращает 1, если текущая позиция — конец файла, или 0, если это не так.  Возвращаемое значение \-1 указывает на ошибку; в этом случае вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение можно продолжить, `errno` устанавливается в `EBADF`, которое указывает на недопустимый идентификатор файла.  
  
## Заметки  
 Функция `_eof` определяет факт достижения конца файла, связанного с `fd`.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_eof`|\<io.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_eof.c  
// This program reads data from a file  
// ten bytes at a time until the end of the  
// file is reached or an error is encountered.  
//  
#include <io.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh, count, total = 0;  
   char buf[10];  
   if( _sopen_s( &fh, "crt_eof.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
        perror( "Open failed");  
        exit( 1 );  
   }  
   // Cycle until end of file reached:   
   while( !_eof( fh ) )  
   {  
      // Attempt to read in 10 bytes:   
      if( (count = _read( fh, buf, 10 )) == -1 )  
      {  
         perror( "Read error" );  
         break;  
      }  
      // Total actual bytes read   
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   _close( fh );  
}  
```  
  
## Вход: crt\_eof.txt  
  
```  
This file contains some text.  
```  
  
### Output  
  
```  
Number of bytes read = 29  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Низкоуровневый ввод\-вывод](../../c-runtime-library/low-level-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)