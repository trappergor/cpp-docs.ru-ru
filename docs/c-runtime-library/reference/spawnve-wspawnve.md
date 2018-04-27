---
title: _spawnve, _wspawnve | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _spawnve
- _wspawnve
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
- wspawnve
- _spawnve
- _wspawnve
- spawnve
dev_langs:
- C++
helpviewer_keywords:
- _spawnve function
- spawnve function
- wspawnve function
- processes, creating
- _wspawnve function
- processes, executing new
- process creation
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff11a55bb9ba6a5a77255be34cb794c15e471f77
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="spawnve-wspawnve"></a>_spawnve, _wspawnve

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnve(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnve(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Режим выполнения для вызывающего процесса.

*cmdname*<br/>
Путь к выполняемому файлу.

*argv*<br/>
Массив указателей на аргументы. Аргумент *argv*[0] обычно находится указателем на путь в реальном режиме или на имя программы в защищенном режиме, и *argv*[1] по *argv*[**n**] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент *argv*[**n** + 1] должен быть **NULL** указатель, отмечающий конец списка аргументов.

*envp*<br/>
Массив указателей на параметры среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение синхронных функций **_spawnve** или **_wspawnve** (**_P_WAIT** указано *режим*) — это состояние завершения нового процесса . Возвращаемое значение асинхронной **_spawnve** или **_wspawnve** (**_P_NOWAIT** или **_P_NOWAITO** указано  *режим*) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает **выхода** сопоставление с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** присваивается одно из следующих значений.

|||
|-|-|
**E2BIG**|Длина списка аргументов превышает 1024 байта.
**EINVAL**|*режим* недопустимый аргумент.
**ENOENT**|Файл или путь не найден.
**ENOEXEC**|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.
**ENOMEM**|Недостаточно памяти для выполнения нового процесса.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды.

Эти функции проверяют свои параметры. Если параметр *cmdname* или *argv* является пустым указателем, или, если *argv* указывает на указатель null или *argv*[0] является пустой строкой, недопустим вызывается обработчик параметров, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL**и возвращают -1. Нет порожденных новых процессов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnve**|\<stdio.h> или \<process.h>|
|**_wspawnve**|\<stdio.h> или \<wchar.h>|

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
