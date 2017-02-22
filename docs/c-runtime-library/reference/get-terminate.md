---
title: "_get_terminate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_terminate"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_terminate"
  - "_get_terminate"
  - "__get_terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__get_terminate - функция"
  - "_get_terminate - функция"
  - "get_terminate - функция"
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_terminate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает процедуру завершения, которая будет вызвана `terminate`.  
  
## Синтаксис  
  
```  
terminate_function _get_terminate( void );  
```  
  
## Возвращаемое значение  
 Возвращает указатель на функцию, зарегистрированную [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md).  Если функция не задана, то возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_terminate`|\<eh.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)