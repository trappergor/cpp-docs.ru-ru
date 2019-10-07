---
title: remove, _wremove
ms.date: 11/04/2016
api_name:
- _wremove
- remove
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remove
- _wremove
- _tremove
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
ms.openlocfilehash: 2ceedcf9d3cc2b26a8d91ca923f81f0ce539b64a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949434"
---
# <a name="remove-_wremove"></a>remove, _wremove

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

Каждая из этих функций возвращает 0, если файл был успешно удален. В противном случае возвращается-1 и **устанавливается значение** **еакцес** , чтобы указать, что путь указывает на файл только для чтения, указывает каталог, Открытый файл или **еноент** , чтобы указать, что имя файла или путь не найдены.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **remove** удаляет файл, указанный в параметре *path.* **_wremove** — это версия **_удалить**для расширенных символов; Аргумент *path* для **_wremove** является строкой расширенных символов. поведение **_wremove** и **_удалить** идентично в противном случае. Чтобы можно было удалить файл, все дескрипторы файлов должны быть закрыты.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

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

### <a name="input-crt_removetxt"></a>Входные данные: crt_remove.txt

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
