---
title: "remove, _wremove | Microsoft Docs"
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
  - "_wremove"
  - "remove"
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
  - "remove"
  - "_wremove"
  - "_tremove"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tremove - функция"
  - "_wremove - функция"
  - "файлы [C++], удаление"
  - "файлы [C++], удаление"
  - "remove - функция"
  - "tremove - функция"
  - "wremove - функция"
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove, _wremove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Удаляют файл.  
  
## Синтаксис  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### Параметры  
 *путь*  
 Путь к файлу, который необходимо удалить.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает 0, если файл успешно удален.  В противном случае они возвращают \-1 и задают `errno` либо значение `EACCES`, чтобы указать, что путь указывает на файл, доступный только для чтения, или что файл открыт, либо значение **ENOENT** для указания того, что имя файла или путь не найден, или что путь указывает на каталог.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция **remove** удаляет файл, указанный *path.* `_wremove` версия **\_remove** для расширенных символов; аргумент *path* для `_wremove` \- строка расширенных символов.  В противном случае поведение `_wremove` и **\_remove** идентично.  Все дескрипторы файла должны быть закрыты прежде, чем его можно удалять.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**remove**|\<stdio.h\> или \<io.h\>|  
|`_wremove`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_remove.c  
/* This program uses remove to delete crt_remove.txt */  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( remove( "crt_remove.txt" ) == -1 )  
      perror( "Could not delete 'CRT_REMOVE.TXT'" );  
   else  
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );  
}  
```  
  
## Input: crt\_remove.txt  
  
```  
This file will be deleted.  
```  
  
## Пример результатов выполнения  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## Эквивалент в .NET Framework  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_unlink, \_wunlink](../Topic/_unlink,%20_wunlink.md)