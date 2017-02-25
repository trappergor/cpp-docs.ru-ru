---
title: "Управление временем | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "даты, члены библиотек времени выполнения"
  - "время, управление временем"
  - "функции даты"
  - "функции времени"
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Управление временем
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти функции следует использовать для получения текущего времени, его преобразования, корректировки и хранения, как требуется. Текущее время представляет собой системное время.  
  
 Подпрограммы `_ftime` и `localtime` используют переменную среды `TZ`. Если значение `TZ` не задано, библиотека времени выполнения пытается использовать данные часового пояса, определенные операционной системой. Если такие сведения недоступны, эти функции используют значение по умолчанию PST8PDT. Дополнительные сведения о переменной `TZ` см. в разделе [\_tzset](../Topic/_tzset.md); также см. раздел [\_daylight, timezone и \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
### Подпрограммы времени  
  
|Функция|Применение|Эквивалент .NET Framework|  
|-------------|----------------|-------------------------------|  
|[asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Преобразуют время из типа `struct tm` в символьную строку. Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[часы](../c-runtime-library/reference/clock.md)|Возвращают реальное прошедшее время для процесса.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [\_ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Преобразуют время из типа `time_t`, `__time32_t` или `__time64_t` в символьную строку. Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)|  
|[difftime, \_difftime32, \_difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Вычисляют разницу между двумя значениями времени.|[System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md)|Хранят текущее системное время в переменной типа `struct _timeb` или `struct``__timeb64`. Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)|  
|[\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Задают время изменения открытого файла|[System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx), [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx), [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)|  
|[gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Преобразуют время из типа `time_t` в тип `struct tm` или из типа `__time64_t` в тип `struct tm`.Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx), [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Преобразуют время из типа `time_t` в тип `struct tm` или из типа `__time64_t` в тип `struct tm`с поправкой на местное время. Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)|  
|[\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Преобразовывают время в календарное значение по времени GMT.|[System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)|Преобразовывают время в календарное значение.|[System::DateTime::DateTime](Overload:System.DateTime.)|  
|[\_strdate, \_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [\_strdate\_s, \_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Возвращают текущую дату системы в виде строки. Версии этих функций с суффиксом `_s` являются более безопасными.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Форматируют строку даты и времени для международного использования.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[\_strtime, \_wstrtime](../Topic/_strtime,%20_wstrtime.md), [\_strtime\_s, \_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Возвращают текущее системное время в виде строки. Версии этих функций с суффиксом `_s` являются более безопасными.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)|Получают текущее системное время как значение типа `time_t`, `__time32_t` или `__time64_t`.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_tzset](../Topic/_tzset.md)|Задает значения внешних переменных времени но основе значения переменной времени среды `TZ`.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Задают время изменения указанного файла, используя либо текущее время, либо значение времени, хранящееся в структуре.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
  
> [!NOTE]
>  Во всех версиях Microsoft C\/C\+\+, кроме версии Microsoft C\/C\+\+ 7.0, и во всех версиях Visual C\+\+ эта функция времени возвращает текущее время как количество секунд, прошедших с полуночи 1\-го января 1970 года. В версии Microsoft C\/C\+\+ 7.0 функция `time` возвращает текущее время как количество секунд, истекших с полуночи 31\-го декабря 1899 года.  
  
> [!NOTE]
>  В версиях [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] и Microsoft C\/C\+\+ до Visual C\+\+ 2005 тип `time_t` определялся как `long int` \(32\-разрядный\), и поэтому не мог использоваться для дат после 3:14:07 19 января 2038 года, время в формате UTC. Теперь тип `time_t` по умолчанию эквивалентен типу `__time64_t`, но при задании директивы `_USE_32BIT_TIME_T` тип `time_t` изменяется на тип `__time32_t` и многие функции времени вызывают версии, которые принимают 32\-разрядный тип `time_t`. Дополнительные сведения см. в разделе [Стандартные типы](../c-runtime-library/standard-types.md) и в комментариях в документации для отдельных функций времени.  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)