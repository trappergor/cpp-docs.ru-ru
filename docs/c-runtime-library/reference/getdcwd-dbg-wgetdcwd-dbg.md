---
title: _getdcwd_dbg, _wgetdcwd_dbg
ms.date: 11/04/2016
api_name:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
ms.openlocfilehash: 8eb22f3716102c1b63b483e493eb44ac99228004
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955233"
---
# <a name="_getdcwd_dbg-_wgetdcwd_dbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

Отладочные версии функций [_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md) (доступны только во время отладки).

## <a name="syntax"></a>Синтаксис

```C
char *_getdcwd_dbg(
   int drive,
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetdcwd_dbg(
   int drive,
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*диск*<br/>
Имя диска.

*buffer*<br/>
Место хранения пути.

*maxlen*<br/>
Максимальная длина пути в символах: **char** для **_getdcwd_dbg** и **wchar_t** для **_wgetdcwd_dbg**.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция выделения, или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на *буфер*. Возвращаемое значение **null** указывает на ошибку **, а для** свойства «вывод» установлено значение **еномем**, указывающее, что недостаточно памяти для выделения *maxlen* байт (если аргумент **null** задан как *buffer*) или **ERANGE** , указывающее, что длина пути превышает *maxlen* символов. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функции **_getdcwd_dbg** и **_wgetdcwd_dbg** идентичны **_getdcwd** и **_wgetdcwd** , за исключением того, что при определении **_DEBUG** эти функции используют отладочную версию функций **malloc** и **_malloc_dbg** для выделить память, если в качестве параметра *буфера* передается **значение NULL** . Дополнительные сведения см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг **_CRTDBG_MAP_ALLOC** . Если определен **_CRTDBG_MAP_ALLOC** , вызовы методов **_getdcwd** и **_wgetdcwd** пересопоставляются с **_getdcwd_dbg** и **_wgetdcwd_dbg**соответственно, а *блокктипе* устанавливается в **_NORMAL_BLOCK**. Таким образом, не нужно явно вызывать эти функции, если не нужно помечать блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
