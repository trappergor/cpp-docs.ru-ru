---
title: remove, _wremove | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wremove
- remove
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
- remove
- _wremove
- _tremove
dev_langs:
- C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97c258d79af8247af993732405d2c792a0822075
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="remove-wremove"></a>remove, _wremove

Удаление файла.

## <a name="syntax"></a>Синтаксис

```C
int remove(
   const char *path
);
int _wremove(
   const wchar_t *path
);
```

### <a name="parameters"></a>Параметры

*path*<br/>
Путь к файлу, который требуется удалить.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если файл был успешно удален. В противном случае возвращается значение -1 и задает **errno** либо **EACCES** для указания, что путь указывает файл только для чтения или открыт файл, или к **ENOENT** указывает, что Имя файла или путь не найден, или что путь указывает каталог.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **remove** удаляет файл, указанный в параметре *path.* **_wremove** — это двухбайтовая версия **уда_лить**; *путь* аргумент **_wremove** представляет собой строку расширенных символов. **_wremove** и **уда_лить** ведут себя идентично. Чтобы можно было удалить файл, все дескрипторы файлов должны быть закрыты.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**remove**|\<stdio.h> или \<io.h>|
|**_wremove**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_remove.c
/* This program uses remove to delete crt_remove.txt */

#include <stdio.h>

int main( void )
{
   if( remove( "crt_remove.txt" ) == -1 )
      perror( "Could not delete 'CRT_REMOVE.TXT'" );
   else
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );
}
```

### <a name="input-crtremovetxt"></a>Входные данные: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
