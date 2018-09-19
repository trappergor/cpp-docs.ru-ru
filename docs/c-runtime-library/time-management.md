---
title: Управление временем | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- dates, run-time library members
- time, time management
- date functions
- time functions
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f63bfe358e3f077bff780e2c5b4436fb841fd145
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083981"
---
# <a name="time-management"></a>Управление временем

Эти функции следует использовать для получения текущего времени, его преобразования, корректировки и хранения, как требуется. Текущее время представляет собой системное время.

Подпрограммы **_Ftime** и **localtime** используют переменную среды **TZ**. Если переменная **TZ** не задана, библиотека времени выполнения пытается использовать данные часового пояса, определенные операционной системой. Если такие сведения недоступны, эти функции используют значение по умолчанию PST8PDT. Дополнительные сведения о переменной **TZ** см. в разделе [_tzset](../c-runtime-library/reference/tzset.md); также см. раздел [_daylight, timezone и _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

### <a name="time-routines"></a>Подпрограммы времени

|Функция|Использовать|
|--------------|---------|
|[asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Преобразуют время из типа**struct tm** в символьную строку. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[часы](../c-runtime-library/reference/clock.md)|Возвращают реальное прошедшее время для процесса.|
|[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [_ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Преобразуют время из типа **time_t**, **__time32_t** или **__time64_t** в символьную строку. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[difftime, _difftime32, _difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Вычисляют разницу между двумя значениями времени.|[System::DateTime::Subtract](https://msdn.microsoft.com/library/system.datetime.subtract.aspx)|
|[_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Хранение текущего системного времени в переменной типа **struct _timeb** или **struct __timeb64**. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Задают время изменения открытого файла|
|[gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Преобразуют время из типа **time_t** в тип **struct tm** или из типа **__time64_t** в тип **struct tm**. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Преобразуют время из типа **time_t** в тип **struct tm** или из типа **__time64_t** в тип **struct tm** с поправкой на местное время. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[_mkgmtime, _mkgmtime32, _mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Преобразовывают время в календарное значение по времени GMT.|
|[mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|Преобразовывают время в календарное значение.|
|[_strdate, _wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [_strdate_s, _wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Возвращают текущую дату системы в виде строки. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Форматируют строку даты и времени для международного использования.|
|[_strtime, _wstrtime](../c-runtime-library/reference/strtime-wstrtime.md), [_strtime_s, _wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Возвращают текущее системное время в виде строки. Версии этих функций с суффиксом **_s** являются более безопасными.|
|[time, _time32, _time64](../c-runtime-library/reference/time-time32-time64.md)|Получают текущее системное время как тип **time_t**, **__time32_t** или **__time64_t**.|
|[_tzset](../c-runtime-library/reference/tzset.md)|Задают значения внешних переменных времени но основе значения переменной времени среды **TZ**.|
|[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Задают время изменения указанного файла, используя либо текущее время, либо значение времени, хранящееся в структуре.|

> [!NOTE]
> Во всех версиях Microsoft C/C++, кроме версии Microsoft C/C++ 7.0, и во всех версиях Visual C++ эта функция времени возвращает текущее время как количество секунд, прошедших с полуночи 1-го января 1970 года. В версии Microsoft C/C++ 7.0 функция **time** возвращает текущее время как количество секунд, истекших с полуночи 31-го декабря 1899 года.

> [!NOTE]
> В версиях Visual C++ и Microsoft C/C++ ранее Visual C++ 2005 тип **time_t** определялся как **long** **int** (32-разрядный). Поэтому его невозможно использовать для дат после 3:14:07 19 января 2038 года (в формате UTC). Теперь тип **time_t** по умолчанию эквивалентен типу **__time64_t**, но при задании директивы **_USE_32BIT_TIME_T** тип **time_t** изменяется на тип **__time32_t** и заставляет многие функции времени вызывать версии, принимающие 32-разрядный тип **time_t**. Дополнительные сведения см. в статье [Standard Types](../c-runtime-library/standard-types.md) (Стандартные типы) и в комментариях в документации для отдельных функций времени.

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
