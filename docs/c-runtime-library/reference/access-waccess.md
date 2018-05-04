---
title: _access _waccess | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 775d0b699c6ac9664bae8cd0e6e28438ef019e69
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="access-waccess"></a>_access, _waccess

Определяет, доступен ли файл только для чтения или нет. Существуют более безопасные версии этих функций; см. раздел [_access_s, _waccess_s](access-s-waccess-s.md).

## <a name="syntax"></a>Синтаксис

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Параметры

*path*<br/>
Путь к файлу или каталогу.

*mode*<br/>
Атрибут чтения и записи.

## <a name="return-value"></a>Возвращаемое значение

Если файл имеет заданный режим, все функции возвращают значение 0. Функция возвращает -1, если файл с именем не существует или не имеет заданный режим; в этом случае **errno** установлено, как показано в следующей таблице.

|||
|-|-|
**EACCES**|Доступ запрещен: настройка разрешений файла не допускает указанный доступ.
**ENOENT**|Имя файла или путь не найдены.
**EINVAL**|Недопустимый параметр.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

При использовании с файлами, **_access** функция определяет, является ли указанный файл или каталог существует и имеет атрибуты, указанные по значению *режим*. При использовании с каталогами, **_access** только определяет, существует ли указанный каталог, в Windows 2000 и более поздних версий операционных систем, все каталоги на чтение и запись.

|*режим* значение|Проверяет файл на|
|------------------|---------------------|
|00|Существование|
|02|Только на запись|
|04|Только чтение|
|06|Чтение и запись|

Эта функция проверяет только то, является ли файл или каталог доступным только для чтения; параметры безопасности файловой системы не проверяются. Для этого требуется токен доступа. Дополнительные сведения о безопасности файловой системы см. в разделе [Токены доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909). Для использования этой функции предназначен класс ATL, см. раздел [Класс CAccessToken](../../atl/reference/caccesstoken-class.md).

**_waccess** — это двухбайтовая версия **_access**; *путь* аргумент **_waccess** представляет собой строку расширенных символов. **_waccess** и **_access** ведут себя идентично.

Эта функция проверяет свои параметры. Если *путь* — **NULL** или *режим* не указан недопустимый режим, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция устанавливает **errno** для **EINVAL** и возвращает значение -1.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_taccess**|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> или \<io.h>|\<errno.h>|

## <a name="example"></a>Пример

В следующем примере используется **_access** для проверки файла с именем crt_ACCESS. C существование и допустимость записи.

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Functions](stat-functions.md)<br/>
