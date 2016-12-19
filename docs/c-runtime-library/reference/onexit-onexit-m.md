---
title: "_onexit, _onexit_m | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_onexit"
  - "_onexit_m"
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
apitype: "DLLExport"
f1_keywords: 
  - "_onexit"
  - "onexit_m"
  - "onexit"
  - "_onexit_m"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция onexit"
  - "реестр, регистрация процедур выхода"
  - "Функция _onexit_m"
  - "Функция onexit_m"
  - "Функция _onexit"
  - "регистрация процедур выхода"
  - "регистрация вызываемого при выходе объекта"
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _onexit, _onexit_m
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Регистрирует процедуру, вызываемую во время выхода.  
  
## Синтаксис  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### Параметры  
 `function`  
 Указатель на функцию, которая должна быть вызвана на выходе.  
  
## Возвращаемое значение  
 `_onexit` возвращает указатель на функцию в случае успеха, или `NULL`, если нет места для хранения указателя на функцию.  
  
## Заметки  
 Функции `_onexit` передается адрес функции \(`function`\), которую нужно вызывать при завершении программы в обычном режиме.  Последовательные вызовы `_onexit` создают регистр функций, которые выполняются в порядке LIFO \(последним поступил — первым обслужен\).  Функции, переданные в `_onexit`, не могут принимать параметры.  
  
 В этом случае, когда `_onexit` вызывается из библиотеки DLL, процедуры, зарегистрированные с `_onexit`, выполняются на выгрузке DLL после того, как `DllMain` вызывается с DLL\_PROCESS\_DETACH.  
  
 `_onexit` является расширением Майкрософт.  Для переносимости ANSI используйте [atexit](../../c-runtime-library/reference/atexit.md).  Версия `_onexit_m` этой функции предназначена для использования смешанного режима.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_onexit`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## Output  
  
```  
This is executed first.  
This is executed next.  
```  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_\_dllonexit](../../c-runtime-library/dllonexit.md)