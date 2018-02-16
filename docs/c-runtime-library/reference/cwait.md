---
title: "_cwait | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 483b98f005a77ff41d2a319a9d07ccc88ad32721
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cwait"></a>_cwait
Ожидает завершения другого процесса.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `termstat`  
 Указатель на буфер, в который будет сохранен код результата указанного процесса, или значение NULL.  
  
 `procHandle`  
 Дескриптор для ожидаемого процесса (то есть процесса, который должен завершиться, прежде чем функция `_cwait` сможет вернуть значение).  
  
 `action`  
 NULL: игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения `procHandle`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если указанный процесс успешно выполнен, возвращает дескриптор указанного процесса и задает для параметра `termstat` код результата, возвращенный указанным процессом. В противном случае возвращается значение -1 и задает `errno` следующим образом.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`ECHILD`|Указанный процесс не существует, `procHandle` недопустим или вызов API [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) или [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) завершился с ошибкой.|  
|`EINVAL`|`action` недопустим.|  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_cwait` ожидает завершения ИД процесса указанного процесса, предоставленного параметром `procHandle`. Значение `procHandle`, передаваемое в `_cwait`, должно быть значением, которое возвращается вызовом функции [_spawn](../../c-runtime-library/spawn-wspawn-functions.md), создавшей указанный процесс. Если ИД процесса завершается до вызова `_cwait`, `_cwait` возвращает значение немедленно. `_cwait` может использоваться любым процессом для ожидания другого известного процесса, для которого существует действительный дескриптор (`procHandle`).  
  
 `termstat` указывает на буфер, в который будет сохранен код результата указанного процесса. Значение `termstat` указывает, завершился ли указанный процесс нормальным образом путем вызова API Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx). `ExitProcess` вызывается внутренне, если указанный процесс вызывает `exit` или `_exit`, возвращает значение из `main` или достигает конца `main`. Дополнительные сведения о значении, передаваемом обратно через `termstat`, см. в разделе [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx). Если функция `_cwait` вызывается с помощью значения NULL для параметра `termstat`, код возврата указанного процесса не сохраняется.  
  
 Параметр `action` игнорируется операционной системой Windows, так как отношения "родитель-потомок" не реализованы в этих средах.  
  
 Если значение `procHandle` не равно -1 или -2 (дескрипторы для текущего потока или процесса), дескриптор будет закрыт. Поэтому в этой ситуации не используйте возвращенный дескриптор.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<process.h>|\<errno.h>|  
  
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
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)