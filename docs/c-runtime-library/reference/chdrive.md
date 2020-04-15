---
title: _chdrive
ms.date: 4/2/2020
api_name:
- _chdrive
- _o__chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 0c19fefcf6a766842ee2e25cbe6bdb61bbf48e7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333347"
---
# <a name="_chdrive"></a>_chdrive

Изменяет текущий рабочий диск.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Параметры

*Диске*<br/>
Целое число от 1 до 26, указывающее текущий рабочий диск (1 = A, 2 = B и т. д.).

## <a name="return-value"></a>Возвращаемое значение

Ноль (0), если текущий рабочий диск был успешно изменен; в противном случае возвращается −1.

## <a name="remarks"></a>Remarks

Если *диск* не находится в диапазоне от 1 до 26, обработчик недействительных параметров вызывается, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **функция _chdrive** возвращается -1, **errno** устанавливается **на EACCES,** и **_doserrno** установлен на **ERROR_INVALID_DRIVE.**

Функция **_chdrive** не является потокобезопасной, так как зависит от не безопасной для потоков функции **SetCurrentDirectory**. Для безопасного использования функции **_chdrive** в многопоточном приложении необходимо обеспечить собственный механизм синхронизации потоков. Для получения дополнительной [информации см.](/windows/win32/api/winbase/nf-winbase-setcurrentdirectory)

Функция **_chdrive** изменяет текущий рабочий диск, а функция **_chdir** — текущий рабочий каталог.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. примеры использования функции [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
