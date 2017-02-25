---
title: "_get_pgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_pgmptr"
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
  - "get_pgmptr"
  - "_get_pgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_pgmptr - функция"
  - "_pgmptr - глобальная переменная"
  - "get_pgmptr - функция"
  - "pgmptr - глобальная переменная"
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _get_pgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущее значение глобальной переменной `_pgmptr`.  
  
## Синтаксис  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### Параметры  
 \[выходной\] `pValue`  
 Указатель на строку для заполнения текущим значением переменной `_pgmptr`.  
  
## Возвращаемое значение  
 Возвращает ноль, если успешно; код ошибки при неудаче.  Если параметр `pValue` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `EINVAL`.  
  
## Заметки  
 Глобальная переменная `_pgmptr`содержит полный путь к исполняемому файлу, связанному с процессом.  Для получения дополнительной информации см. [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_pgmptr`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_get\_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)