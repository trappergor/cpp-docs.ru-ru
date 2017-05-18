---
title: "_makepath_s, _wmakepath_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmakepath_s
- _makepath_s
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
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
dev_langs:
- C++
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0d3ac02a0ac8dfa7f681c8585be7e1b6f41f0f82
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s
Создает путь из компонентов. Это версии функции [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствование безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 [выходной] `path`  
 Буфер полного пути.  
  
 [in] `sizeInWords`  
 Размер буфера в словах.  
  
 [in] `sizeInBytes`  
 Размер буфера в байтах.  
  
 [in] `drive`  
 Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. Если двоеточие отсутствует, функция `_makepath_s` вставляет ее в составной путь автоматически. Если параметр `drive` имеет значение `NULL` или указывает на пустую строку, в составной строке `path` буква диска не отображается.  
  
 [in] `dir`  
 Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Конечная косая черта является необязательной; в одном аргументе `dir` могут использоваться косая черта (/), обратная косая черта (\\) или обе. Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если параметр `dir` имеет значение `NULL` или указывает на пустую строку, путь каталога не вставляется в составную строку `path`.  
  
 [in] `fname`  
 Содержит базовое имя файла без расширений. Если параметр `fname` имеет значение `NULL` или указывает на пустую строку, имя файла не вставляется в составную строку `path`.  
  
 [in] `ext`  
 Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. Функция `_makepath_s` вставляет точку автоматически, если она отсутствует в параметре `ext`. Если параметр `ext` имеет значение `NULL` или указывает на пустую строку, расширение не вставляется в составную строку `path`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`path`|`sizeInWords` / `sizeInBytes`|Назад|Содержимое `path`|  
|------------|------------------------------------|------------|------------------------|  
|`NULL`|любые|`EINVAL`|не изменено|  
|any|<= 0|`EINVAL`|не изменено|  
  
 Если возникает любое из указанных выше условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для параметра `errno` устанавливается значение `EINVAL`, и функция возвращает значение `EINVAL`. Значение `NULL` допускается для параметров `drive`, `fname` и `ext`. Дополнительные сведения о поведении в случае, когда эти параметры являются указателями NULL или пустыми строками, см. в разделе примечаний.  
  
## <a name="remarks"></a>Примечания  
 Функция `_makepath_s` создает строку составного пути из отдельных компонентов, сохраняя результат в параметре `path`. Путь `path` может включать букву диска, путь к каталогу, имя файла и расширение имени файла. `_wmakepath_s` — это двухбайтовая версия `_makepath_s`; аргументы для `_wmakepath_s` представляют собой двухбайтовые строки. Поведение `_wmakepath_s` и `_makepath_s` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 Аргумент `path` должен указывать на пустой буфер достаточного для хранения полного пути размера. Размер составного пути `path` не должен быть больше константы `_MAX_PATH`, определенной в файле Stdlib.h.  
  
 Если параметр path имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того, для параметра `errno` устанавливается значение `EINVAL`. Для всех остальных параметров допускаются значения `NULL`.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_makepath_s`|\<stdlib.h>|  
|`_wmakepath_s`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="output"></a>Вывод  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)
