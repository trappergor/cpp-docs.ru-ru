---
title: _get_osfhandle
ms.date: 4/2/2020
api_name:
- _get_osfhandle
- _o__get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: a12c0c93ae15350a4b91a8aa905acb941f8b6a10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345028"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

Получает дескриптор файла операционной системы, связанный с указанным дескриптором файла.

## <a name="syntax"></a>Синтаксис

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Дескриптор существующего файла.

## <a name="return-value"></a>Возвращаемое значение

Возвращает ручку файла операционной системы, если *fd* действителен. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, он **возвращается INVALID_HANDLE_VALUE** (-1). Он также устанавливает **errno** к **EBADF**, указывая недействительную ручку файла. Чтобы избежать предупреждения, когда результат используется в качестве ручки файла Win32, отбросьте его в тип **HANDLE.**

> [!NOTE]
> Когда **stdin,** **stdout**и **stderr** не связаны с потоком (например, в приложении Windows без окна консоли), значения дескриптора файлов для этих потоков возвращаются из [_fileno](fileno.md) как специальное значение -2. Аналогичным образом, если вы используете 0, 1 или 2 в качестве параметра дескриптора файла вместо результата вызова **_fileno,** **_get_osfhandle** также возвращает специальное значение -2, когда дескриптор файла не связан с потоком, и не устанавливает **errno.** Однако это не является допустимой ценностью обработки файлов, и последующие вызовы, которые пытаются использовать ее, скорее всего, потерпят неудачу.

Для получения дополнительной информации о **EBADF** и других кодах ошибок, [см. _doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Чтобы закрыть файл, ручка файла операционной системы (ОС) получена **_get_osfhandle,** позвоните [_close](close.md) на *fd*дескриптора файла. Никогда не вызывайте **CloseHandle** на возвратное значение этой функции. Базовая ручка файла OS принадлежит дескриптору файла *fd* и закрывается, когда [_close](close.md) называется *fd.* Если дескриптор файла принадлежит `FILE *` потоку, то вызов `FILE *` [прикосновений](fclose-fcloseall.md) на этом потоке закрывает как дескриптор файла, так и основную ручку файла ОС. В этом случае не звоните [_close](close.md) на дескриптор файла.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
