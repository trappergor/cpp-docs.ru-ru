---
title: "_CrtCheckMemory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtCheckMemory"
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
  - "CrtCheckMemory"
  - "_CrtCheckMemory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtCheckMemory - функция"
  - "CrtCheckMemory - функция"
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtCheckMemory
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Подтверждает целостность блоков памяти, выделенных в отладочной куче \(только в отладочной версии\).  
  
## Синтаксис  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## Возвращаемое значение  
 В случае успеха `_CrtCheckMemory` возвращает TRUE; в противном случае функция возвращает FALSE.  
  
## Заметки  
 Функция `_CrtCheckMemory` проверяет память, выделенную диспетчером отладочной кучи, проверяя лежащую в основе базовую кучу и инспектируя каждый блок памяти.  Если в лежащей в основе базовой куче, данных заголовка отладки или буфере перезаписи обнаруживается ошибка или несоответствие памяти, то `_CrtCheckMemory` создает отчет об отладке со сведениями, описывающими условия ошибки.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtCheckMemory` удаляются во время предварительной обработки.  
  
 Поведение `_CrtCheckMemory` может управляться с помощью установки битовых полей флажка [\_crtDbgFlag](../Topic/_crtDbgFlag.md) с помощью функции [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  Включение битового поля **\_CRTDBG\_CHECK\_ALWAYS\_DF** приводит к тому, что `_CrtCheckMemory` вызывается каждый раз при запросе операции выделения памяти.  Хотя этот метод замедляет выполнение, он полезен для быстрого перехвата ошибок.  Выключение битового поля **\_CRTDBG\_ALLOC\_MEM\_DF** приводит к тому, что `_CrtCheckMemory` не проверяет кучу и немедленно возвращает значение **TRUE**.  
  
 Поскольку эта функция возвращает **TRUE** или **FALSE**, она может быть передана одному из макросов [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) для создания простого отладочного механизма обработки ошибок.  В следующем примере вызывается сбой проверочного утверждения в случае обнаружения повреждения в куче:  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 Дополнительные сведения о том, как можно использовать `_CrtCheckMemory` с другими функциями отладки, см. в разделе [Функции создания отчетов о состоянии кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Обзор управления памятью и отладочной кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtCheckMemory`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Пример использования `_CrtCheckMemory` см. в разделе [crt\_dbg1](http://msdn.microsoft.com/ru-ru/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::PerformanceCounter](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../Topic/_crtDbgFlag.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)