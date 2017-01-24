---
title: "_cwait | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwait"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_cwait"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cwait - функция"
  - "cwait - функция"
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cwait
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ожидает завершения другого процесса.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _cwait(     int *termstat,    intptr_t procHandle,    int action  );  
```  
  
#### Параметры  
 `termstat`  
 Указатель на буфер, в который будет сохранен код результата указанного процесса, или значение NULL.  
  
 `procHandle`  
 Дескриптор для ожидаемого процесса \(то есть процесса, который должен завершиться, прежде чем функция `_cwait` сможет вернуть значение\).  
  
 `action`  
 NULL: игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения `procHandle`.  
  
## Возвращаемое значение  
 Если указанный процесс успешно выполнен, возвращает дескриптор указанного процесса и задает для параметра `termstat` код результата, возвращенный указанным процессом.  В противном случае возвращает \-1 и задает следующие значения `errno`.  
  
|Значение|Описание|  
|--------------|--------------|  
|`ECHILD`|Указанный процесс не существует, `procHandle` недопустим или сбой вызова API [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) или [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx).|  
|`EINVAL`|`action` недопустим.|  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_cwait` ожидает завершения ИД процесса указанного процесса, предоставленного параметром `procHandle`.  Значение `procHandle`, передаваемое в `_cwait`, должно быть значением, которое возвращается вызовом функции [\_spawn](../Topic/_spawn,%20_wspawn%20Functions.md), создавшей указанный процесс.  Если ИД процесса завершается до вызова `_cwait`, `_cwait` возвращает значение немедленно.  `_cwait` может использоваться любым процессом для ожидания другого известного процесса, для которого существует действительный дескриптор \(`procHandle`\).  
  
 `termstat` указывает на буфер, в который будет сохранен код результата указанного процесса.  Значение параметра `termstat` обозначает, нормально ли завершился указанный процесс, путем вызова API Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx).  `ExitProcess` вызывается внутренне, если указанный процесс вызывает `exit` или `_exit`, возвращает значение из `main` или достигает конца `main`.  Дополнительные сведения о значении, которое передается обратно через параметр `termstat`, см. в статье [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx).  Если функция `_cwait` вызывается с помощью значения NULL для параметра `termstat`, код возврата указанного процесса не сохраняется.  
  
 Параметр `action` игнорируется операционной системой Windows, так как отношения "родитель\-потомок" не реализованы в этих средах.  
  
 Если значение `procHandle` не равно \-1 или \-2 \(дескрипторы для текущего потока или процесса\), дескриптор будет закрыт.  Поэтому в этой ситуации не используйте возвращенный дескриптор.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_cwait`|\<process.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
//  
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
   if( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for( c = 0; c < 4; c++ ){  
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
  
  **Привет, папа.  It's Ann.  Come here, Ann.  Thank you, Ann.  Привет, папа.  It's Beth.  Привет, папа.  It's Carl.  Привет, папа.  It's Dave.**    
## Эквивалент в .NET Framework  
 [System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)