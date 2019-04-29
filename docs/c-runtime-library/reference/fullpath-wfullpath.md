---
title: _fullpath, _wfullpath
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: aeacaf581b7f33ee893754c192ae547376ce73ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287646"
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
Указатель на буфер, содержащий абсолютный или полный путь, или **NULL**.

*relPath*<br/>
Относительный путь.

*MaxLength*<br/>
Максимальная длина буфера абсолютного пути имя (*absPath*). Длина указывается в байтах для **_fullpath** и в расширенных символах (**wchar_t**) для **_wfullpath**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на буфер, содержащий абсолютный путь (*absPath*). Если возникает ошибка (например, в том случае, если значение, переданное в *relPath* содержит букву диска, который является недопустимым или не найден, или если длина имени создаваемого абсолютного пути (*absPath*) больше, чем *maxLength*), функция возвращает **NULL**.

## <a name="remarks"></a>Примечания

**_Fullpath** функция разворачивает относительный путь в *relPath* в его полный или абсолютный путь и сохраняет его в *absPath*. Если *absPath* — **NULL**, **malloc** выделяется буфер надлежащей длины для хранения пути. Освобождение этого буфера — обязанность вызывающего объекта. Относительный путь указывает путь в другое расположение из текущего расположения (например, текущей рабочей папки: "."). Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы. В отличие от **_makepath**, **_fullpath** может быть использован для получения абсолютный путь для относительных путей (*relPath*), которые включают «. / «или».. /» в именах.

Например, чтобы использовать подпрограммы среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления подпрограмм. Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом (из рабочей папки приложения):

```C
#include <stdlib.h>
```

когда абсолютный путь (реальное расположение в файловой системе) файла может иметь вид:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** автоматически обрабатывает многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящий момент. **_wfullpath** — это двухбайтовая версия **_fullpath**; строковые аргументы **_wfullpath** представляют собой строки расширенных символов. **_wfullpath** и **_fullpath** ведут себя одинаково, за исключением случаев, **_wfullpath** не обрабатывает многобайтовые строки.

Если **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, вызовы **_fullpath** и **_wfullpath** заменяются вызовами функций для **_fullpath_dbg** и **_wfullpath_dbg** чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Эта функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md), если *maxlen* меньше или равно 0. Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **NULL**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Если *absPath* буфера **NULL**, **_fullpath** вызовы [malloc](malloc.md) выделить буфер и игнорирует *maxLength*  аргумент. Корректное освобождение этого буфера (с помощью функции [free](free.md)) — обязанность вызывающего объекта. Если *relPath* аргумент определяет диск, текущий каталог этого диска объединяется с путем.

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
