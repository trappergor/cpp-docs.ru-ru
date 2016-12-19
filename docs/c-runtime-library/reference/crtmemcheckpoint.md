---
title: "_CrtMemCheckpoint | Microsoft Docs"
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
  - "_CrtMemCheckpoint"
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
  - "CrtMemCheckpoint"
  - "_CrtMemCheckpoint"
  - "crtdbg/_CrtMemCheckpoint"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtMemCheckpoint - функция"
  - "_CrtMemCheckpoint - функция"
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemCheckpoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущее состояние отладочной кучи и сохраняет его в предоставленной приложением структуре `_CrtMemState` \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### Параметры  
 `state`  
 Указатель на структуру `_CrtMemState` для заполнения контрольными точками памяти.  
  
## Заметки  
 Функция `_CrtMemCheckpoint` создает моментальный снимок текущего состояния отладочной кучи в любой данный момент. Этот моментальный снимок могут использовать другие функции управления состоянием кучи, такие как [\_CrtMemDifference](../Topic/_CrtMemDifference.md), для обнаружения утечек памяти и других проблем. Если [\_DEBUG](../Topic/_DEBUG.md) не определен, вызовы `_CrtMemState` удаляются на этапе предварительной обработки.  
  
 Приложение должно передать указатель в выделенный ранее экземпляр структуры `_CrtMemState`, определенный в файле Crtdbg.h в параметре `state`. Если при создании контрольной точки возникает ошибка `_CrtMemCheckpoint`, функция создает отчет об отладке `_CRT_WARN`, описывающий проблему.  
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в статье [Функции создания отчетов о состоянии кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Если параметр `state` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) задается значение `EINVAL`, и функция возвращает значение.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h\>, \<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** только отладочные версии UCRT.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtMemDifference](../Topic/_CrtMemDifference.md)