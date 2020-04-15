---
title: _getcwd, _wgetcwd
description: C Runtime Library функционирует _getcwd, _wgetcwd получить текущий рабочий каталог.
ms.date: 4/2/2020
api_name:
- _wgetcwd
- _getcwd
- _o__getcwd
- _o__wgetcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: bc19a416ebebeb901e8dbb435971e6d5f33e4067
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344433"
---
# <a name="_getcwd-_wgetcwd"></a>_getcwd, _wgetcwd

Возвращает текущий рабочий каталог.

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

*Буфера*\
Место хранения пути.

*макслен*\
Максимальная длина пути в символах: **символ** для **_getcwd** и **wchar_t** для **_wgetcwd.**

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в *буфер.* Значение возврата **NULL** указывает на ошибку, и **errno** устанавливается либо **на ENOMEM,** указывая на то, что не хватает памяти для выделения *байтов maxlen* (когда аргумент **NULL** дается в качестве *буфера),* либо **eRANGE**, указывая, что путь длиннее, чем *символы maxlen.* Если *maxlen* меньше или равен нулю, эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md)

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_getcwd** получает полный путь текущего рабочего каталога для диска по умолчанию и хранит его в *буфере.* В истеге аргумент *maxlen* определяет максимальную длину пути. Ошибка возникает, если длина пути (включая термин null) превышает *maxlen.* *Аргумент буфера* может быть **NULL;** буфер по крайней мере размер *maxlen* (больше только при необходимости) автоматически выделяется, используя **malloc**, для хранения пути. Этот буфер позже может быть освобожден, вызывая **свободный** и передавая его **_getcwd** значение возврата (указатель на выделенный буфер).

**_getcwd** возвращает строку, представляющую путь текущего рабочего каталога. Если текущий рабочий каталог является корнем, строка`\`заканчивается с backslash ( ). Если текущий рабочий каталог отличается от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetcwd** является широкохарактерным вариантом **_getcwd;** *аргумент буфера* и значение возврата **_wgetcwd** являются строками широкого характера. **_wgetcwd** и **_getcwd** ведут себя одинаково иначе.

При определении **_DEBUG** и **_CRTDBG_MAP_ALLOC** вызовы **_getcwd** и **_wgetcwd** заменяются вызовами **_getcwd_dbg** и **_wgetcwd_dbg** для отладки распределения памяти. Дополнительные сведения см. в разделе [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getcwd.c
// Compile with: cl /W4 crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h> // _getcwd
#include <stdlib.h> // free, perror
#include <stdio.h>  // printf
#include <string.h> // strlen

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if ( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %zu\n", buffer, strlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>См. также раздел

[Управление каталогом](../../c-runtime-library/directory-control.md)\
[_chdir, _wchdir](chdir-wchdir.md)\
[_mkdir, _wmkdir](mkdir-wmkdir.md)\
[_rmdir, _wrmdir](rmdir-wrmdir.md)
