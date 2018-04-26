---
title: _getdcwd_dbg, _wgetdcwd_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
apitype: DLLExport
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b9709a5dad5bd83dc34c7e2aff7cc888b7b3451
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

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

*Диск*<br/>
Имя диска.

*buffer*<br/>
Место хранения пути.

*MaxLen*<br/>
Максимальная длина пути в символах: **char** для **_getdcwd_dbg** и **wchar_t** для **_wgetdcwd_dbg**.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения или **NULL**.

*linenumber*<br/>
Номер строки в исходном файле, которой была запрошена операция выделения или **NULL**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на *буфера*. Объект **NULL** возвращаемое значение указывает на ошибку, и **errno** устанавливается в значение **ENOMEM**, указывающее на недостаток памяти для выделения *maxlen* байт (при **NULL** аргументы заданы как *буфера*), или к **ERANGE**, указывающее на то, что путь длиннее, чем *maxlen*  символов. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Getdcwd_dbg** и **_wgetdcwd_dbg** идентичны **_getdcwd** и **_wgetdcwd** за исключением того, что, когда **_DEBUG** будет определено, эти функции используют отладочную версию **malloc** и **_malloc_dbg** для выделения памяти, если **NULL** передается как *буфера* параметра. Дополнительные сведения см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить **_CRTDBG_MAP_ALLOC** флаг. Когда **_CRTDBG_MAP_ALLOC** определен, вызовы **_getdcwd** и **_wgetdcwd** сопоставляются с **_getdcwd_dbg** и **_ wgetdcwd_dbg**, соответственно, с *blockType* значение **_NORMAL_BLOCK**. Таким образом, не требуется явно вызывать эти функции, если только необходимости пометить блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
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
