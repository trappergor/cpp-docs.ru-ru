---
title: _isatty
ms.date: 11/04/2016
apiname:
- _isatty
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
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: ef0df5f859779c081df47ef4bfe938ec2601d524
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545591"
---
# <a name="isatty"></a>_isatty

Определяет, связан ли дескриптор файла с устройством символьного ввода-вывода.

## <a name="syntax"></a>Синтаксис

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, ссылающийся на проверяемое устройство.

## <a name="return-value"></a>Возвращаемое значение

**_isatty** возвращает ненулевое значение, если дескриптор связан с устройством символьного ввода. В противном случае **_isatty** возвращает 0.

## <a name="remarks"></a>Примечания

**_Isatty** функция определяет, является ли *fd* связан с устройством символьного ввода (терминал, консоль, принтер или последовательный порт).

Эта функция проверяет *fd* параметра. Если *fd* является недопустимым указателем файла, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает 0 и устанавливает **errno** для **значение EBADF**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
