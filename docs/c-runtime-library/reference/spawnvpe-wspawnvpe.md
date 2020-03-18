---
title: _spawnvpe, _wspawnvpe
ms.date: 11/04/2016
api_name:
- _spawnvpe
- _wspawnvpe
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _spawnvpe
- wspawnvpe
- _wspawnvpe
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
ms.openlocfilehash: 1ea71f5d7a9cd640e3d314eb48846bca995dca5c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442694"
---
# <a name="_spawnvpe-_wspawnvpe"></a>_spawnvpe, _wspawnvpe

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnvpe(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnvpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Режим выполнения для вызывающего процесса

*кмднаме*<br/>
Путь к выполняемому файлу

*argv*<br/>
Массив указателей на аргументы. Аргумент *argv*[0] обычно является указателем на путь в реальном режиме или с именем программы в защищенном режиме, а *argv*[1] через *argv*[**n**] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент *argv*[**n** + 1] должен быть **пустым** указателем, чтобы пометить конец списка аргументов.

*envp*<br/>
Массив указателей на параметры среды

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение из синхронного **_spawnvpe** или **_wspawnvpe** ( **_P_WAIT** , заданное для *режима*) — это состояние выхода нового процесса. Возвращаемое значение из асинхронного **_spawnvpe** или **_wspawnvpe** ( **_P_NOWAIT** или **_P_NOWAITO** , заданное для *режима*) — это обработчик процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Можно задать для состояния выхода ненулевое значение, если порожденный процесс явно вызывает процедуру **выхода** с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение, равное-1, указывает на ошибку (новый процесс не запущен). В этом случае для **параметра «значение возврата»** задается одно из следующих значений:

|||
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **EINVAL** | Недопустимый аргумент *mode* . |
| **ENOENT** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **ENOMEM** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды. Эти функции используют переменную среды **path** для поиска файла, который нужно выполнить.

Эти функции проверяют свои параметры. Если либо *кмднаме* , либо *argv* является пустым указателем, или если *argv* указывает на указатель null или *argv*[0] является пустой строкой, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал**и возвращают-1. Нет порожденных новых процессов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h> или \<process.h>|
|**_wspawnvpe**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>См. также раздел

[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
