---
title: _cwait
description: Справочник по API для функции среды выполнения Microsoft Visual C `_cwait()` .
ms.date: 10/23/2020
api_name:
- _cwait
- _o__cwait
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: 5b4c4db3c40645b947583b722d345c2e80dcaa8e
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639111"
---
# <a name="_cwait"></a>_cwait

Ожидает завершения другого процесса.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>Параметры

*`termstat`*\
Указатель на буфер, где будет сохранен код результата указанного процесса, или **`NULL`** .

*`procHandle`*\
Обработчик ожидания процесса (то есть процесс, который должен завершиться до того, как **_cwait** может вернуть).

*`action`*\
**`NULL`** : Игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения *`procHandle`* .

## <a name="return-value"></a>Возвращаемое значение

После успешного завершения указанного процесса возвращает маркер указанного процесса и задает *`termstat`* результирующий код, возвращаемый указанным процессом. В противном случае возвращает значение-1 и задает **`errno`** , как показано ниже.

|Значение|Описание|
|-----------|-----------------|
|**`ECHILD`**|Указанный процесс не существует, *`procHandle`* недопустим, или [`GetExitCodeProcess`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) [`WaitForSingleObject`](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) не удалось вызвать API или.|
|**`EINVAL`**|*`action`* является недопустимым.|

Дополнительные сведения об этих и других кодах возврата см. в разделе [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Remarks

**`_cwait`** Функция ожидает завершения процесса с идентификатором указанного процесса, предоставленного *`procHandle`* . Значение *`procHandle`* , передаваемое в, **`_cwait`** должно быть значением, возвращаемым вызовом [`_spawn`](../../c-runtime-library/spawn-wspawn-functions.md) функции, создавшей указанный процесс. Если идентификатор процесса завершается до **`_cwait`** вызова, функция **`_cwait`** возвращает значение немедленно. **`_cwait`** может использоваться любым процессом для ожидания любого другого известного процесса, для которого существует допустимый Handle ( *`procHandle`* ).

*`termstat`* Указывает на буфер, где будет храниться код возврата указанного процесса. Значение *`termstat`* указывает, завершается ли указанный процесс обычным образом путем вызова API Windows [`ExitProcess`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) . **`ExitProcess`** вызывается внутренним образом, если указанный процесс вызывает метод **`exit`** или **`_exit`** , возвращает **`main`** значение из или достигает конца **`main`** . Дополнительные сведения о значении, которое передается обратно *`termstat`* , см. в разделе [жетекситкодепроцесс](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Если **`_cwait`** метод вызывается с использованием **`NULL`** значения для *`termstat`* , код возврата указанного процесса не сохраняется.

Этот *`action`* параметр игнорируется операционной системой Windows, так как связи типа «родители-потомки» не реализованы в этих средах.

Если *`procHandle`* не равно-1 или-2 (обрабатывает текущий процесс или поток), дескриптор будет закрыт. В этом случае не используйте возвращенный обработчик.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**`_cwait`**|\<process.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Например, .

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
    intptr_t hProcess;
    char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main(int argc, char* argv[])
{
    int termstat, c;
    unsigned int number;

    srand((unsigned)time(NULL));    // Seed randomizer

    // If no arguments, this is the calling process
    if (argc == 1)
    {
        // Spawn processes in numeric order
        for (c = 0; c < 4; c++) {
            _flushall();
            process[c].hProcess = _spawnl(_P_NOWAIT, argv[0], argv[0],
                process[c].name, NULL);
        }

        // Wait for randomly specified process, and respond when done
        c = getrandom(0, 3);
        printf("Come here, %s.\n", process[c].name);
        _cwait(&termstat, process[c].hProcess, _WAIT_CHILD);
        printf("Thank you, %s.\n", process[c].name);

    }
    // If there are arguments, this must be a spawned process
    else
    {
        // Delay for a period that's determined by process number
        Sleep((argv[1][0] - 'A' + 1) * 1000L);
        printf("Hi, Dad. It's %s.\n", argv[1]);
    }
}
```

Порядок выходных данных зависит от запуска для выполнения.

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>См. также статью

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)\
[_spawn, функции _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)
