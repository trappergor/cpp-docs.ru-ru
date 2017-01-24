---
title: "_CrtDumpMemoryLeaks | Microsoft Docs"
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
  - "_CrtDumpMemoryLeaks"
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
  - "CRTDBG_LEAK_CHECK_DF"
  - "CRTDBG_CHECK_CRT_DF"
  - "_CRTDBG_LEAK_CHECK_DF"
  - "CrtDumpMemoryLeaks"
  - "_CrtDumpMemoryLeaks"
  - "_CRTDBG_CHECK_CRT_DF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtDumpMemoryLeaks - функция"
  - "CRTDBG_LEAK_CHECK_DF - макрос"
  - "_CRTDBG_LEAK_CHECK_DF - макрос"
  - "_CrtDumpMemoryLeaks - функция"
  - "CRTDBG_CHECK_CRT_DF - макрос"
  - "_CRTDBG_CHECK_CRT_DF - макрос"
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDumpMemoryLeaks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Формирует дампы всех блоков памяти в отладочной куче при возникновении утечки памяти \(только отладочная версия\).  
  
## Синтаксис  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## Возвращаемое значение  
 `_CrtDumpMemoryLeaks` возвращает TRUE, если утечка памяти найдена.  В противном случае функция возвращает значение false.  
  
## Заметки  
 Функция `_CrtDumpMemoryLeaks` определяет, произошла ли утечка памяти с начала выполнения программы.  Когда утечка найдена, создается дамп данных заголовка отладки для всех объектов в куче в удобочитаемой для пользователя форме.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtDumpMemoryLeaks` удаляются во время предварительной обработки.  
  
 `_CrtDumpMemoryLeaks` часто вызывается в конце выполнения программы, чтобы убедиться, что вся память, выделенная приложением, была освобождена.  Функцию можно вызывать автоматически при завершении работы программы, установив битовое поле `_CRTDBG_LEAK_CHECK_DF` флага [\_crtDbgFlag](../Topic/_crtDbgFlag.md) с помощью функции [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  
  
 `_CrtDumpMemoryLeaks` вызывает [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) для получения текущего состояния кучи, а затем проверяет состояние блоков, которые не были освобождены.  Если встречается неосвобожденный блок, `_CrtDumpMemoryLeaks` вызывает функцию [\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md), чтобы сбросить информацию для всех объектов, выделенных в куче с начала выполнения программы.  
  
 По умолчанию внутренние блоки времени выполнения C \(`_CRT_BLOCK`\) не включаются в операции создания дампов памяти.  Функцию [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) можно использовать для установки бита `_CRTDBG_CHECK_CRT_DF` флага `_crtDbgFlag`, чтобы включить эти блоки в процесс обнаружения утечки.  
  
 Дополнительные сведения о функциях состояния кучи и о структуре `_CrtMemState` см. в разделе [Функции создания отчетов о состоянии кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Дополнительные сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Пример использования `_CrtDumpMemoryLeaks` см. в разделе [crt\_dbg1](http://msdn.microsoft.com/ru-ru/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)