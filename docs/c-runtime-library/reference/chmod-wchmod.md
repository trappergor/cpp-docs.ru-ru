---
title: "_chmod, _wchmod | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chmod"
  - "_wchmod"
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
  - "_chmod"
  - "_wchmod"
  - "wchmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chmod - функция"
  - "_wchmod - функция"
  - "chmod - функция"
  - "разрешения файла [C++]"
  - "файлы [C++], изменение разрешений"
  - "wchmod - функция"
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _chmod, _wchmod
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет параметры разрешений файла.  
  
## Синтаксис  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### Параметры  
 `filename`  
 Имя существующего файла.  
  
 `pmode`  
 Параметры разрешений для файла.  
  
## Возвращаемое значение  
 Эти функции возвращают значение 0, если параметры разрешений успешно изменены.  Возвращаемое значение, равное \-1, означает неудачу.  Если указанный файл не найден, то `errno` имеет значение `ENOENT`; если параметр является недопустимым, то `errno` имеет значение `EINVAL`.  
  
## Заметки  
 Функция `_chmod` изменяет параметры разрешений файла, указанного в `filename`*.* Параметры разрешений управляют доступом к файлу для чтения и записи.  Целочисленное выражение `pmode` содержит одну или обе следующих константы манифеста, определенных в SYS\\Stat.h.  
  
 `_S_IWRITE`  
 Запись разрешена.  
  
 `_S_IREAD`  
 Чтение разрешено.  
  
 `_S_IREAD | _S_IWRITE`  
 Чтение и запись разрешены.  
  
 Если предоставлены обе константы, они объединяются битовым оператором `OR` \(          `|` \).  Если разрешение записи не задано, то файл доступен только для чтения.  Обратите внимание, что все файлы всегда доступны для чтения; невозможно предоставить доступ только на запись.  Таким образом режимы `_S_IWRITE` и `_S_IREAD | _S_IWRITE` эквивалентны.  
  
 `_wchmod` — двухбайтовая версия `_chmod`; аргумент `filename` для `_wchmod` \- строка двухбайтовых знаков.  В остальных случаях поведение `_wchmod` и `_chmod` идентично.  
  
 Эта функция проверяет свои параметры.  Если `pmode` \- не сочетание одной из констант манифеста, или он содержит другой набор констант, функция просто игнорирует их.  Если параметр `filename` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, `errno` принимает значение `EINVAL`, и функция возвращает \-1.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_chmod`|\<io.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wchmod`|\<io.h\> или \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
  **`A line of text.` `A line of text.`Mode set to read\-only**  
**Отказано в доступе.**  
**Mode set to read\/write**   
## Эквивалент в .NET Framework  
  
-   [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
-   [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции \_stat, \_wstat](../../c-runtime-library/reference/stat-functions.md)