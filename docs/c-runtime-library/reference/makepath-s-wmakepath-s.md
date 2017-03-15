---
title: "_makepath_s, _wmakepath_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmakepath_s"
  - "_makepath_s"
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
  - "_wmakepath_s"
  - "makepath_s"
  - "_makepath_s"
  - "wmakepath_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_makepath_s - функция"
  - "wmakepath_s - функция"
  - "пути"
  - "_wmakepath_s - функция"
  - "makepath_s - функция"
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _makepath_s, _wmakepath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает путь из компонентов.  Здесь представлены версии [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `path`  
 Буфер полного пути.  
  
 \[входящий\] `sizeInWords`  
 Размер буфера в словах.  
  
 \[входящий\] `sizeInBytes`  
 Размер буфера в байтах.  
  
 \[входящий\] `drive`  
 Содержит букву \(A, B и т д\), соответствующую требуемому диску и дополненную необязательным двоеточием.  `_makepath_s` вставляет двоеточие в составной путь автоматически, если оно отсутствует.  Если `drive` — `NULL` или указывает на пустую строку, то буква диска не отображается в составной строке `path`.  
  
 \[входящий\] `dir`  
 Содержит путь каталогов, не включая обозначение диска или фактическое имя файла.  Конечная косая черта является необязательной; в одном аргументе `dir` может использоваться косая черта \(\/\), обратная косая черта \(\\\) или обе.  Если конечная косая черта \(\/ или \\\) не указана, она вставляется автоматически.  Если `dir` — `NULL` или указывает на пустую строку, то путь каталога не вставляется в составную строку `path`.  
  
 \[входящий\] `fname`  
 Содержит базовое имя файла без расширений.  Если `fname` — `NULL` или указывает на пустую строку, то имя файла не вставляется в составную строку `path`.  
  
 \[входящий\] `ext`  
 Содержит фактическое расширение имени файла с предшествующей точкой или без \(.\).  `_makepath_s` вставляет точку автоматически, если она отсутствует в `ext`.  Если `ext` — `NULL` или указывает на пустую строку, то расширение не вставляется в составную строку `path`.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
### Условия возникновения ошибки  
  
|`path`|`sizeInWords` \/ `sizeInBytes`|Return|Содержимое `path`.|  
|------------|------------------------------------|------------|------------------------|  
|`NULL`|any|`EINVAL`|без изменений|  
|any|\<\= 0|`EINVAL`|без изменений|  
  
 Если возникает любое из ошибочных условий, эти функции вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, `errno` присваивается`EINVAL` и функции возвращают`EINVAL`**.** `NULL` разрешен для параметров `drive`, `fname` и `ext`.  Дополнительные сведения о поведении в случае, когда эти параметры являются нулевыми указателями или пустыми строками см. в разделе комментариев.  
  
## Заметки  
 Функция `_makepath_s` создает строку составного пути из отдельных компонентов, сохраняя результат в `path`.  `path` может включать букву диска, путь к каталогу, имя файла и расширение имени файла.  `_wmakepath_s` — это двухбайтовая версия `_makepath_s`; аргументы для `_wmakepath_s` представляют собой двухбайтовые строки.  В остальных случаях поведение `_wmakepath_s` и `_makepath_s` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 Аргумент `path` должен указывать на пустой буфер достаточного для хранения полного пути размера.  Размер составного `path` не может превышать константу `_MAX_PATH`, определенную в Stdlib.h.  
  
 Если путь имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Кроме того, `errno` устанавливается в `EINVAL`.  Значения `NULL` разрешены для всех остальных параметров.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_makepath_s`|\<stdlib.h\>|  
|`_wmakepath_s`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## Output  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## Эквивалент в .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)