---
title: "_get_timezone | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_timezone"
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
  - "_get_timezone"
  - "get_timezone"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "часовые пояса"
  - "get_timezone - функция"
  - "_get_timezone - функция"
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _get_timezone
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает разницу в секундах между координируемым всемирным временем \(UTC\) и местным временем.  
  
## Синтаксис  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### Параметры  
 `seconds`  
 Разница в секундах между временем в формате UTC и местным временем.  
  
## Возвращаемое значение  
 Ноль при успехе или значение `errno` при возникновении ошибки.  
  
## Заметки  
 Функция `_get_timezone` извлекает разницу в секундах между временем в формате UTC и местным временем в виде целого числа.  Значение по умолчанию — 28,800 секунд для Стандартного тихоокеанского времени \(8 часов до времени в формате UTC\).  
  
 Если параметр `seconds` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_timezone`|\<time.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)