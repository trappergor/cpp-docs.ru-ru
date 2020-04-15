---
title: _tzset
ms.date: 4/2/2020
api_name:
- _tzset
- _o__tzset
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: b2537a3bbfd2b5cec6bdf149c520aac7e3344b1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362186"
---
# <a name="_tzset"></a>_tzset

Задает переменные среды, относящиеся ко времени.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
void _tzset( void );
```

## <a name="remarks"></a>Remarks

Функция **_tzset** использует текущую настройку переменной среды **ТЗ** для присвоения значений трем глобальным переменным: **_daylight,** **_timezone**и **_tzname.** Эти переменные используются [функциями _ftime](ftime-ftime32-ftime64.md) и [локального времени](localtime-localtime32-localtime64.md) для внесения корректировок от скоординированного универсального времени (UTC) к локальному времени, а также по функции [времени](time-time32-time64.md) для вычисления UTC из системного времени. Используйте следующий синтаксис для установки переменной среды **ТЗ:**

> **набор ТЗЗ** **-**_цн_ \[ **+**&#124;*хх*\[**:**_мм_\[**:**_ss_*dzn*

|Параметр|Описание|
|-|-|
| *tzn* | Трехбуквенное имя часового пояса, например, PST. Необходимо указать правильное смещение локального времени относительно времени в формате UTC. |
| *Чч* | Различие в часах между временем в формате UTC и местным временем. Знак (+) для положительных значений необязателен. |
| *Мм* | Минуты. Отделен от *hh* толстой кишки (**:**). |
| *сс* | Секунды. Отделен от *мм* толстой кишки **(: ).** |
| *дзн* | Трехбуквенный часовой пояс с переходом на летнее время, например, PDT. Если летнее время никогда не действует в местности, установить **ТЗ** без значения для *dzn*. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST). |

> [!NOTE]
> Не забывайте о вычислении знака разницы во времени. Поскольку разница во времени является смещением локального времени относительно времени в формате UTC (а не наоборот), ее знак может отличаться от интуитивно ожидаемого. Для часовых поясов до пояса времени в формате UTC разница во времени отрицательная; для часовых поясов после пояса времени в формате UTC разница положительная.

Например, чтобы настроить переменную среды **ТЗ** в соответствии с текущим часовом поясом в Германии, введите следующее в командной строке:

> **набор ТЗГГГ-1ГДТ**

Эта команда использует GST для указания немецкого стандартного времени, учитывая, что время в формате UTC отстает на один час от времени в Германии (или, другими словами, что время в Германии на один час опережает время в формате UTC) и учитывая, что Германия использует переход на летнее время.

Если значение **ТЗ** не установлено, **_tzset** попытки использовать информацию часового пояса, указанную операционной системой. В операционной системе Windows эти данные определяются в приложении Дата/время в Панели управления. Если **_tzset** не можете получить эту информацию, он использует PST8PDT по умолчанию, что означает тихоокеанский часовой пояс.

На основе переменного значения среды **ТЗ,** следующие значения присваиваются глобальным переменным **_daylight,** **_timezone**и **_tzname,** когда **_tzset** называется:

|Глобальная переменная|Описание|Значение по умолчанию|
|---------------------|-----------------|-------------------|
|**_daylight**|Ненулевое значение, если в настройках **ТЗ** указан дневной часовой пояс; в противном случае, 0.|1|
|**_timezone**|Разница в секундах между местным временем и временем в формате UTC.|28800 (28800 секунд равны 8 часам)|
|**_tzname**|Строковое значение названия часового пояса от переменной окружающей среды **ТЗ;** пусто, если **ТЗ** не установлен.|PST|
|**_tzname**|Строка значение летнего времени пояса; пустой, если дневной часовой пояс опущен из экологической переменной **ТЗ.**|PDT|

Значения по умолчанию, отображаемые в предыдущей таблице **для _daylight** и **массива _tzname,** соответствуют "PST8PDT". Если зона DST опущена из переменной среды **в области** окружающей среды, значение **_daylight** 0, а [_ftime,](ftime-ftime32-ftime64.md) [gmtime](gmtime-gmtime32-gmtime64.md)и функции [локального времени](localtime-localtime32-localtime64.md) возвращают 0 для своих флагов DST.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tzset**|\<time.h>|

Функция **_tzset** специфична для корпорации Майкрософт. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tzset.cpp
// This program uses _tzset to set the global variables
// named _daylight, _timezone, and _tzname. Since TZ is
// not being explicitly set, it uses the system time.

#include <time.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    _tzset();
    int daylight;
    _get_daylight( &daylight );
    printf( "_daylight = %d\n", daylight );
    long timezone;
    _get_timezone( &timezone );
    printf( "_timezone = %ld\n", timezone );
    size_t s;
    char tzname[100];
    _get_tzname( &s, tzname, sizeof(tzname), 0 );
    printf( "_tzname[0] = %s\n", tzname );
    exit( 0 );
}
```

```Output
_daylight = 1
_timezone = 28800
_tzname[0] = Pacific Standard Time
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
