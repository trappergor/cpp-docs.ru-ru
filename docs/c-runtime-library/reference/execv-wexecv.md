---
title: _execv, _wexecv
ms.date: 4/2/2020
api_name:
- _wexecv
- _execv
- _o__execv
- _o__wexecv
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
- _execv
- _wexecv
- wexecv
helpviewer_keywords:
- _wexecv function
- _execv function
- wexecv function
- execv function
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
ms.openlocfilehash: 638364afa75fa1b04b598370473dee48964c5763
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347887"
---
# <a name="_execv-_wexecv"></a>_execv, _wexecv

Загружает и выполняет новые дочерние процессы.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _execv(
   const char *cmdname,
   const char *const *argv
);
intptr_t _wexecv(
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Параметры

*cmdname*<br/>
Путь к выполняемому файлу.

*Argv*<br/>
Массив указателей на параметры.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения эти функции не возвращаются к вызывающему процессу. Значение возврата -1 указывает на ошибку, и в этом случае установлена глобальная переменная **errno.**

|**значение errno**|Описание|
|-------------------|-----------------|
|**E2BIG**|Пространство, требуемое для аргументов и параметров среды, превышает 32 КБ.|
|**EACCES**|Указанный файл имеет нарушение блокировки или общего доступа.|
|**EINVAL**|Недопустимый параметр.|
|**EMFILE**|Открыто слишком много файлов (указанный файл необходимо открыть и определить, является ли он исполняемым).|
|**ENOENT**|Файл или путь не найдены.|
|**ENOEXEC**|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|
|**ENOMEM**|Недостаточно доступной памяти для выполнения нового процесса; либо доступная память повреждена, либо существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, а значит вызывающий процесс был выделен ненадлежащим образом.|

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая из этих функций загружает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки.

**Функции _execv** проверяют свои параметры. Если *cmdname* является нулевой указатель, или если *argv* является нулевой указатель, указатель на пустой массив, или если массив содержит пустую строку в качестве первого аргумента, **_execv** функции ссылаться на недействительный обработчик параметров, как описано в [параметр проверки](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EINVAL** и возвращают -1. Ни один процесс не запущен.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_execv**|\<process.h>|\<errno.h>|
|**_wexecv**|\<process.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec функции](../../c-runtime-library/exec-wexec-functions.md)<br/>
[Прервать](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
