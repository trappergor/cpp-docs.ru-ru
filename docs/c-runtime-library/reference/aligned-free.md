---
title: "_aligned_free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_free"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_free"
  - "_aligned_free"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free - функция"
  - "aligned_free - функция"
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _aligned_free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает блок памяти, выделенной с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Синтаксис  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### Параметры  
 `memblock`  
 Указатель на блок памяти, который был возвращен в функцию `_aligned_malloc` или `_aligned_offset_malloc`.  
  
## Заметки  
 `_aligned_free` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные.  Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
 Эта функция не проверяет ее параметр, в отличие от других \_aligned функций CRT.  Если `memblock` является указателем на `NULL`, эта функция просто не выполняет никаких действий.  Она не изменяет `errno` и не вызывает обработчик недопустимого параметра.  При возникновении ошибки в функции из\-за неиспользования ранее функций \_aligned для выделения блока памяти или рассогласования памяти, произошедшего из\-за неожиданной проблемы, функция создает отчет отладки из [Макросы \_RPT, \_RPTF, \_RPTW, \_RPTFW](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_free`|\<malloc.h\>|  
  
## Пример  
 Дополнительные сведения см. в разделе [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)