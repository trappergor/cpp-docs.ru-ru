---
title: mktime, _mktime32, _mktime64
ms.date: 11/04/2016
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
ms.openlocfilehash: 8e9524249d6c90323bdcfc0b92ecf2dad281c79b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499912"
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64

Преобразуют локальное время в календарное значение.

## <a name="syntax"></a>Синтаксис

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>Параметры

*timeptr*<br/>
Указатель на структуру времени; см. [asctime](asctime-wasctime.md).

## <a name="return-value"></a>Возвращаемое значение

**_mktime32** возвращает указанное Календарное время, закодированное как значение типа [time_t](../../c-runtime-library/standard-types.md). Если *timeptr* ссылается на время до полуночи 1 января 1970 г., или если невозможно представить Календарное время, **_mktime32** возвращает -1, приведенное к типу **time_t**. При использовании **_mktime32** и если *timeptr* ссылается на время после 23:59:59 18 января 2038 года по Гринвичу (UTC), возвращается значение -1, приведенное к типу **time_t**.

**_mktime64** возвращает -1, приведенное к типу **__time64_t** Если *timeptr* ссылается на дату после 23:59:59 31 декабря 3000 года в формате UTC.

## <a name="remarks"></a>Примечания

**Mktime**, **_mktime32** и **_mktime64** функции преобразуют предоставленную структуру (возможно, неполную), на которые указывают *timeptr*в полностью определенную структуру с нормализованными значениями, а затем преобразует ее в **time_t** значение календарного времени. Преобразованное время имеет ту же кодировку, что и значения, возвращаемые функцией [time](time-time32-time64.md). Исходные значения **tm_wday** и **tm_yday** компоненты *timeptr* пропускаются, а исходные значения других компонентов не ограничено для их нормальными диапазонами.

**mktime** — это встроенная функция, которая эквивалентна **_mktime64**, если не **_USE_32BIT_TIME_T** определен, в противном случае она эквивалентна **_mktime32** .

После корректировки в формат UTC **_mktime32** обрабатывает даты с полуночи 1 января 1970 года до 23:59:59 18 января 2038 года в формате UTC. **_mktime64** обрабатывает даты с полуночи 1 января 1970 года до 23:59:59 31 декабря 3000 года. Этот аргумент может вызывать эти функции могут возвращать значение -1 (приведенное к **time_t**, **__time32_t** или **__time64_t**) несмотря на то, что дата находится в пределах диапазона. Например, если вы находитесь в Каире (Египет), часовой пояс которого на два часа раньше UTC, два часа сначала будут вычтены из даты, указанной в *timeptr*; это может привести к тому, что дата выйдет за пределы диапазона.

Эти функции можно использовать для проверки и заполнения структуры времени (tm). Если в случае успешного выполнения, эти функции устанавливают значения **tm_wday** и **tm_yday** в соответствии с потребностями и задают другие компоненты для представления указанного календарного времени, но все значения принудительно преобразуются в нормальное состояние диапазоны. Конечное значение **tm_mday** не задано до **tm_mon** и **tm_year** определяются. При указании **tm** структуры времени, задайте **tm_isdst** поле:

- нуль (0), чтобы указать, что действует стандартное время;

- значение больше нуля, чтобы указать, что действует переход на зимнее время;

- значение меньше нуля, чтобы указать, что код библиотеки времени выполнения языка C должен вычислить, действует ли стандартное время или переход на зимнее время.

Библиотека времени выполнения языка C определит режим перехода на зимнее время на основе значения переменной среды [TZ](tzset.md). Если **TZ** не задано, вызов Win32 API [GetTimeZoneInformation](/windows/desktop/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) используется для получения летнее время сведения из операционной системы. В случае сбоя библиотека предполагает, что для реализации вычисления перехода на зимнее время используются правила для США. **tm_isdst** — это обязательное поле. Если оно не задано, его значение является неопределенным, а возвращаемые значения этих функций — непредсказуемыми. Если *timeptr* указывает **tm** структуру, возвращенную предыдущим вызовом [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md), или [localtime](localtime-localtime32-localtime64.md) (или вариаций этих функций), **tm_isdst** поле содержит правильное значение.

Обратите внимание, что **gmtime** и **localtime** (и **_gmtime32**, **_gmtime64**, **_localtime32**, и **_localtime64**) используют один буфер на поток для преобразования. Если вы предоставляете этот буфер **mktime**, **_mktime32** или **_mktime64**, предыдущее содержимое удаляется.

Эти функции проверяют свои параметры. Если параметр *timeptr* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают значение -1 и задайте **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
