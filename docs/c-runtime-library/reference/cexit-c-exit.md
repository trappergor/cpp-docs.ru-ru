---
title: "_cexit, _c_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_c_exit"
  - "_cexit"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_cexit"
  - "c_exit"
  - "_c_exit"
  - "cexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_c_exit - функция"
  - "_cexit - функция"
  - "c_exit - функция"
  - "cexit - функция"
  - "операции очистки во время процессов"
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _cexit, _c_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет операции очистки и возвращает без завершения процесса.  
  
## Синтаксис  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## Заметки  
 Функция `_cexit` вызывает, в порядке "последнее на входе — первое на выходе" \(LIFO\), функции, зарегистрированные `atexit` и `_onexit`.  Затем `_cexit` удаляет все буферы ввода\-вывода и закрывает все открытые потоки перед возвратом.  `_c_exit` совпадает с `_exit`, но возвращает в вызывающий процесс без обработки `atexit` или `_onexit` или очистки буферов потоков.  Поведение `exit`,`_exit`, `_cexit` и `_c_exit` показано в следующей таблице.  
  
|Функция|Поведение|  
|-------------|---------------|  
|`exit`|Выполняет полные процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|  
|`_exit`|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|  
|`_cexit`|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|  
|`_c_exit`|Выполняет быстрые процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|  
  
 При вызове функций `_cexit` или `_c_exit`, деструкторы для любых существующих во время вызова временных или автоматических объектов не вызываются.  Автоматический объект является объектом, который определен в функции, в которой он не объявляется статическим.  Временный объект — это объект, созданный компилятором.  Чтобы удалить автоматический объект перед вызовом `_cexit` или `_c_exit`, явным образом вызовите деструктор объекта следующим образом:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_cexit`|\<process.h\>|  
|`_c_exit`|\<process.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)