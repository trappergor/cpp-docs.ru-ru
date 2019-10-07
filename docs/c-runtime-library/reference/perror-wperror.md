---
title: perror, _wperror
ms.date: 11/04/2016
api_name:
- _wperror
- perror
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wperror
- _tperror
- perror
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
ms.openlocfilehash: 755b638f320fcc583faecfe6aa82269e4e1b3d8f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951034"
---
# <a name="perror-_wperror"></a>perror, _wperror

Выводит сообщение об ошибке.

## <a name="syntax"></a>Синтаксис

```C
void perror(
   const char *message
);
void _wperror(
   const wchar_t *message
);
```

### <a name="parameters"></a>Параметры

*message*<br/>
Строковое сообщение для вывода.

## <a name="remarks"></a>Примечания

Функция **perror** выводит сообщение об ошибке в **stderr**. **_wperror** — это версия **_perror**для расширенных символов; Аргумент *сообщения* для **_wperror** является строкой расширенных символов. в противном случае **_wperror** и **_perror** ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

сначала *выводится сообщение* , за которым следует двоеточие, затем — сообщение об ошибке системы для последнего вызова библиотеки, вызвавшего ошибку, и, наконец, символ новой строки. Если *Message* является пустым указателем или указателем на строку null, **perror** выводит только системное сообщение об ошибке.

Номер ошибки хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (определенной в файле ERRNO.H). Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. **perror** выводит соответствующее сообщение об ошибке **, используя значение** переводятся в качестве индекса для **_sys_errlist**. Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определяется как максимальное число элементов в массиве **_sys_errlist** .

Чтобы получить точные результаты, вызовите **perror** сразу после того, как подпрограммы библиотеки возвращают ошибку. В противном случае последующие вызовы могут перезаписать **значение** перезаписи.

В операционной системе **Windows некоторые значения** переводятся в список в диапазоне от а. H не используется. Эти значения зарезервированы для использования операционной системой UNIX. **Список значений,** используемых операционной системой Windows, см. в разделе _doserrno, перечисление, [_sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) . **perror** выводит пустую строку для **любого значения** очистки, которое не используется этими платформами.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**perror**|\<stdio.h> или \<stdlib.h>|
|**_wperror**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_perror.c
// compile with: /W3
/* This program attempts to open a file named
* NOSUCHF.ILE. Because this file probably doesn't exist,
* an error message is displayed. The same message is
* created using perror, strerror, and _strerror.
*/

#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <share.h>

int main( void )
{
   int  fh;

   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )
   {
      /* Three ways to create error message: */
      perror( "perror says open failed" );
      printf( "strerror says open failed: %s\n",
         strerror( errno ) ); // C4996
      printf( _strerror( "_strerror says open failed" ) ); // C4996
      // Note: strerror and _strerror are deprecated; consider
      // using strerror_s and _strerror_s instead.
   }
   else
   {
      printf( "open succeeded on input file\n" );
      _close( fh );
   }
}
```

```Output
perror says open failed: No such file or directory
strerror says open failed: No such file or directory
_strerror says open failed: No such file or directory
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)<br/>
