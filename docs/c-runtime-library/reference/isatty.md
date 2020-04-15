---
title: _isatty
ms.date: 4/2/2020
api_name:
- _isatty
- _o__isatty
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: c9611c2bd55ebc1602a73e4c71518716ea100420
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343906"
---
# <a name="_isatty"></a>_isatty

Определяет, связан ли дескриптор файла с устройством символьного ввода-вывода.

## <a name="syntax"></a>Синтаксис

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Дескриптор файла, ссылающийся на проверяемое устройство.

## <a name="return-value"></a>Возвращаемое значение

**_isatty** возвращает значение ненулевого, если дескриптор связан с устройством символов. В противном случае **_isatty** возвращает 0.

## <a name="remarks"></a>Remarks

Функция **_isatty** определяет, связан ассоциируется ли *fd* с устройством символов (терминал, консоль, принтер или серийный порт).

Эта функция проверяет параметр *fd.* Если *fd* является плохой указателем файла, вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращает 0 и устанавливает **errno** в **EBADF.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

### <a name="sample-output"></a>Пример выходных данных

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
