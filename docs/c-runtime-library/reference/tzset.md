---
title: _tzset
ms.date: 11/04/2016
apiname:
- _tzset
apilocation:
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
apitype: DLLExport
f1_keywords:
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: 6312297e6daa9b4790674bd26d21812d5bee34c6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330259"
---
# <a name="tzset"></a>_tzset

Задает переменные среды, относящиеся ко времени.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
void _tzset( void );
```

## <a name="remarks"></a>Примечания

**_Tzset** функция использует текущее значение переменной среды **TZ** для присвоения значения трем глобальным переменным: **_daylight**, **_timezone** , и **_tzname**. Эти переменные используются [_ftime](ftime-ftime32-ftime64.md) и [localtime](localtime-localtime32-localtime64.md) для внесения коррекций из времени в формате (UTC) в местное время, а также по [время](time-time32-time64.md) Выбор функции вычисления в формате UTC на основе системного времени. Используйте следующий синтаксис для задания **TZ** переменной среды:

> **Задайте TZ =**_tzn_ \[ **+** &#124; **-**]*hh* \[ **:**_мм_\[**:**_ss_]] [*dzn*]

|Параметр|Описание|
|-|-|
| *tzn* | Трехбуквенное имя часового пояса, например, PST. Необходимо указать правильное смещение локального времени относительно времени в формате UTC. |
| *hh* | Различие в часах между временем в формате UTC и местным временем. Знак (+) для положительных значений необязателен. |
| *mm* | Минуты. Отделены от *hh* двоеточием (**:**). |
| *ss* | Секунды. Отделены от *мм* двоеточием (**:**). |
| *dzn* | Трехбуквенный часовой пояс с переходом на летнее время, например, PDT. Если летнее время не действует в местоположении, установите **TZ** без значения для *dzn*. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST). |

> [!NOTE]
> Не забывайте о вычислении знака разницы во времени. Поскольку разница во времени является смещением локального времени относительно времени в формате UTC (а не наоборот), ее знак может отличаться от интуитивно ожидаемого. Для часовых поясов до пояса времени в формате UTC разница во времени отрицательная; для часовых поясов после пояса времени в формате UTC разница положительная.

Например, чтобы задать **TZ** переменной среды в соответствии с текущем часовом поясе в Германии, введите следующее в командной строке:

> **Задайте TZ = GST 1GDT**

Эта команда использует GST для указания немецкого стандартного времени, учитывая, что время в формате UTC отстает на один час от времени в Германии (или, другими словами, что время в Германии на один час опережает время в формате UTC) и учитывая, что Германия использует переход на летнее время.

Если **TZ** значение не задано, **_tzset** пытается использовать данные часового пояса, определенные операционной системой. В операционной системе Windows эти данные определяются в приложении Дата/время в Панели управления. Если **_tzset** не удается получить эту информацию, она использует PST8PDT по умолчанию, что означает Тихоокеанский часовой пояс.

На основе **TZ** значение переменной среды, глобальным переменным назначаются следующие значения **_daylight**, **_timezone**, и **_tzname** при **_tzset** вызывается:

|Глобальная переменная|Описание|Значение по умолчанию|
|---------------------|-----------------|-------------------|
|**_daylight**|Ненулевое значение, указываемое в зону летнему **TZ** параметром; в противном случае — 0.|1|
|**_timezone**|Разница в секундах между местным временем и временем в формате UTC.|28800 (28800 секунд равны 8 часам)|
|**_tzname**[0]|Строковое значение имени часового пояса из **TZ** переменной среды; пусто, если **TZ** не было задано.|PST|
|**_tzname**[1]|Строковое значение часового пояса перехода на летнее время; пустой, если зона летнему **TZ** переменной среды.|PDT|

По умолчанию значений, приведенных в предыдущей таблице **_daylight** и **_tzname** массива соответствуют «PST8PDT». Если зона летнего времени **TZ** переменная среды, значение **_daylight** равно 0 и [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)и [localtime](localtime-localtime32-localtime64.md) возвращают значение 0 для флагов летнего времени.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tzset**|\<time.h>|

**_Tzset** функция зависит от Microsoft. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
