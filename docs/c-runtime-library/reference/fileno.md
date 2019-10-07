---
title: _fileno
ms.date: 11/04/2016
api_name:
- _fileno
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: 586e390e100f5dc46a49b99c007016cf23ac68f0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957205"
---
# <a name="_fileno"></a>_fileno

Получает дескриптор файла, связанного с потоком.

## <a name="syntax"></a>Синтаксис

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**_fileno** возвращает дескриптор файла. Ошибка не возвращается. Результат не определен, если *поток* не задает открытый файл. Если Stream имеет **значение NULL**, **_fileno** вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для **errno** значение **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

> [!NOTE]
> Если **stdout** или **stderr** не связаны с выходным потоком (например, в приложении Windows без окна консоли), возвращается дескриптор файла-2. В предыдущих версиях возвращался дескриптор файла -1. Это изменение позволяет приложениям отличить это условие от ошибки.

## <a name="remarks"></a>Примечания

Подпрограммы **_fileno** возвращают дескриптор файла, который в настоящее время связан с *потоком*. Эта подпрограмма реализуется как функция и макрос. Дополнительные сведения о выборе любой реализации см. в разделе [Выбор между функциями и макросами](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fileno**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fileno.c
// This program uses _fileno to obtain
// the file descriptor for some standard C streams.
//

#include <stdio.h>

int main( void )
{
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );
}
```

```Output
The file descriptor for stdin is 0
The file descriptor for stdout is 1
The file descriptor for stderr is 2
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
