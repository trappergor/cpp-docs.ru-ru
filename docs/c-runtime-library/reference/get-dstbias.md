---
title: "_get_dstbias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_dstbias"
  - "__dstbias"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dstbias"
  - "_get_dstbias"
  - "get_dstbias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dstbias"
  - "_get_dstbias - функция"
  - "смещение на период летнего времени"
  - "get_dstbias - функция"
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_dstbias
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает смещение перехода на зимнее время в секундах.  
  
## Синтаксис  
  
```  
  
error_t _get_dstbias(      int* seconds );  
```  
  
#### Параметры  
 `seconds`  
 Смещение перехода на зимнее время в секундах.  
  
## Возвращаемое значение  
 Нуль в случае успешного выполнения или значение `errno` при возникновении ошибки.  
  
## Заметки  
 Функция `_get_dstbias` получает число секунд смещения перехода на зимнее время в виде целого числа.  Если действует переход на зимнее время, смещение по умолчанию составляет 3600 секунд. Это число соответствует одному часу \(хотя в некоторых регионах может применяться смещение на два часа\).  
  
 Если параметр `seconds` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
 Эту функцию рекомендуется использовать вместо макроса `_dstbias` или нерекомендуемой функции `__dstbias`.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_dstbias`|\<time.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)