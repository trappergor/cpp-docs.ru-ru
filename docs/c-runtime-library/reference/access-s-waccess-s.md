---
title: "_access_s, _waccess_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access_s"
  - "_waccess_s"
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
  - "waccess_s"
  - "access_s"
  - "_waccess_s"
  - "_access_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access_s - функция"
  - "_taccess_s - функция"
  - "_waccess_s - функция"
  - "access_s - функция"
  - "taccess_s - функция"
  - "waccess_s - функция"
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _access_s, _waccess_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет разрешения на чтение и запись файла.  Это версия [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Параметры  
 `path`  
 Путь к файлу или каталогу.  
  
 `mode`  
 Параметры разрешений  
  
## Возвращаемое значение  
 Каждая функция возвращает значение 0, если файл имеет заданный режим.  Функция возвращает код ошибки, если именованный файл не существует или недоступен в заданном режиме.  В этом случае функция возвращает код ошибки из следующего набора, а также устанавливает для `errno` то же значение.  
  
 `EACCES`  
 Доступ запрещен.  Настройка разрешений файла не позволяет указанный доступ.  
  
 `ENOENT`  
 Имя файла или путь не найден.  
  
 `EINVAL`  
 Неверный параметр  
  
 Дополнительные сведения см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 При использовании с файлами, функция `_access_s` определяет существует ли указанный файл и можно ли получить к нему доступ, используя указанный режим `mode`.  При использовании с каталогами, `_access_s` определяет существует ли указанный каталог.  В [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] и последующих версиях операционных систем все каталоги имеют доступ для чтения и записи.  
  
|значение режима|Проверяет файл|  
|---------------------|--------------------|  
|00|Только на существование.|  
|02|Разрешение на запись.|  
|04|Разрешение на чтение.|  
|06|Разрешение на чтение и запись.|  
  
 Разрешения на чтение или запись файла не достаточно для того, чтобы убедиться в возможности открыть файл.  Например, если файл блокирован другим процессом, он может быть недоступен, даже если `_access_s` возвращает 0.  
  
 `_waccess_s` — двухбайтовая версия `_access_s`, где аргумент `path` для `_waccess_s` \- строка двухбайтовых знаков.  В противном случае поведение `_waccess_s` и `_access_s` идентично.  
  
 Эти функции проверяют свои параметры.  Если `path` равно `NULL`, или `mode` не определяет допустимый режим, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_access_s`|\<io.h\>|\<errno.h\>|  
|`_waccess_s`|\<wchar.h\> или \<io.h\>|\<errno.h\>|  
  
## Пример  
 В этом примере используется `_access_s` для проверки файл с именем crt\_access\_s.c, чтобы понять, существует ли он и разрешена ли запись в него.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
  **File crt\_access\_s.c exists.**  
**File crt\_access\_s.c does not have write permission.**   
## Эквивалент в .NET Framework  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции \_stat, \_wstat](../../c-runtime-library/reference/stat-functions.md)