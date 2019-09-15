---
title: _execlp, _wexeclp
ms.date: 11/04/2016
api_name:
- _wexeclp
- _execlp
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
- _wexeclp
- wexeclp
- _execlp
helpviewer_keywords:
- execlp function
- _execlp function
- _wexeclp function
- wexeclp function
ms.assetid: 7b179163-4bcd-4d6a-8baf-68f886791928
ms.openlocfilehash: 6ae1805dd00428aee0acca4bcb3ee221bce1d271
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937187"
---
# <a name="_execlp-_wexeclp"></a>_execlp, _wexeclp

Загружает и выполняет новые дочерние процессы.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _execlp(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL
);
intptr_t _wexeclp(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Параметры

*кмднаме*<br/>
Путь к выполняемому файлу.

*arg0*,... *argN*<br/>
Список указателей на параметры.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения эти функции не возвращаются к вызывающему процессу. Возвращаемое значение, равное-1, **указывает на ошибку** . в этом случае задается глобальная переменная «пробуждение».

|**значение по** значению|Описание|
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

Каждая из этих функций загружает и выполняет новый процесс, передавая каждый аргумент командной строки как отдельный параметр и используя переменную среды **path** для поиска файла для выполнения.

Функции **_execlp** проверяют свои параметры. Если *кмднаме* или *arg0* является пустым указателем или пустой строкой, эти функции вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают-1. Ни один новый процесс не запущен.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_execlp**|\<process.h>|\<errno.h>|
|**_wexeclp**|\<process.h> или \<wchar.h>|\<errno.h>|

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
