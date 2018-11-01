---
title: _futime, _futime32, _futime64
ms.date: 11/04/2016
apiname:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: f21e394acdcc7fbf8a91c5450a4c04daa050db21
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652508"
---
# <a name="futime-futime32-futime64"></a>_futime, _futime32, _futime64

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

*fd*<br/>
Дескриптор открытого файла.

*FILETIME*<br/>
Указатель на структуру, содержащую новую дату изменения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха. Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и **errno** присваивается **значение EBADF**, указывающее, является недопустимым дескриптором файла, или **EINVAL**, указывающее, при использовании недопустимого параметр.

## <a name="remarks"></a>Примечания

**_Futime** подпрограмма задает дату и время доступа для открытого файла, связанного с *fd*. **_futime** идентична [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md), за исключением того, что ее аргумент принимает дескриптор файла, открытого файла, а не имя файла или путь к файлу. **_Utimbuf** структура содержит поля с новой датой изменения и время доступа. Оба поля должны содержать допустимые значения. **_utimbuf32** и **_utimbuf64** идентичны **_utimbuf** Однако используют 32-разрядных и 64-разрядных времени типов, соответственно. **_futime** и **_utimbuf** использовать 64-разрядный тип времени и **_futime** функционирует аналогично результату для **_futime64**. Если необходимо применить старое поведение принудительно, определите **_USE_32BIT_TIME_T**. Связи с этим функция **_futime** быть идентична по поведению **_futime32** и вызывает **_utimbuf** структуре, чтобы использовать 32-разрядный тип времени, делая его эквивалентным **__utimbuf32**.

**_futime64**, которая использует **__utimbuf64** структуры, можно считывать и изменять файл даты до 23:59:59 31 декабря 3000 года в формате UTC; в то время как вызов **_futime32** завершается неудачей, если дата файла позже 23:59:59 18 января 2038 года в формате UTC. Полночь 1-го января 1970 года — нижняя граница диапазона дат для этих функций.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

### <a name="input-crtfutimecinput"></a>Входные данные: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>Пример результатов выполнения

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

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
