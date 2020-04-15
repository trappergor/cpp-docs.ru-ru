---
title: _chdir, _wchdir
ms.date: 4/2/2020
api_name:
- _wchdir
- _chdir
- _o__chdir
- _o__wchdir
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
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
ms.openlocfilehash: a3f224e68e4b5a43274616892012ceba737d6d17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333388"
---
# <a name="_chdir-_wchdir"></a>_chdir, _wchdir

Изменяет текущий рабочий каталог.

## <a name="syntax"></a>Синтаксис

```C
int _chdir(
   const char *dirname
);
int _wchdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Параметры

*dirname*<br/>
Путь к новому рабочему каталогу.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения эти функции возвращают значение 0. Значение возврата -1 указывает на сбой. Если указанный путь не может быть найден, **errno** устанавливается на **ENOENT**. Если *dirname* **null,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается на **EINVAL** и функция возвращается -1.

## <a name="remarks"></a>Remarks

Функция **_chdir** изменяет текущий рабочий каталог в каталог, указанный *dirname.* Параметр *dirname* должен относиться к существующему каталогу. Эта функция может изменить текущий рабочий каталог на любом диске. Если новая буква диска указана в *dirname,* письмо диска по умолчанию также изменяется. Например, если А — буква диска по умолчанию, и \BIN — текущий рабочий каталог, следующий вызов изменит текущий рабочий каталог для диска C и установит C как новый диск по умолчанию:

```C
_chdir("c:\temp");
```

Когда вы используете дополнительный backslash характер** (&#92;**) в путях, вы должны поместить два backslashes** (&#92;&#92;**) в строке C буквально представлять один backslash** (&#92;). **

**_wchdir** является широкохарактерным вариантом **_chdir;** *аргумент dirname* к **_wchdir** является широкохарактерной строкой. **_wchdir** и **_chdir** ведут себя одинаково иначе.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chdir**|\<direct.h>|\<errno.h>|
|**_wchdir**|\<direct.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_chdir.c
// arguments: C:\WINDOWS

/* This program uses the _chdir function to verify
   that a given directory exists. */

#include <direct.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int argc, char *argv[] )
{

   if(_chdir( argv[1] ) )
   {
      switch (errno)
      {
      case ENOENT:
         printf( "Unable to locate the directory: %s\n", argv[1] );
         break;
      case EINVAL:
         printf( "Invalid buffer.\n");
         break;
      default:
         printf( "Unknown error.\n");
      }
   }
   else
      system( "dir *.exe");
}
```

```Output
Volume in drive C has no label.
Volume Serial Number is 2018-08A1

Directory of c:\windows

08/29/2002  04:00 AM         1,004,032 explorer.exe
12/17/2002  04:43 PM            10,752 hh.exe
03/03/2003  09:24 AM            33,792 ieuninst.exe
10/29/1998  04:45 PM           306,688 IsUninst.exe
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE
03/03/2003  09:24 AM            33,792 Q330994.exe
08/29/2002  04:00 AM           134,144 regedit.exe
02/28/2003  06:26 PM            46,352 setdebug.exe
08/29/2002  04:00 AM            15,360 TASKMAN.EXE
08/29/2002  04:00 AM            49,680 twunk_16.exe
08/29/2002  04:00 AM            25,600 twunk_32.exe
08/29/2002  04:00 AM           256,192 winhelp.exe
08/29/2002  04:00 AM           266,752 winhlp32.exe
              13 File(s)      2,249,184 bytes
               0 Dir(s)  67,326,029,824 bytes free
```

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
