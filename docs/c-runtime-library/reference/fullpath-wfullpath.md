---
title: "_fullpath, _wfullpath | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fullpath
- _wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9874d4c0b3576f79880d95a04285be9ff299c7c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath
Создает абсолютный или полный путь для указанного относительного пути.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `absPath`  
 Указатель на буфер, содержащий абсолютный или полный путь, или NULL.  
  
 `relPath`  
 Относительный путь.  
  
 `maxLength`  
 Максимальная длина буфера абсолютного пути (`absPath`). Длина указывается в байтах для `_fullpath` и в расширенных символах (`wchar_t`) для `_wfullpath`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на буфер, содержащий абсолютный путь (`absPath`). Если произошла ошибка (например, если значение, переданное в параметре `relPath`, содержит букву диска, который является недопустимым или не может быть найден, или если длина создаваемого абсолютного пути (`absPath`) больше `maxLength`), функция возвращает значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 `_fullpath` Функция расширяет относительный путь в `relPath` полностью или абсолютный путь и сохраняет это имя в `absPath`. Если параметр `absPath` имеет значение NULL, с помощью функции `malloc` выделяется буфер надлежащей длины для хранения пути. Освобождение этого буфера — обязанность вызывающего объекта. Относительный путь указывает путь в другое расположение из текущего расположения (например, текущей рабочей папки: "."). Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы. В отличие от функции `_makepath`, функцию `_fullpath` можно использовать для получения абсолютного пути из относительных путей (`relPath`), содержащих в себе "./" или "../".  
  
 Например, чтобы использовать подпрограммы среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления подпрограмм. Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом (из рабочей папки приложения):  
  
```  
#include <stdlib.h>  
```  
  
 когда абсолютный путь (реальное расположение в файловой системе) файла может иметь вид:  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 Функция `_fullpath` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей. `_wfullpath` — это версия функции `_fullpath` для расширенных символов; аргументы строки для функции `_wfullpath` представляют собой строки расширенных символов. В остальных отношениях поведение функций `_wfullpath` и `_fullpath` идентично, за исключением того, что функция `_wfullpath` не обрабатывает многобайтовые строки.  
  
 Если определены директивы `_DEBUG` и `_CRTDBG_MAP_ALLOC`, вызовы функций `_fullpath` и `_wfullpath` заменяются вызовами функций `_fullpath_dbg` и `_wfullpath_dbg`, чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_fullpath_dbg, _wfullpath_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md), если значение `maxlen` меньше или равно 0. Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `NULL`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Если буфер `absPath` имеет значение `NULL`, функция `_fullpath` вызывает функцию [malloc](../../c-runtime-library/reference/malloc.md), чтобы выделить буфер, и игнорирует аргумент `maxLength`. Корректное освобождение этого буфера (с помощью функции [free](../../c-runtime-library/reference/free.md)) — обязанность вызывающего объекта. Если аргумент `relPath` определяет диск, текущий каталог этого диска объединяется с путем.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h>|  
|`_wfullpath`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Full path is: C:\Documents and Settings\user\My Documents\test  
Full path is: C:\test  
Full path is: C:\Documents and Settings\user\test  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)