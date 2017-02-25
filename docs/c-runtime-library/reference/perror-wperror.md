---
title: "perror, _wperror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wperror"
  - "perror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wperror"
  - "_tperror"
  - "perror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tperror - функция"
  - "_wperror - функция"
  - "сообщения об ошибках, печать"
  - "perror - функция"
  - "печать сообщений об ошибках"
  - "tperror - функция"
  - "wperror - функция"
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# perror, _wperror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вывод сообщения об ошибке.  
  
## Синтаксис  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### Параметры  
 `string`  
 Строковое сообщение для печати.  
  
## Заметки  
 Функция `perror` выводит сообщение об ошибке в `stderr`.  `_wperror` — версия **\_perror** для расширенных символов; аргумент `string` для `_wperror` — строка расширенных символов.  В противном случае поведение `_wperror` и **\_perror** идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` выводится первой, затем выводится двоеточие, затем системное сообщение об ошибке от последнего выполнившегося с ошибкой вызова библиотеки и, в конце, выводится символ новой строки.  Если `string` является указателем null или указателем на строку нулевой длины, `perror` печатает только сообщение о системной ошибке.  
  
 Номер ошибки хранится в переменной [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) \(определена в ERRNO.H\).  Доступ к сообщениям о системной ошибке осуществляется через переменную [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки.  `perror` выводит соответствующее сообщение об ошибке с используя значение `errno` как индекс в `_sys_errlist`.  Значение переменной [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) определено как максимальное количество элементов в массиве `_sys_errlist`.  
  
 Для точных результатов следует вызывать `perror` сразу после того, как библиотечная подпрограмма возвращается с ошибкой.  В противном случае последующие вызовы могут перезаписать значение `errno`.  
  
 В операционной системе Windows некоторые значения `errno`, перечисленные в ERRNO.H, не используются.  Эти значения зарезервированы для использования операционной системой UNIX.  Смотрите раздел [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для списка `errno` используемых операционной системой Windows.  `perror` выводит пустую строку для любого значения `errno` не используемого этими платформами.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`perror`|\<stdio.h\> или \<stdlib.h\>|  
|`_wperror`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## Output  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)