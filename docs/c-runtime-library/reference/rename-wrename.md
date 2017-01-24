---
title: "rename, _wrename | Microsoft Docs"
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
  - "rename"
  - "_wrename"
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
  - "_wrename"
  - "_trename"
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_trename - функция"
  - "_wrename - функция"
  - "каталоги [C++], переименование"
  - "файлы [C++], переименование"
  - "имена [C++], изменение каталога"
  - "имена [C++], изменение файла"
  - "rename - функция"
  - "переименование каталогов"
  - "переименование файлов"
  - "trename - функция"
  - "wrename - функция"
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rename, _wrename
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Переименование файла или каталога.  
  
## Синтаксис  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### Параметры  
 *oldname*  
 Указатель на старое имя.  
  
 *newname*  
 Указатель на новое имя.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает 0 в случае успеха.  При возникновении ошибки функция возвращает ненулевое значение и задает `errno` одно из следующих значений:  
  
 `EACCES`  
 Файл или каталог, указанный *newname*, уже существует и не может быть создан \(недопустимый путь\); или *oldname* является каталогом, а *newname* определяет другой путь.  
  
 `ENOENT`  
 Файл или путь, указанный *oldname*, не найден.  
  
 `EINVAL`  
 Имя содержит недопустимые символы.  
  
 Для других возможных возвращаемых значений см. [\_doserrno, \_errno, syserrlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция **rename** переименовывает файл или каталог, указанный *oldname*, к имени, заданному *newname*.  Старое имя должно быть путем к существующему файлу или каталогу.  Новое имя не должно быть именем существующего файла или каталога.  Можно использовать **rename** для перемещения файла из одного каталога или устройства в другое, указав другой путь в аргументе *newname*.  Однако нельзя использовать **rename** для перемещения каталога.  Каталоги можно переименовывать, но не перемещать.  
  
 `_wrename` — это двухбайтовая версия **\_rename**; аргументы для `_wrename` представляют собой двухбайтовые строки.  В противном случае поведение `_wrename` и **\_rename** идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_trename`|**переименовать**|**переименовать**|`_wrename`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**переименовать**|\<io.h\> или \<stdio.h\>|  
|`_wrename`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## Output  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## Эквивалент в .NET Framework  
 [System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)