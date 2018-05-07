---
title: _spawnl, _wspawnl | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wspawnl
- _spawnl
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
- spawnl
- wspawnl
- _wspawnl
- _spawnl
dev_langs:
- C++
helpviewer_keywords:
- spawnl function
- processes, creating
- _spawnl function
- processes, executing new
- _wspawnl function
- wspawnl function
- process creation
ms.assetid: dd4584c9-7173-4fc5-b93a-6e7d3c2316d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcd276e59edd78942f14211845c615d7e4f7eb6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="spawnl-wspawnl"></a>_spawnl, _wspawnl

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnl(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL
);
intptr_t _wspawnl(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Режим выполнения для вызывающего процесса.

*cmdname*<br/>
Путь к выполняемому файлу.

*arg0*, *arg1*,... *argn*<br/>
Список указателей на аргументы. *Arg0* аргумент — указатель на *cmdname*. Аргументы *arg1* через *argn* представляют собой указатели на символьные строки, формирующие новый список аргументов. После *argn*, должно быть **NULL** указатель, отмечающий конец списка аргументов.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение синхронных функций **_spawnl** или **_wspawnl** (**_P_WAIT** указано *режим*) — это состояние завершения нового процесса. Возвращаемое значение асинхронной **_spawnl** или **_wspawnl** (**_P_NOWAIT** или **_P_NOWAITO** указано *режим* ) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает **выхода** сопоставление с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае **errno** присваивается одно из следующих значений.

|||
|-|-|
**E2BIG**|Длина списка аргументов превышает 1024 байта.
**EINVAL**|*режим* недопустимый аргумент.
**ENOENT**|Файл или путь не найден.
**ENOEXEC**|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.
**ENOMEM**|Недостаточно памяти для выполнения нового процесса.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Эти функции проверяют свои параметры. Если параметр *cmdname* или *arg0* является пустой строкой или вызывается указателем null, обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL**и возвращают -1. Нет порожденных новых процессов.

## <a name="remarks"></a>Примечания

Каждая из этих функций создает и выполняет новый процесс, передавая все аргументы командной строки как отдельные параметры.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnl**|\<process.h>|
|**_wspawnl**|\<stdio.h> или \<wchar.h>|

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
