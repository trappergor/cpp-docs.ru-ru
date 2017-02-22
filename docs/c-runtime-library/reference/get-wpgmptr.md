---
title: "_get_wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_wpgmptr"
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
  - "get_wpgmptr"
  - "_get_wpgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_wpgmptr - функция"
  - "_wpgmptr - глобальная переменная"
  - "get_wpgmptr - функция"
  - "wpgmptr - глобальная переменная"
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _get_wpgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущее значение глобальной переменной `_wpgmptr`.  
  
## Синтаксис  
  
```  
errno_t _get_wpgmptr(     wchar_t **pValue  );  
```  
  
#### Параметры  
 \[выходной\] `pValue`  
 Указатель на строку, которая будет заполнена текущим значением переменной `_wpgmptr`.  
  
## Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае ошибки.  Если параметр `pValue` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
## Заметки  
 Глобальная переменная `_wpgmptr` содержит полный путь к исполняемому файлу, связанному с процессом, в виде строки двухбайтовых знаков.  Для получения дополнительной информации см. [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_wpgmptr`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_get\_pgmptr](../../c-runtime-library/reference/get-pgmptr.md)