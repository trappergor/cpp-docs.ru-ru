---
title: "_makepath, _wmakepath | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _makepath
- _wmakepath
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbbaa2f4191d36fb92af5e157990fde6f053df55
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath
Создают путь из компонентов. Существуют более безопасные версии этих функций; см. раздел [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Буфер полного пути.  
  
 `drive`  
 Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. Если двоеточие отсутствует, функция `_makepath` вставляет ее в составной путь автоматически. Если параметр `drive` имеет значение `NULL` или указывает на пустую строку, в составной строке `path` буква диска не отображается.  
  
 `dir`  
 Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Конечная косая черта является необязательной; в одном аргументе `dir` могут использоваться косая черта (/), обратная косая черта (\\) или обе. Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если параметр `dir` имеет значение `NULL` или указывает на пустую строку, путь каталога не вставляется в составную строку `path`.  
  
 `fname`  
 Содержит базовое имя файла без расширений. Если параметр `fname` имеет значение `NULL` или указывает на пустую строку, имя файла не вставляется в составную строку `path`.  
  
 `ext`  
 Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. Функция `_makepath` вставляет точку автоматически, если она отсутствует в параметре `ext`. Если параметр `ext` имеет значение `NULL` или указывает на пустую строку, расширение не вставляется в составную строку `path`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_makepath` создает строку составного пути из отдельных компонентов, сохраняя результат в параметре `path`. Путь `path` может включать букву диска, путь к каталогу, имя файла и расширение имени файла. `_wmakepath` — это двухбайтовая версия `_makepath`; аргументы для `_wmakepath` представляют собой двухбайтовые строки. Поведение `_wmakepath` и `_makepath` идентично в противном случае.  
  
 **Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Длина строки, завершающейся нуль-символом, не должна превышать размер буфера `path`. Функция `_makepath` не проверяет, чтобы длина строки составного пути не превышала `_MAX_PATH`. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 Аргумент `path` должен указывать на пустой буфер достаточного для хранения полного пути размера. Размер составного пути `path` не должен быть больше константы `_MAX_PATH`, определенной в файле Stdlib.h.  
  
 Если параметр path имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того, для параметра `errno` устанавливается значение `EINVAL`. Для всех остальных параметров допускаются значения `NULL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Path created with _makepath: c:\sample\crt\makepath.c  
  
Path extracted with _splitpath:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: makepath  
  Ext: .c  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)