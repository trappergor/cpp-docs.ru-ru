---
title: "_CrtGetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetAllocHook"
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
  - "CrtGetAllocHook"
  - "_CrtGetAllocHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtGetAllocHook - функция"
  - "CrtGetAllocHook - функция"
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtGetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает текущую определенную клиентом функцию выделения памяти для привязывания к процессу выделения отладочной памяти времени выполнения языка C \(только для отладочной версии\).  
  
## Синтаксис  
  
```  
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );  
```  
  
## Возвращаемое значение  
 Возвращает определенную в настоящее время функцию\-обработчик выделения памяти.  
  
## Заметки  
 `_CrtGetAllocHook` извлекает текущую определенную клиентом функцию\-обработчик выделения памяти для процесса выделения памяти отладочной библиотеки времени выполнения языка C.  
  
 Дополнительные сведения о других способных на обработку функциях среды выполнения и написании собственных определяемых клиентом функциях\-ловушках см. в разделе [Написание функций отладочных ловушек](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtGetAllocHook`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetAllocHook](../Topic/_CrtSetAllocHook.md)