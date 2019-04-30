---
title: _spawnvp, _wspawnvp
ms.date: 11/04/2016
apiname:
- _wspawnvp
- _spawnvp
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: b697eabd7a45eedbf9c892acee570a9e8b818d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355137"
---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp

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

*mode*<br/>
Режим выполнения для вызова процесса.

*cmdname*<br/>
Путь к выполняемому файлу.

*argv*<br/>
Массив указателей на аргументы. Аргумент *argv*[0] обычно является указателем на путь в режиме реального времени или на имя программы в защищенном режиме, и *argv*[1] через *argv*[**n**] являются указателями на строки символов, которые образуют новый список аргументов. Аргумент *argv*[**n** + 1] должен быть **NULL** указатель для обозначения конца списка аргументов.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение синхронных функций **_spawnvp** или **_wspawnvp** (**_P_WAIT** для *режим*) — это состояние завершения нового процесса . Возвращаемое значение асинхронной **_spawnvp** или **_wspawnvp** (**_P_NOWAIT** или **_P_NOWAITO** указанный для  *режим*) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Состояния выхода можно задать ненулевое значение, если порожденный процесс использует ненулевой аргумент для вызова **выйти из** подпрограммы. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** присваивается одно из следующих значений:

|||
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **EINVAL** | *режим* аргумент является недопустимым. |
| **ENOENT** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **ENOMEM** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций создает новый процесс и выполняет его и передает массив указателей на аргументы командной строки и использует **путь** для поиска выполняемого файла переменную среды.

Эти функции проверяют свои параметры. Если параметр *cmdname* или *argv* является пустым указателем, или если *argv* указывает на указатель null или *argv*[0] представляет собой пустую строку, Недопустимая подпись вызывается обработчик параметров, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL**и возвращают -1. Нет порожденных новых процессов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h> или \<process.h>|
|**_wspawnvp**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
