---
title: _cwait
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d54f62c8ce391b2c8ead92a0a73ac48e6f2b3cb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348150"
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

*термсрок*<br/>
Указатель на буфер, где будет храниться код результата указанного процесса, или **NULL.**

*procHandle*<br/>
Ручка к процессу, которую нужно ждать (т.е. процесс, который должен завершиться до **того,** как _cwait может вернуться).

*Действий*<br/>
NULL: Игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения на *procHandle*.

## <a name="return-value"></a>Возвращаемое значение

Когда указанный процесс успешно завершен, возвращает ручку указанного процесса и устанавливает *termstat* к коду результата, который возвращается указанным процессом. В противном случае, возвращает -1 и устанавливает **errno** следующим образом.

|Значение|Описание|
|-----------|-----------------|
|**ECHILD**|Никакого указанного процесса не существует, *procHandle* является недействительным, или вызов на [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) или [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API не удалось.|
|**EINVAL**|*действия* недействительны.|

Для получения дополнительной информации об этих и других кодах возврата [_sys_nerr _sys_errlist _doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)см.

## <a name="remarks"></a>Remarks

**Функция _cwait** ждет прекращения идентификатора процесса указанного процесса, предоставленного *procHandle.* Значение *procHandle,* которое передается **_cwait** должно быть значением, возвращенным вызовом в [функцию _spawn,](../../c-runtime-library/spawn-wspawn-functions.md) создавую указанный процесс. Если идентификатор процесса завершается до вызова **_cwait,** **_cwait** немедленно возвращается. **_cwait** может быть использован любым процессом, чтобы ждать любого другого известного процесса, для которого существует действительная ручка *(procHandle).*

*termstat* указывает на буфер, в котором будет храниться код возврата указанного процесса. Значение *termstat* указывает, был ли указанный процесс прекращен в обычном порядке, позвонив в API [Windows ExitProcess.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) **ExitProcess** вызывается внутренне, если указанный процесс вызывает **выход** или **_exit,** возвращается из **основного**или достигает конца **основного.** Для получения дополнительной информации о значении, которое прошло обратно через *termstat*, [см. GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Если **_cwait** вызывается с помощью значения **NULL** для *termstat,* код возврата указанного процесса не сохраняется.

Параметр *действия* игнорируется операционной системой Windows, поскольку отношения родителей и детей не реализуются в этих средах.

Если *procHandle* не является -1 или -2 (ручки к текущему процессу или потоку), ручка будет закрыта. Поэтому в этой ситуации не используйте возвращенный дескриптор.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

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
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
