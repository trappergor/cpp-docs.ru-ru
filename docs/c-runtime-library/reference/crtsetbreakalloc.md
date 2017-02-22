---
title: "_CrtSetBreakAlloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetBreakAlloc"
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
  - "CrtSetBreakAlloc"
  - "_CrtSetBreakAlloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetBreakAlloc - функция"
  - "CrtSetBreakAlloc - функция"
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetBreakAlloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает точку останова для указанного порядкового номера выделения объекта \(только отладочная версия\).  
  
## Синтаксис  
  
```  
  
long _CrtSetBreakAlloc(     long lBreakAlloc  );  
```  
  
#### Параметры  
 *lBreakAlloc*  
 Порядковый номер выделения, для которого задается точка останова.  
  
## Возвращаемое значение  
 Возвращает предыдущий порядковый номер выделения объекта, для которого задана точка останова.  
  
## Заметки  
 `_CrtSetBreakAlloc` позволяет приложению выполнять обнаружение утечки памяти путем останова в определенной точке выделения памяти и обратной трассировки до источника запроса.  Функция использует последовательный порядковый номер выделения объекта, назначенный блоку памяти во время выделения в куче.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, вызовы `_CrtSetBreakAlloc` удаляются на этапе предварительной обработки.  
  
 Порядковый номер выделения объекта хранится в поле *lRequest* структуры **\_CrtMemBlockHeader**, определенной в Crtdbg.h.  Когда данные о блоке памяти включаются в отчет одной из функций дампа отладки, этот номер заключается в фигурные скобки \(например, {36}\).  
  
 Дополнительные сведения о том, как `_CrtSetBreakAlloc` можно использовать с другими функциями управления памятью, см. в разделе [Отслеживание запросов выделения кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Track_Heap_Allocation_Requests).  Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии основной кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)