---
title: "_aligned_free_dbg | Microsoft Docs"
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
  - "_aligned_free_dbg"
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
  - "_aligned_free_dbg"
  - "aligned_free_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free_dbg - функция"
  - "aligned_free_dbg - функция"
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает блок памяти, который был выделен с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void _aligned_free_dbg(    void *memblock );  
```  
  
#### Параметры  
 `memblock`  
 Указатель на блок памяти, возвращенный в функцию `_aligned_malloc` или `_aligned_offset_malloc`.  
  
## Заметки  
 `_aligned_free_dbg`  — это отладочная версия функции [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, каждый вызов функции `_aligned_free_dbg` сокращается до вызова функции \_`aligned_free`.  И \_`aligned_free`, и `_aligned_free_dbg` освобождают блок памяти в основной куче, однако `_aligned_free_dbg`  включает функцию отладки: возможность хранить освободившиеся блоки в связанном списке кучи для моделирования условий недостатка памяти.  
  
 `_aligned_free_dbg` выполняет проверку действительности для всех указанных файлов и расположений блоков перед выполнением операции освобождения.  Приложение не ожидает предоставления этих сведений.  Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи.  Если задано битовое поле `_CRTDBG_DELAY_FREE_MEM_DF`  флага [\_crtDbgFlag](../Topic/_crtDbgFlag.md), освободившийся блок заполняется значением 0xDD, ему назначается тип блока `_FREE_BLOCK` и он хранится в связанном списке блоков памяти кучи.  
  
 В случае возникновения ошибки при освобождении памяти для `errno` задаются сведения о характере сбоя, полученные от операционной системы.  Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии основной кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Сведения о типах блоков выделения и о том, как они используются, см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_free_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)