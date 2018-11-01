---
title: _getdrive
ms.date: 11/04/2016
apiname:
- _getdrive
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
- _getdrive
- getdrive
helpviewer_keywords:
- current disk drive
- getdrive function
- disk drives
- _getdrive function
ms.assetid: e40631a0-8f1a-4897-90ac-e1037ff30bca
ms.openlocfilehash: d71f72c00cc384d5f4f69d8a58dbcfb7aa39332f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470685"
---
# <a name="getdrive"></a>_getdrive

Получает текущий диск.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _getdrive( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает текущий (используемый по умолчанию) диск (1=A, 2=B и т. д). Ошибка не возвращается.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdrive**|\<direct.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getdrive.c
// compile with: /c
// Illustrates drive functions including:
//    _getdrive       _chdrive        _getdcwd
//

#include <stdio.h>
#include <direct.h>
#include <stdlib.h>
#include <ctype.h>

int main( void )
{
   int ch, drive, curdrive;
   static char path[_MAX_PATH];

   // Save current drive.
   curdrive = _getdrive();

   printf( "Available drives are:\n" );

   // If we can switch to the drive, it exists.
   for( drive = 1; drive <= 26; drive++ )
   {
      if( !_chdrive( drive ) )
      {
         printf( "%c:", drive + 'A' - 1 );
         if( _getdcwd( drive, path, _MAX_PATH ) != NULL )
            printf( " (Current directory is %s)", path );
         putchar( '\n' );
      }
   }

   // Restore original drive.
   _chdrive( curdrive );
}
```

```Output
Available drives are:
A: (Current directory is A:\)
C: (Current directory is C:\)
E: (Current directory is E:\testdir\bin)
F: (Current directory is F:\)
G: (Current directory is G:\)
```

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdrive](chdrive.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
