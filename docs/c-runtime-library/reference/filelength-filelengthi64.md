---
title: _filelength, _filelengthi64
ms.date: 4/2/2020
api_name:
- _filelengthi64
- _filelength
- _o__filelength
- _o__filelengthi64
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
- _filelength
- _filelengthi64
- filelengthi64
helpviewer_keywords:
- filelengthi64 function
- lengths, file
- filelength function
- _filelength function
- files [C++], length
- _filelengthi64 function
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
ms.openlocfilehash: 1a830bedc8dca65410a2df49b96c6e3bf6e11b4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346874"
---
# <a name="_filelength-_filelengthi64"></a>_filelength, _filelengthi64

Получает длину файла.

## <a name="syntax"></a>Синтаксис

```C
long _filelength(
   int fd
);
__int64 _filelengthi64(
   int fd
);
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Указывает дескриптор файла.

## <a name="return-value"></a>Возвращаемое значение

Оба **_filelength** и **_filelengthi64** вернуть длину файла, в байтах, целевого файла, связанного с *fd*. Если *fd* является недействительным дескриптором файлов, эта функция вызывает обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, обе функции возвращают -1L, чтобы указать ошибку и установить **errno** в **EBADF.**

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_filelength**|\<io.h>|
|**_filelengthi64**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [_chsize](chsize.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_fileno](fileno.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[Функции _stat, _wstat](stat-functions.md)<br/>
