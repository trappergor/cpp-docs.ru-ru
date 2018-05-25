---
title: _chdir _wchdir | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wchdir
- _chdir
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
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs:
- C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b81ace9c9fe5cf21d93f7e7dd4a8b5f2f2c5d726
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
---
# <a name="chdir-wchdir"></a>_chdir, _wchdir

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

*каталог*<br/>
Путь к новому рабочему каталогу.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения эти функции возвращают значение 0. Возвращаемое значение-1 означает сбой. Если не удается найти указанный путь, **errno** равно **ENOENT**. Если *dirname* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает -1.

## <a name="remarks"></a>Примечания

**_Chdir** функция изменяет текущий рабочий каталог для каталога, заданного параметром *dirname*. *Dirname* должен ссылаться на существующий каталог. Эта функция может изменить текущий рабочий каталог на любом диске. Если указана новая буква диска, в *dirname*, буква диска по умолчанию также изменяется. Например, если А — буква диска по умолчанию, и \BIN — текущий рабочий каталог, следующий вызов изменит текущий рабочий каталог для диска C и установит C как новый диск по умолчанию:

```C
_chdir("c:\temp");
```

При использовании Необязательная обратная косая черта (**&#92;**) в пути, необходимо поместить две обратные косые черты (**&#92;&#92;**) в строковом литерале для представления одной обратной косой черты ( **&#92;**).

**_wchdir** — это двухбайтовая версия **_chdir**; *dirname* аргумент **_wchdir** представляет собой строку расширенных символов. **_wchdir** и **_chdir** ведут себя идентично.

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chdir**|\<direct.h>|\<errno.h>|
|**_wchdir**|\<direct.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
