---
title: "quick_exit1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "quick_exit"
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
  - "quick_exit"
  - "process/quick_exit"
  - "stdlib/quick_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция quick_exit"
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# quick_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Приводит к завершению работы программы в обычном режиме.  
  
## Синтаксис  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### Параметры  
 status  
 Код состояния, возвращаемый средой размещения.  
  
## Возвращаемое значение  
 Функция `quick_exit` не может вернуть управление вызывающему объекту.  
  
## Заметки  
 Функция `quick_exit` приводит к завершению работы программы в обычном режиме. Она не вызывает функции, зарегистрированные `atexit`, `_onexit` или обработчики сигналов, зарегистрированные функцией `signal`. Поведение не определено, если `quick_exit` вызывается несколько раз или если также вызывается функция `exit`.  
  
 Функция `quick_exit` вызывает в порядке поступления \(LIFO\) функции, зарегистрированные `at_quick_exit`, за исключением функций, которые уже были вызваны на тот момент, когда функция была зарегистрирована.  Поведение не определено, если вызов [longjmp](../../c-runtime-library/reference/longjmp.md) осуществляется во время вызова зарегистрированной функции, который привел бы к прерыванию вызова функции.  
  
 После вызова зарегистрированных функций `quick_exit` вызывает `_Exit` с использованием значения `status`, чтобы вернуть управление среде размещения.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`quick_exit`|\< process.h \> или \< stdlib.h \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)