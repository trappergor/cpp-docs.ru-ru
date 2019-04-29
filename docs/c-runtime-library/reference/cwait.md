---
title: _cwait
ms.date: 11/04/2016
apiname:
- _cwait
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
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: f7a49497ac71ec15261e1215bd2bbed2e49f42ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288788"
---
# <a name="cwait"></a>_cwait

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

*termstat*<br/>
Указатель на буфер, где будет храниться код результата указанного процесса, или **NULL**.

*procHandle*<br/>
Дескриптор для ожидаемого процесса (то есть процесса, прежде чем **_cwait** может возвращать).

*Действие*<br/>
NULL: Игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения на *procHandle*.

## <a name="return-value"></a>Возвращаемое значение

После успешного завершения указанного процесса, возвращает дескриптор указанного процесса и задает *termstat* на код результата, который возвращается указанным процессом. В противном случае возвращается значение -1 и задает **errno** следующим образом.

|Значение|Описание|
|-----------|-----------------|
|**ECHILD**|Указанный процесс не существует, *procHandle* недопустим или вызов [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) или [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) вызова API.|
|**EINVAL**|*Действие* является недопустимым.|

Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Cwait** функция ожидает завершения ИД процесса указанного процесса, предоставляемый *procHandle*. Значение *procHandle* передаваемый **_cwait** должно быть значением, которое возвращается вызовом [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) функции, создавшей указанный процесс. Если ИД процесса завершается до **_cwait** вызове **_cwait** возвращается немедленно. **_cwait** может использоваться любым процессом для ожидания любого другого известного процесса, для которого является допустимым дескриптором (*procHandle*) существует.

*termstat* указывает на буфер, где будет храниться код возврата указанного процесса. Значение *termstat* указывает, является ли указанный процесс завершился обычным образом путем вызова Windows [ExitProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitprocess) API. **ExitProcess** вызывается внутренним образом, если указанный процесс вызывает **выйти из** или **_exit**, возвращает из **основной**, или достигает конца **основной** . Дополнительные сведения о значении, передаваемом обратно через *termstat*, см. в разделе [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Если **_cwait** вызывается с помощью **NULL** значение *termstat*, код возврата указанного процесса не сохраняется.

*Действие* параметр игнорируется операционной системой Windows, поскольку родительско дочерних отношений не реализуются в этих средах.

Если не *procHandle* -1 или -2 (дескрипторы для текущего процесса или потока), дескриптор будет закрыт. Поэтому в этой ситуации не используйте возвращенный дескриптор.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
