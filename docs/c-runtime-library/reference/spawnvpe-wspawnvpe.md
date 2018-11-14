---
title: _spawnvpe, _wspawnvpe
ms.date: 11/04/2016
apiname:
- _spawnvpe
- _wspawnvpe
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
- _spawnvpe
- wspawnvpe
- spawnvpe
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
ms.openlocfilehash: a98cc3c441261a92876b94e1231e66bb71e9d3d9
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326606"
---
# <a name="spawnvpe-wspawnvpe"></a>_spawnvpe, _wspawnvpe

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

*cmdname*<br/>
Путь к выполняемому файлу

*argv*<br/>
Массив указателей на аргументы. Аргумент *argv*[0] обычно является указателем на путь в режиме реального времени или на имя программы в защищенном режиме, и *argv*[1] через *argv*[**n**] являются указателями на строки символов, формирующие новый список аргументов. Аргумент *argv*[**n** + 1] должен быть **NULL** указатель для обозначения конца списка аргументов.

*envp*<br/>
Массив указателей на параметры среды

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение синхронных функций **_spawnvpe** или **_wspawnvpe** (**_P_WAIT** для *режим*) — это состояние завершения нового процесс. Возвращаемое значение асинхронной **_spawnvpe** или **_wspawnvpe** (**_P_NOWAIT** или **_P_NOWAITO** указанный для  *режим*) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает **выйти из** подпрограмму с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** присваивается одно из следующих значений:

|||
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **EINVAL** | *режим* аргумент является недопустимым. |
| **ENOENT** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **ENOMEM** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды. Эти функции используют **путь** для поиска выполняемого файла переменную среды.

Эти функции проверяют свои параметры. Если параметр *cmdname* или *argv* является пустым указателем, или если *argv* указывает на указатель null или *argv*[0] представляет собой пустую строку, Недопустимая подпись вызывается обработчик параметров, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL**и возвращают -1. Нет порожденных новых процессов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h> или \<process.h>|
|**_wspawnvpe**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>См. также

[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
