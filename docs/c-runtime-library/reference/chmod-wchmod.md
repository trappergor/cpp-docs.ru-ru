---
title: _chmod _wchmod | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _chmod
- _wchmod
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
- _chmod
- _wchmod
- wchmod
dev_langs:
- C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8194e6bdaf93c4bc2cbbc8c2ff2fdf23df438a5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="chmod-wchmod"></a>_chmod, _wchmod

Изменяет параметры разрешений файла.

## <a name="syntax"></a>Синтаксис

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя существующего файла.

*pmode*<br/>
Настройка разрешений для файла.

## <a name="return-value"></a>Возвращаемое значение

Эти функции возвращают 0, если параметр разрешений успешно изменен. Возвращаемое значение-1 означает сбой. Если не удается найти указанный файл, **errno** равно **ENOENT**; Если параметр является допустимым, **errno** равно **EINVAL**.

## <a name="remarks"></a>Примечания

**_Chmod** функция изменяет настройки разрешений файла, указанного *filename*. Параметр разрешений управляет чтением и записью в файл. Целочисленное выражение *pmode* содержит одно или оба из следующих констант манифеста, определенная в SYS\Stat.h.

|*pmode*|Значение|
|-|-|
**_S_IREAD**|Разрешено только чтение.
**_S_IWRITE**|Разрешена запись. (Если действует, разрешает чтение и запись.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Разрешены чтение и запись.

Если заданы обе константы, они объединяются побитовым или оператор (**|**). Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Обратите внимание на то, что все файлы всегда доступны для чтения; предоставить разрешение только на запись нельзя. Таким образом, режимы **_S_IWRITE** и **_S_IREAD** | **_S_IWRITE** эквивалентны.

**_wchmod** — это двухбайтовая версия **_chmod**; *filename* аргумент **_wchmod** представляет собой строку расширенных символов. **_wchmod** и **_chmod** ведут себя идентично.

Эта функция проверяет свои параметры. Если *pmode* не является сочетанием одного из констант манифеста или включает дополнительный набор констант, функция просто игнорирует их. Если *filename* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает -1.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wchmod**|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_chmod.c
// This program uses _chmod to
// change the mode of a file to read-only.
// It then attempts to modify the file.
//

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

// Change the mode and report error or success
void set_mode_and_report(char * filename, int mask)
{
   // Check for failure
   if( _chmod( filename, mask ) == -1 )
   {
      // Determine cause of failure and report.
      switch (errno)
      {
         case EINVAL:
            fprintf( stderr, "Invalid parameter to chmod.\n");
            break;
         case ENOENT:
            fprintf( stderr, "File %s not found\n", filename );
            break;
         default:
            // Should never be reached
            fprintf( stderr, "Unexpected error in chmod.\n" );
       }
   }
   else
   {
      if (mask == _S_IREAD)
        printf( "Mode set to read-only\n" );
      else if (mask & _S_IWRITE)
        printf( "Mode set to read/write\n" );
   }
   fflush(stderr);
}

int main( void )
{

   // Create or append to a file.
   system( "echo /* End of file */ >> crt_chmod.c_input" );

   // Set file mode to read-only:
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );

   system( "echo /* End of file */ >> crt_chmod.c_input " );

   // Change back to read/write:
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );

   system( "echo /* End of file */ >> crt_chmod.c_input " );
}
```

```Output

A line of text.

```

```Output

      A line of text.Mode set to read-only
Access is denied.
Mode set to read/write
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Functions](stat-functions.md)<br/>
