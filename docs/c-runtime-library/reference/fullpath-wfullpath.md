---
title: _fullpath, _wfullpath
ms.date: 4/2/2020
api_name:
- _fullpath
- _wfullpath
- _o__fullpath
- _o__wfullpath
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 0910cf4f39e00be84e683cd6f3b9afbeb3f2a749
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345489"
---
# <a name="_fullpath-_wfullpath"></a>_fullpath, _wfullpath

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
Указатель на буфер, содержащий абсолютное или полное имя пути, или **NULL**.

*relPath*<br/>
Относительный путь.

*maxLength*<br/>
Максимальная длина буфера имени абсолютного пути *(absPath).* Эта длина в байтах для **_fullpath** но в широких характерах **(wchar_t**) для **_wfullpath.**

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель в буфер, содержащий абсолютное имя пути *(absPath).* Если есть ошибка (например, если значение, пройденное в *relPath* включает в себя дисковое письмо, которое не является действительным или не может быть найдено, или если длина созданного абсолютного имени пути *(absPath)* больше, чем *maxLength),* функция возвращает **NULL**.

## <a name="remarks"></a>Remarks

Функция **_fullpath** расширяет имя относительного пути в *relPath* до его полностью квалифицированного или абсолютного пути и хранит это имя в *absPath.* Если *absPath* **null,** **malloc** используется для выделения буфера достаточной длины для удержания имени пути. Освобождение этого буфера — обязанность вызывающего объекта. Относительный путь указывает путь в другое расположение из текущего расположения (например, текущей рабочей папки: "."). Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы. В отличие от **_makepath,** **_fullpath** может быть использован для получения абсолютного названия пути для относительных путей *(relPath),* которые включают "./" или ". /" на их имена.

Например, чтобы использовать подпрограммы среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления подпрограмм. Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом (из рабочей папки приложения):

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

когда абсолютный путь (реальное расположение в файловой системе) файла может иметь вид:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтовым кодом, который используется в настоящее время. **_wfullpath** является широкохарактерным вариантом **_fullpath;** строка аргументы **_wfullpath** являются широкохарактерные строки. **_wfullpath** и **_fullpath** ведут себя одинаково, за исключением того, что **_wfullpath** не обрабатывает строки с мультибайт-символами.

Если **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, вызовы **_fullpath** и **_wfullpath** заменяются вызовами **_fullpath_dbg** и **_wfullpath_dbg,** позволяющими отлажовать распределение памяти. Дополнительные сведения см. в разделе [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметра,](../../c-runtime-library/parameter-validation.md)если *maxlen* меньше или равна 0. Если выполнение разрешено продолжать, эта функция устанавливает **errno** **к EINVAL** и возвращает **NULL**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Если буфер *absPath* **null,** **_fullpath** вызывает [malloc](malloc.md) для того чтобы выделить буфер и игнорирует аргумент *maxLength.* Корректное освобождение этого буфера (с помощью функции [free](free.md)) — обязанность вызывающего объекта. Если аргумент *relPath* определяет диск, текущий каталог этого диска совмещен с траекторией.

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
