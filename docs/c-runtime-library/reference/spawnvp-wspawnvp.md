---
title: _spawnvp, _wspawnvp
ms.date: 4/2/2020
api_name:
- _wspawnvp
- _spawnvp
- _o__spawnvp
- _o__wspawnvp
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wspawnvp
- _spawnvp
- wspawnvp
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
ms.openlocfilehash: ee6d6155c06bb174a6ffd1e29cda0d73cbd2da32
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355752"
---
# <a name="_spawnvp-_wspawnvp"></a>_spawnvp, _wspawnvp

Создает и выполняет процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnvp(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnvp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Параметры

*Режим*<br/>
Режим выполнения для вызова процесса.

*cmdname*<br/>
Путь к выполняемому файлу.

*Argv*<br/>
Массив указателей на аргументы. Аргумент *argv*, как правило, указатель на путь в реальном режиме или на название программы в защищенном режиме, и *argv*через *argv***n**n - указатели на строки персонажа, которые образуют новый список аргументов. Аргумент *argv***n** no 1 должен быть указателем **NULL,** чтобы отметить конец списка аргументов.

## <a name="return-value"></a>Возвращаемое значение

Значение возврата от синхронного **_spawnvp** или **_wspawnvp** **(_P_WAIT,** указанное для *режима)* является состоянием выхода нового процесса. Значение возврата из асинхронного **_spawnvp** или **_wspawnvp** **(_P_NOWAIT** или **_P_NOWAITO,** указанное для *режима)* является ручкой процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Статус выхода можно установить на ненулевое значение, если нереститы специально используют ненулевой аргумент для вызова рутины **выхода.** Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Значение возврата -1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** устанавливается на одно из следующих значений:

|||
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **EINVAL** | *аргумент режима* недействителен. |
| **ENOENT** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **ENOMEM** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая из этих функций создает новый процесс и выполняет его, передает массив указателей аргументам командной строки и использует переменную среды **PATH** для поиска файла для выполнения.

Эти функции проверяют свои параметры. Если или *cmdname* или *argv* является нулевой указатель, или если *argv* указывает на нулевую указатель, или *argv*»0» является пустой строки, недействительный обработчик параметров вызывается, как описано в [параметрвалиции](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции установить **errno** к **EINVAL**, и вернуть -1. Нет порожденных новых процессов.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h> или \<process.h>|
|**_wspawnvp**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_spawn, _wspawn Functions](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Прервать](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec функции](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
