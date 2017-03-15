---
title: "atexit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atexit"
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
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit - функция"
  - "обработка, на выходе"
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# atexit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обрабатывает указанную функцию на выходе.  
  
## Синтаксис  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### Параметры  
 `func`  
 Функция, которую необходимо вызвать.  
  
## Возвращаемое значение  
 `atexit` возвращает 0 в случае успеха или ненулевое значение, если возникает ошибка.  
  
## Заметки  
 Функции `atexit` передается адрес функции \(`func`\), которую нужно вызывать при завершении программы в обычном режиме.  Последовательные вызовы `atexit` создают регистр функций, которые выполняются в порядке последним поступил — первым обслужен \(LIFO\).  Функции, переданные в `atexit`, не могут принимать параметры.  `atexit` и `_onexit` используют кучу для хранения регистра функций.  Поэтому количество функций, которые можно зарегистрировать, ограничивается только памятью кучи.  
  
 Код в функции `atexit` не должен содержать какую\-либо зависимость от какой\-либо библиотеки DLL, которая может быть уже выгружена на момент вызова функции `atexit`.  
  
 Для создания ANSI\- совместимого приложения используйте ANSI\-стандартную функцию `atexit` \(а не аналогичную ей функцию `_onexit`\).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`atexit`|\<stdlib.h\>|  
  
## Пример  
 Эта программа отправляет четыре функции в стек функций, они должны выполниться при вызове `atexit`.  Когда программа завершает работу, эти программы выполняются в порядке последним поступил — первым обслужен.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
  **This is executed first.**  
**This is executed next.**   
## Эквивалент в .NET Framework  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)