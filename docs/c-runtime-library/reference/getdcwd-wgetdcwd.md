---
title: _getdcwd, _wgetdcwd
ms.date: 11/04/2016
api_name:
- _getdcwd
- _wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: 3b67e04e914baf85545fcde63cf27c86bc15fac1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956026"
---
# <a name="_getdcwd-_wgetdcwd"></a>_getdcwd, _wgetdcwd

Получает полный путь текущей рабочей папки на указанном диске.

## <a name="syntax"></a>Синтаксис

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Параметры

*диск*<br/>
Неотрицательное целое число, которое определяет диск (0 — диск по умолчанию, 1 — A, 2 — B и т. д.).

Если указанный диск недоступен или не удается определить тип диска (например, съемный, стационарный, компакт-диск, электронный диск или сетевой диск), вызывается обработчик недопустимых параметров. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

*buffer*<br/>
Место хранения для пути или **NULL**.

Если указано **значение NULL** , эта функция выделяет буфер по крайней мере *maxlen* размера с помощью функции **malloc**, а возвращаемое значение **_getdcwd** — это указатель на выделенный буфер. Буфер можно освободить, вызвав **Free** и передав ему указатель.

*maxlen*<br/>
Ненулевое положительное число, указывающее максимальную длину пути в символах: **char** для **_getdcwd** и **wchar_t** для **_wgetdcwd**.

Если *maxlen* меньше или равно нулю, вызывается обработчик недопустимых параметров. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку, представляющую полный путь к текущему рабочему каталогу на указанном диске, или **значение NULL**, которое указывает на ошибку.

Если для параметра *buffer* задано **значение NULL** и недостаточно памяти для выделения *maxlen* символов, возникает ошибка **, а для** свойства "переводится" значение **еномем**. Если длина пути, в том числе завершающего нуль-символа, превышает *maxlen*, возникает ошибка, а **параметру** "ключ вывода" присваивается значение **ERANGE**. Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_getdcwd** возвращает полный путь к текущему рабочему каталогу на указанном диске и сохраняет его в *буфере*. Если текущей рабочей папкой является корневой каталог, строка заканчивается обратной косой чертой (\\). Если текущая рабочая папка находится в каталоге, отличном от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetdcwd** — это версия **_getdcwd**для расширенных символов, ее параметр *buffer* и возвращаемое значение представляют собой строки расширенных символов. В противном случае поведение **_wgetdcwd** и **_getdcwd** работает одинаково.

Эта функция потокобезопасна, даже если она зависит от функции **GetFullPathName**, которая сама не потокобезопасна. Однако можно нарушить потокобезопасность, если многопоточное приложение вызывает и эту функцию, и функцию [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew).

Версия этой функции, которая имеет суффикс **_nolock** , ведет себя идентично этой функции, за исключением того, что она не является потокобезопасной и не защищена от помех в других потоках. Для получения дополнительной информации см. [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

При определении **_DEBUG** и **_CRTDBG_MAP_ALLOC** вызовы методов **_getdcwd** и **_wgetdcwd** заменяются вызовами **_getdcwd_dbg** и **_wgetdcwd_dbg** , что позволяет отлаживать выделение памяти. Дополнительные сведения см. в разделе[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
