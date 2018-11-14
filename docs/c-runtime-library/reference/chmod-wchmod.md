---
title: _chmod, _wchmod
ms.date: 11/04/2016
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
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
ms.openlocfilehash: 278ee1e6dda9e153b55676ce5c0ca389f383efd1
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518415"
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

Эти функции возвращают 0, если параметр разрешений успешно изменен. Возвращаемое значение-1 указывает сбой. Если указанный файл не найден, **errno** присваивается **ENOENT**; Если же параметр недопустим, **errno** присваивается **EINVAL**.

## <a name="remarks"></a>Примечания

**_Chmod** функция изменяет параметр разрешений для файла, указанного в *filename*. Параметр разрешений управляет чтением и записью в файл. Целочисленное выражение *pmode* содержит одну или обе из следующих констант манифеста, определенных в файле SYS\Stat.h.

| *pmode* | Значение |
|-|-|
| **\_S\_IREAD** | Разрешено только чтение. |
| **\_S\_IWRITE** | Разрешена запись. (Если действует, разрешает чтение и запись.) |
| **\_S\_IREAD** &AMP;#124;  **\_S\_IWRITE** | Разрешены чтение и запись. |

Если заданы обе константы, они объединяются побитовым или оператор (**\|**). Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Обратите внимание на то, что все файлы всегда доступны для чтения; предоставить разрешение только на запись нельзя. Таким образом, режимы **_S_IWRITE** и **_S_IREAD** \| **_S_IWRITE** эквивалентны.

**_wchmod** — это двухбайтовая версия **_chmod**; *filename* аргумент **_wchmod** — строка расширенных символов. **_wchmod** и **_chmod** идентично в противном случае.

Эта функция проверяет свои параметры. Если *pmode* не является комбинацией одной из констант манифеста или включает дополнительный набор констант, функция просто их пропускает. Если *filename* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает -1.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

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
