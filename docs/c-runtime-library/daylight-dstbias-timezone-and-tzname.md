---
title: _daylight, _dstbias, _timezone и _tzname
ms.date: 11/04/2016
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
helpviewer_keywords:
- time zones
- time adjustments
- timezone variables
- _tzname function
- _daylight function
- _timezone function
- daylight function
- local time adjustments
- timezone function
- tzname function
- time-zone variables
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
ms.openlocfilehash: 3f9f78d0798140399960cade7ead408f958450ba
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748259"
---
# <a name="daylight-dstbias-timezone-and-tzname"></a>_daylight, _dstbias, _timezone и _tzname

`_daylight`, `_dstbias`, `_timezone` и `_tzname` используются в некоторых процедурах даты и времени для корректировки локального времени. Использование этой глобальной переменной не рекомендуется в силу наличия более безопасных функциональных версий, которые следует использовать вместо глобальных переменных.

|Глобальная переменная|Функциональный эквивалент|
|---------------------|---------------------------|
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|

Они объявляются в файле Time.h описанным ниже образом.

## <a name="syntax"></a>Синтаксис

```
extern int _daylight;
extern int _dstbias;
extern long _timezone;
extern char *_tzname[2];
```

## <a name="remarks"></a>Примечания

При вызове `_ftime`, `localtime` или `_tzset` значения `_daylight`, `_dstbias`, `_timezone` и `_tzname` определяются, исходя из значения переменной среды `TZ`. Если значение `TZ` прямо не указано, `_tzname[0]` и `_tzname[1]` содержат соответственно параметры по умолчанию PST и PDT.  Функции обработки времени ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) пытаются задать значения `_daylight`, `_dstbias` и `_timezone`, запрашивая операционную систему о значении по умолчанию для каждой переменной. Значения глобальных переменных часовых поясов перечислены в следующей таблице.

|Переменная|Значение|
|--------------|-----------|
|`_daylight`|Ненулевое, если переход на летнее время (DST) указан в `TZ` или определяется операционной системой; в противном случае — 0. Значение по умолчанию — 1.|
|`_dstbias`|Смещение при переходе на летнее время.|
|`_timezone`|Разница в секундах между временем в формате UTC и местным временем. Значение по умолчанию — 28 000.|
|`_tzname[0]`|Имя часового пояса, исходя из переменной среды `TZ`. Значение по умолчанию — PST.|
|`_tzname[1]`|Имя пояса DST, исходя из переменной среды `TZ`. Значение по умолчанию — PDT (тихоокеанское летнее время).|

## <a name="see-also"></a>См. также

[Глобальные переменные](../c-runtime-library/global-variables.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
