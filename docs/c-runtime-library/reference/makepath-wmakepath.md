---
title: "_makepath, _wmakepath | Microsoft Docs"
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
  - "_makepath"
  - "_wmakepath"
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
  - "_wmakepath"
  - "_tmakepath"
  - "makepath"
  - "tmakepath"
  - "wmakepath"
  - "_makepath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath - функция"
  - "_tmakepath function"
  - "_wmakepath - функция"
  - "makepath - функция"
  - "пути"
  - "tmakepath - функция"
  - "wmakepath - функция"
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath, _wmakepath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создание пути из компонентов.  Существуют более безопасные версии этих функций; см. раздел [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## Синтаксис  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### Параметры  
 `path`  
 Буфер полного пути.  
  
 `drive`  
 Содержит букву \(A, B и т д\), соответствующую требуемому диску и дополненную необязательным двоеточием.  `_makepath` вставляет двоеточие в составной путь автоматически, если оно отсутствует.  Если `drive` — `NULL` или указывает на пустую строку, то буква диска не отображается в составной строке `path`.  
  
 `dir`  
 Содержит путь каталогов, не включая обозначение диска или фактическое имя файла.  Конечная косая черта является необязательной; в одном аргументе `dir` может использоваться косая черта \(\/\), обратная косая черта \(\\\) или обе.  Если конечная косая черта \(\/ или \\\) не указана, она вставляется автоматически.  Если `dir` — `NULL` или указывает на пустую строку, то путь каталога не вставляется в составную строку `path`.  
  
 `fname`  
 Содержит базовое имя файла без расширений.  Если `fname` — `NULL` или указывает на пустую строку, то имя файла не вставляется в составную строку `path`.  
  
 `ext`  
 Содержит фактическое расширение имени файла с предшествующей точкой или без \(.\).  `_makepath` вставляет точку автоматически, если она отсутствует в `ext`.  Если `ext` — `NULL` или указывает на пустую строку, то расширение не вставляется в составную строку `path`.  
  
## Заметки  
 Функция `_makepath` создает строку составного пути из отдельных компонентов, сохраняя результат в `path`.  `path` может включать букву диска, путь к каталогу, имя файла и расширение имени файла.  `_wmakepath` — это двухбайтовая версия `_makepath`; аргументы для `_wmakepath` представляют собой двухбайтовые строки.  В остальных случаях поведение `_wmakepath` и `_makepath` идентично.  
  
 **Примечание о безопасности** Следует использовать строку, оканчивающуюся символом null.  Чтобы избежать переполнения буфера, строка, завершаемая нулевым символом, не должна превышать размер буфера `path`.  `_makepath` не гарантирует, что длина составной строки пути не превышает `_MAX_PATH`.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 Аргумент `path` должен указывать на пустой буфер достаточного для хранения полного пути размера.  Размер составного `path` не может превышать константу `_MAX_PATH`, определенную в Stdlib.h.  
  
 Если путь имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Кроме того, `errno` устанавливается в `EINVAL`.  Значения `NULL` разрешены для всех остальных параметров.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_makepath`|\<stdlib.h\>|  
|`_wmakepath`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
  **Path created with \_makepath: c:\\sample\\crt\\makepath.c**  
**Path extracted with \_splitpath:**  
 **Drive: c:**  
 **Dir: \\sample\\crt\\**  
 **Filename: makepath**  
 **Ext: .c**   
## Эквивалент в .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)   
 [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)