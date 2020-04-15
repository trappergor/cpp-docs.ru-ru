---
title: _chmod, _wchmod
ms.date: 4/2/2020
api_name:
- _chmod
- _wchmod
- _o__chmod
- _o__wchmod
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
ms.openlocfilehash: faceb49c921162da042f863abbebbe2ef0a52153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350094"
---
# <a name="_chmod-_wchmod"></a>_chmod, _wchmod

Изменяет параметры разрешений файла.

## <a name="syntax"></a>Синтаксис

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Параметры

*Имени файла*<br/>
Имя существующего файла.

*pmode*<br/>
Настройка разрешений для файла.

## <a name="return-value"></a>Возвращаемое значение

Эти функции возвращают 0, если параметр разрешений успешно изменен. Значение возврата -1 указывает на сбой. Если указанный файл не может быть найден, **errno** устанавливается на **ENOENT**; если параметр недействителен, **errno** устанавливается в **EINVAL.**

## <a name="remarks"></a>Remarks

Функция **_chmod** изменяет настройку разрешения файла, указанную *по имени файла.* Параметр разрешений управляет чтением и записью в файл. В истеже *выражении pmode* содержится одна или обе следующие константы манифеста, определенные в SYS-Stat.h.

| *pmode* | Значение |
|-|-|
| **\_S\_IREAD** | Разрешено только чтение. |
| **\_S\_IWRITE** | Разрешена запись. (Если действует, разрешает чтение и запись.) |
| **\_S\_IREAD** &#124; ** \_\_S IWRITE** | Разрешены чтение и запись. |

Когда обе константы даны, они соединены**\|** с bitwise или оператором ( ). Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Обратите внимание на то, что все файлы всегда доступны для чтения; предоставить разрешение только на запись нельзя. Таким образом, режимы **_S_IWRITE** и **_S_IWRITE** **_S_IREAD** \| являются эквивалентными.

**_wchmod** является широкохарактерным вариантом **_chmod;** аргумент *имени файла* для **_wchmod** является широкохарактерной строкой. **_wchmod** и **_chmod** ведут себя одинаково иначе.

Эта функция проверяет свои параметры. Если *pmode* не является сочетанием одной из явных констант или включает в себя альтернативный набор констант, функция просто игнорирует их. Если *имя файла* **NULL,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается на **EINVAL** и функция возвращается -1.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wchmod**|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[Функции _stat, _wstat](stat-functions.md)<br/>
