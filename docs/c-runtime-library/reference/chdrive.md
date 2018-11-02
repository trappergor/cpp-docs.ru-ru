---
title: _chdrive
ms.date: 11/04/2016
apiname:
- _chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 963b7b7b40b632981abfc1529beb9c48a5b991ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602310"
---
# <a name="chdrive"></a>_chdrive

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

*Диск*<br/>
Целое число от 1 до 26, указывающее текущий рабочий диск (1 = A, 2 = B и т. д.).

## <a name="return-value"></a>Возвращаемое значение

Ноль (0), если текущий рабочий диск был успешно изменен; в противном случае возвращается −1.

## <a name="remarks"></a>Примечания

Если *диск* находится не в диапазоне от 1 до 26, вызывается обработчик недопустимых параметров, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_chdrive** функция возвращает -1, **errno** присваивается **EACCES**, и **_doserrno** присваивается  **ERROR_INVALID_DRIVE**.

Функция **_chdrive** не является потокобезопасной, так как зависит от не безопасной для потоков функции **SetCurrentDirectory**. Для безопасного использования функции **_chdrive** в многопоточном приложении необходимо обеспечить собственный механизм синхронизации потоков. Дополнительные сведения см. в разделе [SetCurrentDirectory](/windows/desktop/api/winbase/nf-winbase-setcurrentdirectory).

Функция **_chdrive** изменяет текущий рабочий диск, а функция **_chdir** — текущий рабочий каталог.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. примеры использования функции [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
