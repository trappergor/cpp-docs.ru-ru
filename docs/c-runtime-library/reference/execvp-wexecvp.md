---
title: _execvp, _wexecvp | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _execvp
- _wexecvp
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
- _execvp
- wexecvp
- _wexecvp
dev_langs:
- C++
helpviewer_keywords:
- _execvp function
- _wexecvp function
- wexecvp function
- execvp function
ms.assetid: a4db15df-b204-4987-be7c-de84c3414380
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 952f98e508d0814ee7f4e45f80d242777944382d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="execvp-wexecvp"></a>_execvp, _wexecvp

Загружает и выполняет новые дочерние процессы.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _execvp(
   const char *cmdname,
   const char *const *argv
);
intptr_t _wexecvp(
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Параметры

*cmdname*<br/>
Путь к выполняемому файлу.

*argv*<br/>
Массив указателей на параметры.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения эти функции не возвращаются к вызывающему процессу. Возвращаемое значение-1 указывает на ошибку в этом случае **errno** имеет значение глобальной переменной.

|**errno** значение|Описание|
|-------------------|-----------------|
|**E2BIG**|Пространство, требуемое для аргументов и параметров среды, превышает 32 КБ.|
|**EACCES**|Указанный файл имеет нарушение блокировки или общего доступа.|
|**EINVAL**|Недопустимый параметр.|
|**EMFILE**|Открыто слишком много файлов (указанный файл необходимо открыть и определить, является ли он исполняемым).|
|**ENOENT**|Файл или путь не найдены.|
|**ENOEXEC**|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|
|**ENOMEM**|Недостаточно доступной памяти для выполнения нового процесса; либо доступная память повреждена, либо существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, а значит вызывающий процесс был выделен ненадлежащим образом.|

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций загружает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки, а также с помощью **путь** для поиска выполняемого файла в переменную среды.

**_Execvp** функции проверяют свои параметры. Если *cmdname* является пустым указателем, или *argv* является пустым указателем, указателем на пустой массив или массив содержит пустую строку в качестве первого аргумента, эти функции вызывают обработчик недопустимого параметра как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают -1. Ни один процесс не запущен.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_execvp**|\<process.h>|\<errno.h>|
|**_wexecvp**|\<process.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
