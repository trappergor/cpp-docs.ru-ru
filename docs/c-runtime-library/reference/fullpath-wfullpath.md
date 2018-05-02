---
title: _fullpath, _wfullpath | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f619bae0c3d6d0d3f45e4c8ee6b25458f10007e4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath

Создает абсолютный или полный путь для указанного относительного пути.

## <a name="syntax"></a>Синтаксис

```C
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

### <a name="parameters"></a>Параметры

*absPath*<br/>
Указатель на буфер, содержащий абсолютный или полный путь, или NULL.

*relPath*<br/>
Относительный путь.

*maxLength*<br/>
Максимальная длина буфера абсолютного пути (*absPath*). Длина указывается в байтах для **_fullpath** и в расширенных символах (**wchar_t**) для **_wfullpath**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на буфер, содержащий абсолютный путь (*absPath*). Если возникает ошибка (например, в том случае, если значение, переданное в *relPath* содержит букву диска, который является недопустимым или не удается найти, или если длина созданного абсолютного пути (*absPath*) больше, чем *maxLength*), функция возвращает **NULL**.

## <a name="remarks"></a>Примечания

**_Fullpath** функция расширяет относительный путь в *relPath* полностью или абсолютный путь и сохраняет это имя в *absPath*. Если *absPath* имеет значение NULL, **malloc** выделяется буфер надлежащей длины для хранения пути. Освобождение этого буфера — обязанность вызывающего объекта. Относительный путь указывает путь в другое расположение из текущего расположения (например, текущей рабочей папки: "."). Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы. В отличие от **_makepath**, **_fullpath** может быть использован для получения абсолютный путь для относительных путей (*relPath*), которые включают «. / «или».. /» в их именах.

Например, чтобы использовать подпрограммы среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления подпрограмм. Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом (из рабочей папки приложения):

```C
#include <stdlib.h>
```

когда абсолютный путь (реальное расположение в файловой системе) файла может иметь вид:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** автоматически требуемым образом обрабатывает аргументы строки многобайтовых символов соответствующим образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой страницей в настоящий момент. **_wfullpath** — это двухбайтовая версия **_fullpath**; строковые аргументы функции **_wfullpath** представляют собой строки расширенных символов. **_wfullpath** и **_fullpath** ведут себя одинаково, за исключением того, что **_wfullpath** не обрабатывает многобайтовые строки.

Если **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, вызовы **_fullpath** и **_wfullpath** заменяются вызовами функций для **_fullpath_dbg** и **_wfullpath_dbg** чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Эта функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md), если *maxlen* меньше или равно 0. Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **NULL**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Если *absPath* буфер **NULL**, **_fullpath** вызовы [malloc](malloc.md) для выделения буфера и игнорирует *maxLength*  аргумент. Корректное освобождение этого буфера (с помощью функции [free](free.md)) — обязанность вызывающего объекта. Если *relPath* аргумент определяет диск, текущий каталог этого диска объединяется с путем.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
