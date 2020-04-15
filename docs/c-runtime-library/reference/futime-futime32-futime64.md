---
title: _futime, _futime32, _futime64
ms.date: 4/2/2020
api_name:
- _futime64
- _futime32
- _futime
- _o__futime32
- _o__futime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 1f60bb3b366c48e3d53368f81ebc2528694794f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345504"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

Задает время изменения открытого файла.

## <a name="syntax"></a>Синтаксис

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Дескриптор открытого файла.

*Filetime*<br/>
Указатель на структуру, содержащую новую дату изменения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха. Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функция возвращается -1 и **errno** устанавливается **в EBADF,** указывая недействительный дескриптор файла, или **EINVAL**, с указанием недействительного параметра.

## <a name="remarks"></a>Remarks

**В _futime** рутина устанавливает дату изменения и время доступа в открытый файл, связанный с *fd.* **_futime** идентичен [_utime,](utime-utime32-utime64-wutime-wutime32-wutime64.md)за исключением того, что его аргументом является дескриптор файла открытого файла, а не имя файла или путь к файлу. Структура **_utimbuf** содержит поля для новой даты изменения и времени доступа. Оба поля должны содержать допустимые значения. **_utimbuf32** и **_utimbuf64** идентичны **_utimbuf,** за исключением использования 32-битных и 64-битных типов времени, соответственно. **_futime** и **_utimbuf** использовать 64-битный тип времени, и **_futime** идентичен по поведению **_futime64.** Если вам нужно заставить старое поведение, определить **_USE_32BIT_TIME_T**. Это приводит к **тому, что _futime** идентичен по поведению **_futime32** и приводит к тому, что структура **_utimbuf** использует 32-битный тип времени, что эквивалентно **__utimbuf32.**

**_futime64**, который использует **__utimbuf64** структуру, может читать и изменять даты файлов через 23:59:59, 31 декабря 3000, UTC; в то время как вызов **_futime32** не удается, если дата в файле позже, чем 23:59:59 18 января 2038, UTC. Полночь 1-го января 1970 года — нижняя граница диапазона дат для этих функций.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>Входные данные: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
