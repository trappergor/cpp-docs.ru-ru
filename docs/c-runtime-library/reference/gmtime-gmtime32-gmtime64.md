---
title: gmtime, _gmtime32, _gmtime64
description: Справочник по API для `gmtime` , `_gmtime32` и `_gmtime64` , который преобразует `time_t` значение в `tm` структуру.
ms.date: 10/27/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: bb8bee6b752f64d85dfb0f8c9e5ba7acf204a76f
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907549"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>`gmtime`, `_gmtime32`, `_gmtime64`

Преобразует `time_t` значение времени в `tm` структуру. Доступны более безопасные версии этих функций; см. раздел [ `gmtime_s` , `_gmtime32_s` , `_gmtime64_s` ](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*`sourceTime`*\
Указатель на хранимое время. Время представляется в виде секунд, истекших после полуночи (00:00:00) 1-го января 1970 года, время в формате UTC.

## <a name="return-value"></a>Возвращаемое значение

Указатель на структуру типа [`tm`](../../c-runtime-library/standard-types.md) . Поля возвращаемой структуры содержат вычисленное значение *`sourceTime`* аргумента в формате UTC, а не в местном времени. Каждое из полей структуры имеет тип `int`, как описано далее:

|Поле|Описание|
|-|-|
|`tm_sec`|Секунд после минуты (0-59).|
|`tm_min`|Минут после часа (0-59).|
|`tm_hour`|Часы с полуночи (0-23).|
|`tm_mday`|День месяца (1-31).|
|`tm_mon`|Месяц (0-11; Январь = 0).|
|`tm_year`|Год (текущий год минус 1900).|
|`tm_wday`|День недели (0-6; Воскресенье = 0).|
|`tm_yday`|День года (0-365; 1 января = 0).|
|`tm_isdst`|Значение всегда равно 0 для **gmtime** .|

И 32-разрядные, и 64-разрядные версии **`gmtime`** ,, [`mktime`](mktime-mktime32-mktime64.md) [`mkgmtime`](mkgmtime-mkgmtime32-mkgmtime64.md) и [`localtime`](localtime-localtime32-localtime64.md) используют одну общую `tm` структуру для каждого потока для преобразования. Каждый вызов одной из этих функций уничтожает результат любого предыдущего вызова. Если *`sourceTime`* представляет дату до полуночи, 1 января 1970 г **`gmtime`** . возвращается значение `NULL` . Ошибки не возвращаются.

**_gmtime64** , в котором используется `__time64_t` структура, позволяет выражать даты до 23:59:59, 31 декабря 3000, UTC. **`_gmtime32`** представляет только даты до 23:59:59 января 2038, в формате UTC. Полночь 1-ого января 1970 года — нижняя граница диапазона дат для обеих функций.

**`gmtime`** — Это встроенная функция, которая возвращает значение **`_gmtime64`** и `time_t` эквивалентно, `__time64_t` Если `_USE_32BIT_TIME_T` не определен. Если необходимо, чтобы компилятор воссчитался `time_t` как старый 32-разрядный `time_t` , можно определить `_USE_32BIT_TIME_T` , но это приводит к тому, что **`gmtime`** в нем будут присутствовать в строке, а также должны быть **`_gmtime32`** `time_t` определены как `__time32_t` . Мы не советуем делать этого, так как это не разрешено на 64-разрядных платформах. В любом случае приложение может завершиться ошибкой после 18 января 2038 г.

Эти функции проверяют свои параметры. Если *`sourceTime`* является пустым указателем или имеет *`sourceTime`* отрицательное значение, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр `errno` в значение `EINVAL`.

## <a name="remarks"></a>Remarks

**`_gmtime32`** Функция разделяет *`sourceTime`* значение и сохраняет его в статической выделенной структуре типа `tm` , определенной в `TIME.H` . Значение *`sourceTime`* обычно получается из вызова [`time`](time-time32-time64.md) функции.

> [!NOTE]
> В большинстве случаев целевая среда пытается определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**`gmtime`** , **`_gmtime32`** , **`_gmtime64`**|`<time.h>`| `<ctime>` или `<time.h>`|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main(void)
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)\
[`asctime`, `_wasctime`](asctime-wasctime.md)\
[`ctime`, `_ctime32`, `_ctime64`, `_wctime`, `_wctime32`, `_wctime64`](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)\
[`_ftime`, `_ftime32`, `_ftime64`](ftime-ftime32-ftime64.md)\
[`gmtime_s`, `_gmtime32_s`, `_gmtime64_s`](gmtime-s-gmtime32-s-gmtime64-s.md)\
[`localtime`, `_localtime32`, `_localtime64`](localtime-localtime32-localtime64.md)\
[`_mkgmtime`, `_mkgmtime32`, `_mkgmtime64`](mkgmtime-mkgmtime32-mkgmtime64.md)\
[`mktime`, `_mktime32`, `_mktime64`](mktime-mktime32-mktime64.md)\
[`time`, `_time32`, `_time64`](time-time32-time64.md)
