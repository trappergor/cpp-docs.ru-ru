---
title: _lseek, _lseeki64
ms.date: 11/04/2016
apiname:
- _lseeki64
- _lseek
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lseeki64
- _lseek
- lseeki64
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
ms.openlocfilehash: 4d0320b45cb8cd99f1d9f6494b7dcb17bc545a81
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326099"
---
# <a name="lseek-lseeki64"></a>_lseek, _lseeki64

Перемещает указатель файла в заданное местоположение.

## <a name="syntax"></a>Синтаксис

```C
long _lseek(
   int fd,
   long offset,
   int origin
);
__int64 _lseeki64(
   int fd,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

*offset*<br/>
Количество байт, начиная с *origin*.

*origin*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

**_lseek** Возвращает смещение в байтах от начала файла новой позиции. **_lseeki64** Возвращает смещение в 64-разрядное целое число. Функция возвращает – 1 L для указания ошибки. Если передан недопустимый параметр, например неверный дескриптор файла, параметр *origin* имеет недопустимое значение или позиция, заданная параметром *offset*, располагается до начала файла, вызывается обработчик недопустимого параметра, как описывается в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **значение EBADF** и возвращают – 1 L. Если устройство неспособно выполнять поиск (например, терминалы и принтеры), возвращаемое значение не определено.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Lseek** функция перемещает файловый указатель, связанный с *fd* в новое расположение, *смещение* байтов из *origin*. Следующая операция в файле выполняется в новом местоположении. Аргумент *origin* должен быть одной из следующих констант, определенных в Stdio.h.

|*источник* значение||
|-|-|
| **SEEK_SET** | Начало файла. |
| **SEEK_CUR** | Текущая позиция указателя файла. |
| **SEEK_END** | Конец файла. |

Можно использовать **_lseek** можно переместить указатель в любое место в файле или за пределами файла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lseek**|\<io.h>|
|**_lseeki64**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_lseek.c
/* This program first opens a file named lseek.txt.
* It then uses _lseek to find the beginning of the file,
* to find the current position in the file, and to find
* the end of the file.
*/

#include <io.h>
#include <fcntl.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh;
   long pos;               /* Position of file pointer */
   char buffer[10];

   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );

   /* Seek the beginning of the file: */
   pos = _lseek( fh, 0L, SEEK_SET );
   if( pos == -1L )
      perror( "_lseek to beginning failed" );
   else
      printf( "Position for beginning of file seek = %ld\n", pos );

   /* Move file pointer a little */
    _read( fh, buffer, 10 );

   /* Find current position: */
   pos = _lseek( fh, 0L, SEEK_CUR );
   if( pos == -1L )
      perror( "_lseek to current position failed" );
   else
      printf( "Position for current position seek = %ld\n", pos );

   /* Set the end of the file: */
   pos = _lseek( fh, 0L, SEEK_END );
   if( pos == -1L )
      perror( "_lseek to end failed" );
   else
      printf( "Position for end of file seek = %ld\n", pos );

   _close( fh );
}
```

### <a name="input-crtlseekcinput"></a>Входные данные: crt_lseek.c_input

```Input
Line one.
Line two.
Line three.
Line four.
Line five.
```

### <a name="output"></a>Вывод

```Output
Position for beginning of file seek = 0
Position for current position seek = 10
Position for end of file seek = 57
```

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_tell, _telli64](tell-telli64.md)<br/>
