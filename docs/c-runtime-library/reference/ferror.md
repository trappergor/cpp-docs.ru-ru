---
title: ferror
ms.date: 11/04/2016
apiname:
- ferror
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
- ferror
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
ms.openlocfilehash: 2be90ffe8a135b4108abd9504099bd2f6c28f249
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587893"
---
# <a name="ferror"></a>ferror

Проверяет наличие ошибок в потоке.

## <a name="syntax"></a>Синтаксис

```C
int ferror(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Если ошибки не произошло на *поток*, **ferror** возвращает 0. В противном случае возвращается ненулевое значение. Если поток имеет **NULL**, **ferror** вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает значение 0.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Ferror** (реализованная и как функция и как макрос) проверяет для чтения или записи ошибок в файле, связанном с *поток*. Если произошла ошибка, индикатор ошибки для потока остается установленным до закрытия или на начало потока или пока не **clearerr** вызывается на ее основе.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**ferror**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [feof](feof.md).

## <a name="see-also"></a>См. также

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
