---
title: mktime, _mktime32, _mktime64
ms.date: 11/04/2016
api_name:
- _mktime32
- mktime
- _mktime64
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: a282e9f27a0e8f2a91219facda96a5929d3982ea
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951522"
---
# <a name="mktime-_mktime32-_mktime64"></a>mktime, _mktime32, _mktime64

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

**_mktime32** возвращает указанное Календарное время, закодированное как значение типа [time_t](../../c-runtime-library/standard-types.md). Если *timeptr* ссылается на дату до полуночи 1 января 1970, или если не удается представить Календарное время, **_mktime32** возвращает-1 приведение к типу **time_t**. При использовании **_mktime32** и если *timeptr* ссылается на дату после 23:59:59 18 января 2038 г., время в формате UTC, оно возвращает-1 приведение к типу **time_t**.

**_mktime64** возвратит-1 Cast к типу **__time64_t** , если *timeptr* ссылается на дату после 23:59:59 31 декабря 3000, UTC.

## <a name="remarks"></a>Примечания

Функции **функциях mktime**, **_mktime32** и **_mktime64** преобразуют предоставленную структуру времени (возможно, неполную), на которую указывает *timeptr* , в полностью определенную структуру с нормализованными значениями, а затем преобразует их в **time_t** значение календарного времени. Преобразованное время имеет ту же кодировку, что и значения, возвращаемые функцией [time](time-time32-time64.md). Исходные значения компонентов **tm_wday** и **tm_yday** структуры *timeptr* игнорируются, а исходные значения других компонентов не ограничиваются их нормальными диапазонами.

**функциях mktime** — это встроенная функция, эквивалентная **_mktime64**, если не определен **_USE_32BIT_TIME_T** , в этом случае она эквивалентна **_mktime32**.

После корректировки в формате UTC **_mktime32** обрабатывает даты от полуночи 1 января 1970 г. до 23:59:59 18 января 2038 г. в формате UTC. **_mktime64** обрабатывает даты с полуночи 1 января 1970 до 23:59:59, 31 декабря 3000 г. Эта корректировка может привести к тому, что эти функции возвращают значение-1 (приведение к **time_t**, **__time32_t** или **__time64_t**), даже если указанная дата находится в пределах диапазона. Например, если вы находитесь в Каире (Египет), часовой пояс которого на два часа раньше UTC, два часа сначала будут вычтены из даты, указанной в *timeptr*; это может привести к тому, что дата выйдет за пределы диапазона.

Эти функции можно использовать для проверки и заполнения структуры времени (tm). В случае успеха эти функции задают значения **tm_wday** и **tm_yday** соответствующим образом и устанавливают другие компоненты для представления указанного календарного времени, но со значениями, которые принудительно задаются в нормальных диапазонах. Конечное значение **tm_mday** не устанавливается до тех пор, пока не будут определены **tm_mon** и **tm_year** . При указании времени структуры **TM** задайте для поля **tm_isdst** значение:

- нуль (0), чтобы указать, что действует стандартное время;

- значение больше нуля, чтобы указать, что действует переход на зимнее время;

- значение меньше нуля, чтобы указать, что код библиотеки времени выполнения языка C должен вычислить, действует ли стандартное время или переход на зимнее время.

Библиотека времени выполнения языка C определит режим перехода на зимнее время на основе значения переменной среды [TZ](tzset.md). Если **не задано** , то вызов Win32 API [жеттимезонеинформатион](/windows/win32/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) используется для получения сведений о летнем времени из операционной системы. В случае сбоя библиотека предполагает, что для реализации вычисления перехода на зимнее время используются правила для США. **tm_isdst** является обязательным полем. Если оно не задано, его значение является неопределенным, а возвращаемые значения этих функций — непредсказуемыми. Если *timeptr* указывает на структуру **TM** , возвращенную предыдущим вызовом [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md)или [localtime](localtime-localtime32-localtime64.md) (или вариантов этих функций), поле **tm_isdst** содержит правильное значение.

Обратите внимание, что **gmtime** и **localtime** (и **_gmtime32**, **_gmtime64**, **_localtime32**и **_localtime64**) используют один буфер для каждого потока для преобразования. При указании этого буфера для **функциях mktime**, **_mktime32** или **_mktime64**предыдущее содержимое уничтожается.

Эти функции проверяют свои параметры. Если параметр *timeptr* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают значение-1 и **задают значение** **еинвал**.

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
