---
title: _getdcwd, _wgetdcwd
ms.date: 4/2/2020
api_name:
- _getdcwd
- _wgetdcwd
- _o__getdcwd
- _o__wgetdcwd
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3a4ca8ff3f1153893282c65bc4c2becd687138ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344400"
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

*Диске*<br/>
Неотрицательное целое число, которое определяет диск (0 — диск по умолчанию, 1 — A, 2 — B и т. д.).

Если указанный диск недоступен или тип диска (например, съемный, фиксированный, CD-ROM, диск оперативной памяти или сетевой диск) не может быть определен, недействительный параметр обработчик вызывается. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

*Буфера*<br/>
Место хранения для пути или **NULL**.

Если **null** указан, эта функция выделяет буфер по крайней мере *maxlen* размера с помощью **malloc**, и значение возврата **_getdcwd** является указателем на выделенный буфер. Буфер можно освободить, позвонив **бесплатно** и передав его указателем.

*макслен*<br/>
Ненулевой положительный ряд, который определяет максимальную длину пути, в символах: **символ** для **_getdcwd** и **wchar_t** для **_wgetdcwd**.

Если *maxlen* меньше или равен нулю, вызывается обработчик недействительных параметров. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку, представляющую полный путь текущего рабочего каталога на указанном диске, или **NULL,** который указывает на ошибку.

Если *буфер* указан как **NULL** и не хватает памяти для выделения *символов maxlen,* происходит ошибка и **errno** устанавливается на **ENOMEM.** Если длина пути, включая термин null, превышает *maxlen,* возникает ошибка, и **errno** устанавливается на **ERANGE.** Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_getdcwd** получает полный путь текущего рабочего каталога на указанном диске и хранит его в *буфере.* Если текущей рабочей папкой является корневой каталог, строка заканчивается обратной косой чертой (\\). Если текущая рабочая папка находится в каталоге, отличном от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetdcwd** представляет собой широкохарактерную версию **_getdcwd,** а ее параметр *буфера* и значение возврата представляют собой широкохарактерные строки. В противном случае **_wgetdcwd** и **_getdcwd** ведут себя одинаково.

Эта функция потокобезопасна, даже если она зависит от функции **GetFullPathName**, которая сама не потокобезопасна. Однако можно нарушить потокобезопасность, если многопоточное приложение вызывает и эту функцию, и функцию [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew).

Версия этой функции, которая имеет **_nolock** суффикс ведет себя одинаково, чтобы эта функция, за исключением того, что он не является нитовым и не защищен от помех другими потоками. Для получения дополнительной информации см. [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

При определении **_DEBUG** и **_CRTDBG_MAP_ALLOC** вызовы **_getdcwd** и **_wgetdcwd** заменяются вызовами **_getdcwd_dbg** и **_wgetdcwd_dbg,** чтобы можно было отладить распределение памяти. Дополнительные сведения см. в разделе[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
