---
title: "_findclose | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_findclose"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_findclose"
  - "findclose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_findclose - функция"
  - "findclose - функция"
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _findclose
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Закрывает указанный дескриптор поиска и освобождает связанные ресурсы.  
  
## Синтаксис  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### Параметры  
 `handle`  
 Искомый дескриптор, возвращенный предыдущим вызовом `_findfirst`.  
  
## Возвращаемое значение  
 В случае успеха `_findclose` возвращает 0.  В противном случае она возвращает значение \-1 и задает `errno` значение `ENOENT`, означающее, что больше не удается найти соответствующих файлов.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_findclose`|\<io.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Системные вызовы](../Topic/System%20Calls.md)   
 [Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)