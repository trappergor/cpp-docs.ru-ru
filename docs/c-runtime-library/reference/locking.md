---
title: _locking
ms.date: 11/04/2016
apiname:
- _locking
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
- _locking
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
ms.openlocfilehash: 90327ed3388d4f18e0f64f92c33112c9ddd800f5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327048"
---
# <a name="locking"></a>_locking

Блокирует или разблокирует байт файла.

## <a name="syntax"></a>Синтаксис

```C
int _locking(
   int fd,
   int mode,
   long nbytes
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла.

*mode*<br/>
Выполняемое действие блокировки.

*nbytes*<br/>
Число байтов для блокировки.

## <a name="return-value"></a>Возвращаемое значение

**_locking** возвращает 0 в случае успеха. Возвращаемое значение-1 указывает на ошибку; в этом случае [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается одно из следующих значений.

|Значение errno|Условие|
|-|-|
| **EACCES** | Нарушение блокировки (файл уже заблокирован или разблокирован). |
| **EBADF** | Недопустимый дескриптор файла. |
| **EDEADLOCK** | Нарушение блокировки. Возвращается, когда **_LK_LOCK** или **_LK_RLCK** установлен флаг и файл не может быть заблокирован после 10 попыток. |
| **EINVAL** | Недопустимый аргумент был присвоен **_locking**. |

Если сбой происходит из-за недопустимого параметра, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Примечания

**_Locking** функция блокирует или разблокирует *nbytes* байт из файла, указанного в *fd*. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Все блокировки или разблокировки начинаются с текущего положения указателя файла и распространяются на следующие *nbytes* байт. Возможна блокировка байтов за концом файла.

Параметр *mode* должен быть одной из следующих констант манифеста, определенных в файле Locking.h.

|*режим* значение|Действие|
|-|-|
| **_LK_LOCK** | Блокирует указанные байты. Если заблокировать байты не удается, программа попытается повторить блокировку через 1 секунду. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку. |
| **_LK_NBLCK** | Блокирует указанные байты. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку. |
| **_LK_NBRLCK** | Совпадение с кодом **_LK_NBLCK**. |
| **_LK_RLCK** | Совпадение с кодом **_LK_LOCK**. |
| **_LK_UNLCK** | Разблокирует указанные байты, которые предварительно должны быть заблокированы. |

Можно заблокировать несколько разделов файла, которые не перекрываются. Разблокируемый раздел файла должен быть предварительно заблокирован. **_locking** объединяет смежные разделы; Если два заблокированных раздела являются смежными, каждый регион должен быть разблокирован отдельно. Разделы следует блокировать только на короткое время. Их необходимо разблокировать перед закрытием файла или выходом из программы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_locking**|\<io.h> и \<sys/locking.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_locking.c
/* This program opens a file with sharing. It locks
* some bytes before reading them, then unlocks them. Note that the
* program works correctly only if the file exists.
*/

#include <sys/types.h>
#include <sys/stat.h>
#include <sys/locking.h>
#include <share.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <io.h>

int main( void )
{
   int  fh, numread;
   char buffer[40];

   /* Quit if can't open file or system doesn't
    * support sharing.
    */
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,
                          _S_IREAD | _S_IWRITE );
   printf( "%d %d\n", err, fh );
   if( err != 0 )
      exit( 1 );

   /* Lock some bytes and read them. Then unlock. */
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )
   {
      long lseek_ret;
      printf( "No one can change these bytes while I'm reading them\n" );
      numread = _read( fh, buffer, 30 );
      buffer[30] = '\0';
      printf( "%d bytes read: %.30s\n", numread, buffer );
      lseek_ret = _lseek( fh, 0L, SEEK_SET );
      _locking( fh, LK_UNLCK, 30L );
      printf( "Now I'm done. Do what you will with them\n" );
   }
   else
      perror( "Locking failed\n" );

   _close( fh );
}
```

### <a name="input-crtlockingtxt"></a>Входные данные: crt_locking.txt

```Input
The first thirty bytes of this file will be locked.
```

## <a name="sample-output"></a>Пример результатов выполнения

```Output
No one can change these bytes while I'm reading them
30 bytes read: The first thirty bytes of this
Now I'm done. Do what you will with them
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
