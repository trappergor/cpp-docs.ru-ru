---
title: "_CrtGetReportHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetReportHook"
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
  - "CrtGetReportHook"
  - "_CrtGetReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtGetReportHook - функция"
  - "_CrtGetReportHook - функция"
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtGetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает определенную клиентом функция отчетов для её прикрепления к среде выполнения языка C для процесса создания отчетов \(только в отладочной версии\).  
  
## Синтаксис  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## Возвращаемое значение  
 Возвращает текущую определяемую клиентом функцию отчетов.  
  
## Заметки  
 `_CrtGetReportHook` позволяет приложению получить текущую функцию отчетов в процессе обработки ошибок отладочной библиотеки времени выполнения языка C.  
  
 Дополнительные сведения о других способных на обработку функциях среды выполнения и написании собственных определяемых клиентом функциях\-ловушках см. в разделе [Написание функций отладочных ловушек](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtGetReportHook`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Пример использования `_CrtSetReportHook` см. в [report](http://msdn.microsoft.com/ru-ru/f6e08c30-6bd9-459a-830a-56deec0d2051).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)