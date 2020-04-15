---
title: _spawnv, _wspawnv
ms.date: 4/2/2020
api_name:
- _wspawnv
- _spawnv
- _o__spawnv
- _o__wspawnv
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
- wspawnv
- _spawnv
- _wspawnv
helpviewer_keywords:
- wspawnv function
- processes, creating
- _spawnv function
- processes, executing new
- process creation
- _wspawnv function
- spawnv function
ms.assetid: 72360ef4-dfa9-44c1-88c1-b3ecb660aa7d
ms.openlocfilehash: f4a4d695e265c28efd1b9da8588752d8b2635163
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355897"
---
# <a name="_spawnv-_wspawnv"></a>_spawnv, _wspawnv

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnv(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnv(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Параметры

*Режим*<br/>
Режим выполнения для вызывающего процесса.

*cmdname*<br/>
Путь к выполняемому файлу.

*Argv*<br/>
Массив указателей на аргументы. Аргумент *argv*, как правило, указатель на путь в реальном режиме или на название программы в защищенном режиме, и *argv*через *argv***n**- указатели на строки персонажа, формирующие новый список аргументов. Аргумент *argv***n** no 1 должен быть указателем **NULL,** чтобы отметить конец списка аргументов.

## <a name="return-value"></a>Возвращаемое значение

Значение возврата от синхронного **_spawnv** или **_wspawnv** **(_P_WAIT,** указанное для *режима)* является состоянием выхода нового процесса. Значение возврата от асинхронного **_spawnv** или **_wspawnv** **(_P_NOWAIT** или **_P_NOWAITO,** указанные для *режима)* является ручкой процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Статус выхода можно установить на ненулевое значение, если нереститы конкретно вызывает рутину **выхода** с ненулевой аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Значение возврата -1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** устанавливается на одно из следующих значений.

|||
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **EINVAL** | *аргумент режима* недействителен. |
| **ENOENT** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **ENOMEM** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки.

Эти функции проверяют свои параметры. Если или *cmdname* или *argv* является нулевой указатель, или если *argv* указывает на нулевую указатель, или *argv*»0» является пустой строки, недействительный обработчик параметров вызывается, как описано в [параметрвалиции](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции установить **errno** к **EINVAL**, и вернуть -1. Нет порожденных новых процессов.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnv**|\<stdio.h> или \<process.h>|
|**_wspawnv**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
