---
title: "_free_dbg | Microsoft Docs"
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
  - "_free_dbg"
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
  - "_free_dbg"
  - "free_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "блоки памяти, повторное выделение"
  - "освобождение памяти"
  - "Функция _free_dbg"
  - "Функция free_dbg"
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает блок памяти в куче \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### Параметры  
 `userData`  
 Указатель на блок выделенной памяти, который необходимо освободить.  
  
 `blockType`  
 Тип выделенного блока памяти, который необходимо освободить: `_CLIENT_BLOCK`, `_NORMAL_BLOCK` или `_IGNORE_BLOCK`.  
  
## Заметки  
 Функция `_free_dbg` является отладочной версией функции [free](../../c-runtime-library/reference/free.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определена, каждый вызов `_free_dbg` сводится к вызову `free`.  И `free`, и `_free_dbg` освобождают блок памяти в куче, но `_free_dbg` предоставляет две функции отладки: возможность хранить освобожденные блоки в связанном списке кучи, чтобы эмулировать условия нехватки памяти и параметр типа блоков для освобождения определенных типов выделения.  
  
 `_free_dbg` выполняет проверку допустимости всех указанных файлов и расположений блоков перед выполнением операции освобождения.  От приложения не требуется предоставлять эти данные.  Когда освобождается блок памяти, менеджер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи.  Если битовое поле `_CRTDBG_DELAY_FREE_MEM_DF` флагов [\_crtDbgFlag](../Topic/_crtDbgFlag.md) задано, освобожденный блок заполняется значением 0xDD, ему присваивается тип блока `_FREE_BLOCK`, и он остается в связанном списке блоков памяти кучи.  
  
 При возникновении ошибки освобождения памяти, в `errno` заносятся данные операционной системы, которые объясняют причину ошибки.  Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Дополнительные сведения о типах блока выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в отладочной сборке приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_free_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Пример использования `_free_dbg` см. в разделе [crt\_dbg2](http://msdn.microsoft.com/ru-ru/21e1346a-6a17-4f57-b275-c76813089167).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)