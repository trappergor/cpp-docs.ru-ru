---
title: "_access, _waccess | Microsoft Docs"
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
  - "_access"
  - "_waccess"
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
  - "_waccess"
  - "_access"
  - "taccess"
  - "waccess"
  - "_taccess"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_access - функция"
  - "_taccess - функция"
  - "_waccess - функция"
  - "access - функция"
  - "taccess - функция"
  - "waccess - функция"
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _access, _waccess
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, доступен ли файл только для чтения, или нет.  Доступны более безопасные версии; см. раздел [\_access\_s, \_waccess\_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## Синтаксис  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Параметры  
 `path`  
 Путь к файлу или каталогу.  
  
 `mode`  
 Атрибут чтения\/записи.  
  
## Возвращаемое значение  
 Каждая функция возвращает значение 0, если файл имеет заданный режим.  Функция возвращает значение \-1, если указанный файл не существует или не находится в заданном режиме; в этом случае `errno` имеет одно из значений, которые показаны в следующей таблице.  
  
 `EACCES`  
 Доступ запрещен: настройка разрешений файла не позволяет указанный доступ.  
  
 `ENOENT`  
 Имя файла или путь не найден.  
  
 `EINVAL`  
 Неверный параметр  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 При использовании с файлами, функция `_access` определяет, существует ли указанный файл или каталог и имеет ли он атрибуты, определенные значением `mode`.  При использовании с каталогами, `_access` только определяет, существует ли указанный каталог; в [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] и последующих версиях операционных систем, все каталоги имеют доступ по чтению и записи.  
  
|Значение `mode`|Проверяет файл|  
|---------------------|--------------------|  
|00|Только на существование|  
|02|На доступ только для записи|  
|04|Только для чтения|  
|06|На доступ по чтению и записи|  
  
 Эта функция только проверяет, имеет ли файл и каталог доступ только для чтения или нет, она не проверяет параметры безопасности файловой системы.  Для этого требуется токен доступа.  Дополнительные сведения о безопасности файловой системы см. в разделе [Токены доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909).  Для обеспечения этой функциональности существует класс ATL; см. раздел [CAccessToken Class](../Topic/CAccessToken%20Class.md).  
  
 `_waccess` — двухбайтовая версия `_access`; аргумент `path` для `_waccess` \- строка двухбайтовых знаков.  В остальных случаях поведение `_waccess` и `_access` идентично.  
  
 Эта функция проверяет свои параметры.  Если `path` равно `NULL`, или `mode` не определяет допустимый режим, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если разрешено продолжить выполнение, функция задает `errno` значение `EINVAL` и возвращает \-1.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`_access`|\<io.h\>|\<errno.h\>|  
|`_waccess`|\<wchar.h\> или \<io.h\>|\<errno.h\>|  
  
## Пример  
 В следующем примере используется `_access` для проверки файл с именем crt\_ACCESS.C, чтобы понять, существует ли он и разрешена ли запись в него.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
  **File crt\_ACCESS.C exists.**  
**File crt\_ACCESS.C does not have write permission.**   
## Эквивалент в .NET Framework  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции \_stat, \_wstat](../../c-runtime-library/reference/stat-functions.md)