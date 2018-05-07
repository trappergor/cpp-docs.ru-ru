---
title: mktime, _mktime32, _mktime64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d02ae8e38a0d3e3b56b5ae69ddd937ef99d76b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

**_mktime32** возвращает кодируются как значение типа указанного календарного времени [time_t](../../c-runtime-library/standard-types.md). Если *timeptr* ссылается на время до полуночи 1 января 1970 года, или если невозможно представить Календарное время, **_mktime32** возвращает -1, приведенное к типу **time_t**. При использовании **_mktime32** и, если *timeptr* ссылается на время после 23:59:59 18 января 2038 года, универсальное глобальное (UTC), возвращается значение -1, приведенное к типу **time_t**.

**_mktime64** возвращает -1, приведенное к типу **__time64_t** Если *timeptr* ссылается на дату после 23:59:59, 31 декабря 3000 года, время UTC.

## <a name="remarks"></a>Примечания

**Mktime**, **_mktime32** и **_mktime64** функции преобразуют предоставленную структуру (возможно, неполную), на который указывает *timeptr*в полностью определенную структуру с нормализованными значениями, а затем преобразуется в **time_t** календарного времени. Преобразованное время имеет ту же кодировку, что и значения, возвращаемые функцией [time](time-time32-time64.md). Исходные значения **tm_wday** и **tm_yday** компоненты *timeptr* структуры учитываются, а не ограничены исходные значения других компонентов в их нормальных диапазонах.

**mktime** — это встроенная функция, эквивалентная **_mktime64**, пока не **_USE_32BIT_TIME_T** определен, в этом случае он эквивалентен **_mktime32** .

После корректировки в соответствии с форматом UTC **_mktime32** обрабатывает даты с полуночи 1 января 1970 года до 23:59:59 18 января 2038 года, время UTC. **_mktime64** обрабатывает даты с полуночи 1 января 1970 г. до 23:59:59 31 декабря 3000 года. Этот аргумент может вызывать эти функции возвращают значение -1 (приведение к **time_t**, **__time32_t** или **__time64_t**) несмотря на то, что указанная дата находится в пределах диапазона. Например, если вы находитесь в Каире (Египет), часовой пояс которого на два часа раньше UTC, два часа сначала будут вычтены из даты, указанной в *timeptr*; это может привести к тому, что дата выйдет за пределы диапазона.

Эти функции можно использовать для проверки и заполнения структуры времени (tm). При успешном выполнении, эти функции устанавливают значения **tm_wday** и **tm_yday** и настраивают другие компоненты для отображения указанного календарного времени, однако значения принудительно задаются с обычным диапазоны. Конечное значение **tm_mday** не задано до **tm_mon** и **tm_year** определяются. При указании **tm** времени структуры, задайте **tm_isdst** поля:

- нуль (0), чтобы указать, что действует стандартное время;

- значение больше нуля, чтобы указать, что действует переход на зимнее время;

- значение меньше нуля, чтобы указать, что код библиотеки времени выполнения языка C должен вычислить, действует ли стандартное время или переход на зимнее время.

Библиотека времени выполнения языка C определит режим перехода на зимнее время на основе значения переменной среды [TZ](tzset.md). Если **TZ** не задано, вызов API-интерфейса Win32 [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) используется для получения зимнее время из операционной системы. В случае сбоя библиотека предполагает, что для реализации вычисления перехода на зимнее время используются правила для США. **tm_isdst** — это обязательное поле. Если оно не задано, его значение является неопределенным, а возвращаемые значения этих функций — непредсказуемыми. Если *timeptr* указывает **tm** структуры, возвращенный предыдущим вызовом [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md), или [localtime](localtime-localtime32-localtime64.md) (или вариаций этих функций) **tm_isdst** поле содержит правильное значение.

Обратите внимание, что **gmtime** и **localtime** (и **_gmtime32**, **_gmtime64**, **_localtime32**, и **_localtime64**) используют один буфер на поток для преобразования. Если предоставить этот буфер **mktime**, **_mktime32** или **_mktime64**, предыдущее содержимое удаляется.

Эти функции проверяют свои параметры. Если параметр *timeptr* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции возвращают значение -1 и задайте **errno** для **EINVAL**.

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
