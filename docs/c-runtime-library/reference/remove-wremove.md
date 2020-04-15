---
title: remove, _wremove
ms.date: 4/2/2020
api_name:
- _wremove
- remove
- _o__wremove
- _o_remove
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
ms.openlocfilehash: 6a3d7ea81b2f6b1a7e87c706ca883394e02dff3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338150"
---
# <a name="remove-_wremove"></a>remove, _wremove

Удалите файл.

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

*Путь*<br/>
Путь к файлу, который требуется удалить.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если файл был успешно удален. В противном случае он возвращает -1 и устанавливает **errno** либо в **EACCES,** чтобы указать, что путь определяет файл только для чтения, указывает каталог, или файл открыт, или **ENOENT,** чтобы указать, что имя файла или путь не найден.

Для получения дополнительной информации об этих и других кодах возврата смотрите [_doserrno, errno, _sys_errlist и _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Remarks

Функция **remove** удаляет файл, указанный в параметре *path.* **_wremove** является широкохарактерным вариантом **_remove;** *аргумент пути* к **_wremove** является широкохарактерной строкой. **_wremove** и **_remove** ведут себя одинаково иначе. Чтобы можно было удалить файл, все дескрипторы файлов должны быть закрыты.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**удаление**|**удаление**|**_wremove**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**удаление**|\<stdio.h> или \<io.h>|
|**_wremove**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

### <a name="sample-output"></a>Пример выходных данных

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
