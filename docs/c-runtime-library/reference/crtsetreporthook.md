---
title: "_CrtSetReportHook | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook"
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
  - "_CrtSetReportHook"
  - "CrtSetReportHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtSetReportHook - функция"
  - "_CrtSetReportHook - функция"
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает определяемую клиентом функцию отчетов путём её прикрепления в процесс создания отчетов среды выполнения языка C \(только отладочная версия\).  
  
## Синтаксис  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### Параметры  
 `reportHook`  
 Новая определяемая клиентом функция отчетов, которую необходимо прикрепить в процесс создания отчетов среды выполнения языка C.  
  
## Возвращаемое значение  
 Возвращает предыдущую определяемую клиентом функцию отчетов.  
  
## Заметки  
 `_CrtSetReportHook` позволяет приложению использовать собственную сообщающую об ошибках функцию в процессе обработки ошибок отладочной библиотеки времени выполнения языка C.  В результате, всякий раз, когда вызывается [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) для создания отчета отладки, сначала вызывается функция отчетов приложения.  Эта функциональность позволяет приложению выполнять такие операции, как фильтрация отчетов отладки, чтобы отобрать выделения конкретного типа или отправить отчет в назначения, которые недоступны при использовании `_CrtDbgReport`.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtSetReportHook` удаляются во время предварительной обработки.  
  
 Более надежную версию `_CrtSetReportHook` см. в разделе [\_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 Функция `_CrtSetReportHook` устанавливает определяемую клиентом функцию отчетов, указанную в `reportHook` и возвращает предыдущую определенную клиентом функцию.  В следующем примере показано, как должна быть объявлена определяемая клиентом функция отчетов:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 где `reportType` \- тип отчета отладки \(`_CRT_WARN`, `_CRT_ERROR` или `_CRT_ASSERT`\), `message` \- полностью собранное пользовательское отладочное сообщение, которое будет содержаться в отчете, а `returnValue` \- значение, указанное определяемой клиентом функцией отчетов, которое должна быть возвращено `_CrtDbgReport`.  Полное описание доступных типов отчетов см. в разделе [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
 Если определяемая клиентом функция отчетов полностью обрабатывает сообщение отладки так, что дальнейшая выдача отчета не требуется, то функция должна возвращать `TRUE`.  Если функция возвращает `FALSE`, `_CrtDbgReport` вызывается для создания отчета отладки с использованием текущих параметров для типа, режима и файла отчета.  Кроме того, указав возвращаемое значение `_CrtDbgReport` в `returnValue`, приложение может контролировать, происходит ли прерывание при отладке.  Полное описание настройки и создания отчета об отладке см. в разделах `_CrtSetReportMode`, [\_CrtSetReportFile](../Topic/_CrtSetReportFile.md) и `_CrtDbgReport`.  
  
 Дополнительные сведения о других способных на обработку функциях среды выполнения и написании собственных определяемых клиентом функциях\-ловушках см. в разделе [Написание функций отладочных ловушек](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
> [!NOTE]
>  Если приложение компилировано с `/clr` и функциональность отчетов вызывается после того, как приложение покидает main, среда CLR вызывает исключение, если функции отчета вызывают какие\-либо функции CRT.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtSetReportHook`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)