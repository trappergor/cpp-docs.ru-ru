---
title: "_fullpath, _wfullpath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fullpath"
  - "_wfullpath"
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
  - "wfullpath"
  - "fullpath"
  - "_wfullpath"
  - "_fullpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath - функция"
  - "_wfullpath - функция"
  - "абсолютные пути"
  - "fullpath - функция"
  - "относительные пути к файлам"
  - "wfullpath - функция"
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _fullpath, _wfullpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает абсолютный или полный путь для указанного относительного пути.  
  
## Синтаксис  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### Параметры  
 `absPath`  
 Указатель на буфер, содержащий абсолютный или полный путь, или NULL.  
  
 `relPath`  
 Относительный путь.  
  
 `maxLength`  
 Максимальная длина буфера абсолютного пути \(`absPath`\).  Эта длина в байтах для `_fullpath`, но в расширенных символах \(`wchar_t`\) для `_wfullpath`.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на буфер, содержащий абсолютный путь \(`absPath`\).  Если произошла ошибка \(например, если значение, переданное в `relPath` содержит букву диска, который является недопустимым или не может быть найден, или, если длина создаваемого абсолютного пути \(`absPath`\) больше `maxLength`\), функция возвращает `NULL`.  
  
## Заметки  
 Функция `_fullpath` разворачивает относительный путь в `relPath` в его полный или абсолютный путь и сохраняет его в `absPath`*.* Если `absPath` равно NULL, `malloc` используется, чтобы выделить буфер надлежащей длины для хранения пути.  Освобождение этого буфера — обязанность вызывающего объекта.  Относительный путь указывает путь в другое расположение из текущего расположения \(например, текущей рабочей папки: "."\).  Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы.  В отличие от `_makepath`, `_fullpath` можно использовать для получения абсолютного пути из относительных путей \(`relPath`\), содержащих в себе «.\/» или «..\/».  
  
 Например, чтобы использовать процедуры среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления процедур.  Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом \(из рабочей папки приложения\):  
  
```  
#include <stdlib.h>  
```  
  
 когда абсолютный путь \(реальное расположение в файловой системе\) файла может быть:  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath` автоматически обрабатывает аргументы в виде многобайтовых строк как подходящие, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей.  `_wfullpath` — это двухбайтовая версия `_fullpath`; аргументы строки для `_wfullpath` представляют собой двухбайтовые строки.  В остальных случаях поведение `_wfullpath` и `_fullpath` идентично, за исключением того, что `_wfullpath` не обрабатывает многобайтовые строки.  
  
 Если `_DEBUG` и `_CRTDBG_MAP_ALLOC` определены, вызовы `_fullpath` и `_wfullpath` заменяются вызовами `_fullpath_dbg` и `_wfullpath_dbg`, чтобы разрешить отладку выделения памяти.  Дополнительные сведения см. в разделе [\_fullpath\_dbg, \_wfullpath\_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Эта функция вызывает обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md), если `maxlen` меньше или равно 0.  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `NULL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Если буфер `absPath` равен `NULL`, `_fullpath` вызывает функцию [malloc](../../c-runtime-library/reference/malloc.md), чтобы выделить буфер, и игнорирует аргумент `maxLength`.  Корректное освобождение этого буфера \- обязанность вызывающего объекта \(с помощью [free](../../c-runtime-library/reference/free.md)\).  Если аргумент `relPath` определяет диск, текущий каталог этого диска объединяется с путем.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fullpath`|\<stdlib.h\>|  
|`_wfullpath`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
  **Полный путь выглядит следующим образом: C:\\Documents and Settings\\user\\My Documents\\test**  
**Полный путь выглядит следующим образом: C:\\test**  
**Полный путь выглядит следующим образом: C:\\Documents and Settings\\user\\test**   
## Эквивалент в .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)