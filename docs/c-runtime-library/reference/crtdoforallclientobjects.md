---
title: "_CrtDoForAllClientObjects | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDoForAllClientObjects"
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
  - "_CrtDoForAllClientObjects"
  - "CrtDoForAllClientObjects"
  - "crtdbg/_CrdDoForAllClientObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtDoForAllClientObjects - функция"
  - "CrtDoForAllClientObjects - функция"
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtDoForAllClientObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает функцию, предоставляемую приложением, для всех типов `_CLIENT_BLOCK` в куче \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### Параметры  
 `pfn`  
 Указатель на функцию обратного вызова функции, предоставляемой приложением. Первый параметр для этой функции указывает на данные. Второй параметр является указателем контекста, передаваемым в вызов функции `_CrtDoForAllClientObjects`.  
  
 `context`  
 Указатель на контекст, предоставляемый приложением, для передачи в функцию, предоставляемую приложением.  
  
## Заметки  
 Функция `_CrtDoForAllClientObjects` выполняет поиск блоков памяти с типом `_CLIENT_BLOCK` в связанном списке кучи и вызывает функцию, предоставляемую приложением, если удается найти блок этого типа. Найденный блок и параметр `context` передаются как аргументы в функцию, предоставляемую приложением. Во время отладки приложение может отследить определенную группу выделений, явно вызывая функции отладочной кучи для выделения памяти и указывая, что блокам должен назначаться тип `_CLIENT_BLOCK`. Эти блоки затем могут отслеживаться по отдельности и включаться в разные отчеты об обнаружении утечки и состоянии памяти.  
  
 Если битовое поле `_CRTDBG_ALLOC_MEM_DF` флага [\_crtDbgFlag](../Topic/_crtDbgFlag.md) не включено, сразу возвращается `_CrtDoForAllClientObjects`. Если значение [\_DEBUG](../Topic/_DEBUG.md) не задано, вызовы `_CrtDoForAllClientObjects` удаляются во время предобработки.  
  
 Дополнительные сведения о типе `_CLIENT_BLOCK` и о том, как его могут использовать другие функции отладки, см. в статье [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Если параметр `pfn` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) задается значение `EINVAL`, и функция возвращает значение.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h\>, \<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** отладочные версии только универсальных библиотек времени выполнения C.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Функции создания отчетов о состоянии кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)   
 [\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)