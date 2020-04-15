---
title: _tell, _telli64
ms.date: 4/2/2020
api_name:
- _telli64
- _tell
- _o__tell
- _o__telli64
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
- telli64
- _telli64
- _tell
helpviewer_keywords:
- tell function
- file pointers [C++], getting
- _tell function
- file pointers [C++]
- telli64 function
- _telli64 function
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
ms.openlocfilehash: 111d5745703d15fccf0b2a941248203cc80d07a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362555"
---
# <a name="_tell-_telli64"></a>_tell, _telli64

Получает позицию указателя файла.

## <a name="syntax"></a>Синтаксис

```C
long _tell(
   int handle
);
__int64 _telli64(
   int handle
);
```

### <a name="parameters"></a>Параметры

*Обрабатывать*<br/>
Дескриптор файла, ссылающийся на открытый файл.

## <a name="return-value"></a>Возвращаемое значение

Текущая позиция указателя файла. Для устройств, которые не поддерживают поиск, возвращаемое значение не определено.

Значение возврата -1L указывает на ошибку. Если *ручка* является недействительным дескриптором файла, вызовуется обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EBADF** и возвращают -1L.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Remarks

**Функция _tell** получает текущее положение указателя файла (если таковое, связанное с аргументом *ручки.* Позиция выражается в виде количества байт от начала файла. Для **_telli64** функции это значение выражается как целый 64-битный ряд.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tell**, **_telli64**|\<io.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tell.c
// This program uses _tell to tell the
// file pointer position after a file read.
//

#include <io.h>
#include <stdio.h>
#include <fcntl.h>
#include <share.h>
#include <string.h>

int main( void )
{
   int  fh;
   char buffer[500];

   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )
   {
      char buff[50];
      _strerror_s( buff, sizeof(buff), NULL );
      printf( buff );
      exit( -1 );
   }

   if( _read( fh, buffer, 500 ) > 0 )
      printf( "Current file position is: %d\n", _tell( fh ) );
   _close( fh );
}
```

### <a name="input-crt_telltxt"></a>Входные данные: crt_tell.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Выходные данные

```Output
Current file position is: 20
```

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
