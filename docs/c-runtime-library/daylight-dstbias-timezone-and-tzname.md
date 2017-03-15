---
title: "_daylight, _dstbias, _timezone и _tzname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "часовые пояса"
  - "коррекция времени"
  - "timezone - переменные"
  - "_tzname - функция"
  - "_daylight - функция"
  - "_timezone - функция"
  - "daylight - функция"
  - "коррекция местного времени"
  - "timezone - функция"
  - "tzname - функция"
  - "time-zone - переменные"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _daylight, _dstbias, _timezone и _tzname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_daylight`, `_dstbias`, `_timezone` и `_tzname` используются в некоторых процедурах времени и даты для коррекции локального времени.  Эти глобальные переменные не рекомендуются в силу наличия более безопасных функциональных версий, которые должны использоваться вместо глобальных переменных.  
  
|Глобальная переменная|Функциональный эквивалент|  
|---------------------------|-------------------------------|  
|`_daylight`|[\_get\_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[\_get\_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[\_get\_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Они объявлены в Time.h следующим образом.  
  
## Синтаксис  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## Заметки  
 При вызове `_ftime`, `localtime` или `_tzset`, значения `_daylight`, `_dstbias`, `_timezone` и `_tzname` определяется на основе значения переменной среды `TZ`.  Если явно не устанавливается значение `TZ`, `_tzname[0]` и `_tzname[1]` содержат параметры по умолчанию «PST» и «PDT» соответственно.  Функции обработки времени \([\_tzset](../Topic/_tzset.md), [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)\) могут задавать значения `_daylight`, `_dstbias` и `_timezone` путем запроса у операционной системы значения по умолчанию для каждой переменной.  Значения глобальной переменной часового пояса приведены в следующей таблице.  
  
|Переменная|Значение|  
|----------------|--------------|  
|`_daylight`|Не ноль, если летнее время указано в `TZ` или известно от операционной системы; в противном случае — значение 0.  Значение по умолчанию — 1.|  
|`_dstbias`|смещение на период летнего времени.|  
|`_timezone`|Различие в секундах между координируемыми всемирным временем и местным временем.  Значение по умолчанию — 28,800.|  
|`_tzname[0]`|Имя часового пояса, производное от переменной среды `TZ`.  Значение по умолчанию — "PST".|  
|`_tzname[1]`|Имя пояса летнего времени, производное от переменной среды `TZ`.  Значение по умолчанию — «PDT» \(тихоокеанское дневное стандартное время\).|  
  
## См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)