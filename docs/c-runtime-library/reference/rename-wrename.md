---
title: rename, _wrename
ms.date: 11/04/2016
api_name:
- rename
- _wrename
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
- _wrename
- _trename
- Rename
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
ms.openlocfilehash: d3d88c46fc055fb173264b40a56c755c360c7adf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949307"
---
# <a name="rename-_wrename"></a>rename, _wrename

Переименовывает файл или каталог.

## <a name="syntax"></a>Синтаксис

```C
int rename(
   const char *oldname,
   const char *newname
);
int _wrename(
   const wchar_t *oldname,
   const wchar_t *newname
);
```

### <a name="parameters"></a>Параметры

*oldname*<br/>
Указатель на старое имя.

*newname*<br/>
Указатель на новое имя.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций при успешном выполнении возвращает 0. При возникновении ошибки функция возвращает ненулевое значение **и задает для** нуля одно из следующих значений:

|Значение errno|Условие|
|-|-|
| **EACCES** | Файл или каталог, указанный в *newname*, уже существует, либо его не удалось создать (недопустимый путь); или *oldname* является каталогом, а *newname* указывает другой путь. |
| **ENOENT** | Файл или путь, указанный в *oldname*, не найден. |
| **EINVAL** | Имя содержит недопустимые символы. |

Другие возможные возвращаемые значения см. в разделе [_doserrno, _errno, syserrlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **rename** переименовывает файл или каталог, указанный в *oldname* и присваивает имя, заданное в *newname*. Старое имя должно быть путем к существующему файлу или каталогу. Новое имя не должно быть путем к существующему файлу или каталогу. Можно использовать функцию **rename** для перемещения файла из одного каталога или с одного устройства на другое, указав другой путь в аргументе *newname*. Однако нельзя использовать функцию **rename** для перемещения каталога. Каталоги можно переименовать, но нельзя перемещать.

**_wrename** — это версия **_rename**для расширенных символов; аргументы для **_wrename** являются строками расширенных символов. в противном случае **_wrename** и **_rename** ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**rename**|**rename**|**_wrename**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**rename**|\<io.h> или \<stdio.h>|
|**_wrename**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_renamer.c
/* This program attempts to rename a file named
* CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation
* to succeed, a file named CRT_RENAMER.OBJ must exist and
* a file named CRT_RENAMER.JBO must not exist.
*/

#include <stdio.h>

int main( void )
{
   int  result;
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";

   /* Attempt to rename file: */
   result = rename( old, new );
   if( result != 0 )
      printf( "Could not rename '%s'\n", old );
   else
      printf( "File '%s' renamed to '%s'\n", old, new );
}
```

### <a name="output"></a>Вывод

```Output
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
