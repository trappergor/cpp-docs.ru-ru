---
title: _getcwd, _wgetcwd
ms.date: 11/04/2016
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: 4c533f0e716cb9a13c152b9be3c46f60291118d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331796"
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd

Получает текущий рабочий каталог.

## <a name="syntax"></a>Синтаксис

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения пути.

*MaxLen*<br/>
Максимальная длина пути в символах: **char** для **_getcwd** и **wchar_t** для **_wgetcwd**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на *буфера*. Объект **NULL** возвращаемое значение указывает на ошибку, и **errno** устанавливается в значение **ENOMEM**, том, что не хватает памяти для выделения *maxlen* байт (при **NULL** передан аргумент *буфера*), или к **ERANGE**, том, что путь не длиннее *maxlen*  символов. Если *maxlen* меньше или равен нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Getcwd** функция получает полный путь текущего рабочего каталога для диска по умолчанию и сохраняет его в *буфера*. Целочисленный аргумент *maxlen* указывает максимальную длину пути. Ошибка возникает, если длина пути (включая завершающий нуль-символ) превышает *maxlen*. *Буфера* аргументом может быть **NULL**буфер минимального размера *maxlen* (больше только при необходимости) автоматически выделяется с помощью **malloc**, для сохранения пути. Позже этот буфер можно освободить путем вызова **бесплатный** и передавая ему **_getcwd** возвращаемое значение (указатель на выделенный буфер).

**_getcwd** возвращает строку, представляющую путь к текущему рабочему каталогу. Если текущий рабочий каталог является корневым, строка заканчивается обратной косой чертой ( **\\** ). Если текущий рабочий каталог отличается от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetcwd** — это двухбайтовая версия **_getcwd**; *буфера* аргумент и возвращаемое значение **_wgetcwd** представляют собой строки расширенных символов. **_wgetcwd** и **_getcwd** идентично в противном случае.

Когда **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, вызовы функций **_getcwd** и **_wgetcwd** заменяются вызовами функций для **_ getcwd_dbg** и **_wgetcwd_dbg** чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
