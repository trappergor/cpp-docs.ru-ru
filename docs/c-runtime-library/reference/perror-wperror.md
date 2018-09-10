---
title: perror, _wperror | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wperror
- perror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wperror
- _tperror
- perror
dev_langs:
- C++
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df9e064ac7af761a858c6e18d99526a9b3c7ffb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103792"
---
# <a name="perror-wperror"></a>perror, _wperror

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

**Perror** функция выводит сообщение об ошибке для **stderr**. **_wperror** — это двухбайтовая версия **_perror**; *сообщение* аргумент **_wperror** — строка расширенных символов. **_wperror** и **_perror** идентично в противном случае.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*сообщение* сначала выводится, а затем с помощью символа двоеточия, затем следует системное сообщение об ошибке для последнего вызова библиотеки, который вызвал ошибку и, наконец, символ новой строки. Если *сообщение* является пустым указателем или указателем на строку null **perror** выводит только системное сообщение об ошибке.

Номер ошибки хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (определенной в файле ERRNO.H). Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. **perror** печатает сообщение соответствующее сообщение об ошибке с помощью **errno** значение как индекс для **_sys_errlist**. Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определяется как максимальное число элементов в **_sys_errlist** массива.

Точные результаты вызова **perror** сразу же после подпрограмма библиотеки возвращает ошибку. В противном случае последующие вызовы могут перезаписать **errno** значение.

В Windows операционная система, некоторые **errno** значений, перечисленных в ERRNO. H не используются. Эти значения зарезервированы для использования операционной системой UNIX. См. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) список **errno** значения, используемые операционной системой Windows. **perror** выводит пустую строку для любых **errno** значение не используется в этих платформах.

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
