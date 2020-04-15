---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
ms.date: 4/2/2020
api_name:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
- _o__wctime32
- _o__wctime64
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
ms.openlocfilehash: 6056ad8bac6561c0ce2902928364996b2be9ae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348247"
---
# <a name="ctime-_ctime32-_ctime64-_wctime-_wctime32-_wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Доступны более безопасные версии этих функций; см. раздел [ctime_s _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *ctime( const time_t *sourceTime );
char *_ctime32( const __time32_t *sourceTime );
char *_ctime64( const __time64_t *sourceTime );
wchar_t *_wctime( const time_t *sourceTime );
wchar_t *_wctime32( const __time32_t *sourceTime );
wchar_t *_wctime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*источникВремя*<br/>
Указатель на сохраненное время для преобразования.

## <a name="return-value"></a>Возвращаемое значение

Указатель на результирующую строку символов. **NULL** будет возвращен, если:

- *sourceTime* представляет дату до полуночи, 1 января 1970 года, UTC.

- Если вы используете **_ctime32** или **_wctime32** и *sourceTime* представляет дату после 23:59:59 18 января 2038, UTC.

- Если вы используете **_ctime64** или **_wctime64** и *sourceTime* представляет дату после 23:59:59, 31 декабря 3000, UTC.

**ctime** является вневаемая функция, которая оценивает **_ctime64** и **time_t** эквивалентно **__time64_t.** Если вам нужно заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t,** вы можете определить **_USE_32BIT_TIME_T.** Это приведет к **ctime** для оценки **_ctime32**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

## <a name="remarks"></a>Remarks

Функция **ctime** преобразует временное значение, хранящееся как [time_t](../../c-runtime-library/standard-types.md) значение, в строку символов. Значение *sourceTime* обычно получено от звонока к [времени](time-time32-time64.md), которое возвращает число секунд прошло с полночи (00:00:00), 1-ое января 1970, координированное всеобщее время (UTC). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки ("\n") и нуль-символ ("\0") занимают две последние позиции строки.

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Просмотрите [функции time,](time-time32-time64.md) [_ftime](ftime-ftime32-ftime64.md)и [локального времени](localtime-localtime32-localtime64.md) для получения информации о настройке местного времени и [функции _tzset](tzset.md) для получения подробной информации об определении среды часового пояса и глобальных переменных.

Вызов **ctime** изменяет единый статически выделенный буфер, используемый **функциями gmtime** и **локального времени.** Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова. **ctime** разделяет статический буфер с функцией **asctime.** Таким образом, призыв к **ctime** разрушает результаты любого предыдущего вызова **asctime,** **местное время,** или **gmtime**.

**_wctime** и **_wctime64** являются широкохарактерные варианты **ctime** и **_ctime64;** возвращение указателя на широкохарактерную строку. В противном случае, **_ctime64,** **_wctime,** и **_wctime64** вести себя одинаково, чтобы **ctime**.

Эти функции проверяют свои параметры. Если *sourceTime* является нулевой указателем, или если значение *sourceTime* отрицательное, эти функции вызывают недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции возвращают **NULL** и устанавливают **errno** **в EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**Ctime**|**Ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> или \<wchar.h>|
|**_wctime32**|\<time.h> или \<wchar.h>|
|**_wctime64**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ctime64.c
// compile with: /W3
/* This program gets the current
* time in _time64_t form, then uses ctime to
* display the time in string form.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   __time64_t ltime;

   _time64( &ltime );
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996
   // Note: _ctime64 is deprecated; consider using _ctime64_s
}
```

```Output
The time is Wed Feb 13 16:04:43 2002
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
