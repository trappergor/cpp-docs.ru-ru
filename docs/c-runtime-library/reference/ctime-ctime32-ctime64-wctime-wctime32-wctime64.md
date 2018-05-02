---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
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
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53640ab7ae25384fca1e148bfbdd311530f00a49
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

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

*sourceTime*<br/>
Указатель на сохраненное время для преобразования.

## <a name="return-value"></a>Возвращаемое значение

Указатель на результирующую строку символов. **Значение NULL** будет возвращено, если:

- *sourceTime* представляет дату перед полуночью 1 января 1970 года в формате UTC.

- Если вы используете **_ctime32** или **_wctime32** и *sourceTime* представляет дату после 23:59:59 18 января 2038 года, время UTC.

- Если вы используете **_ctime64** или **_wctime64** и *sourceTime* представляет дату после 23:59:59, 31 декабря 3000 года, время UTC.

**CTime** — это встроенная функция, которая принимает значение **_ctime64** и **time_t** эквивалентно **__time64_t**. Если вам нужно заставляют компилятор интерпретировать **time_t** как старое 32-разрядное **time_t**, можно определить **_USE_32BIT_TIME_T**. Результате **ctime** будет вычисляться как **_ctime32**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

## <a name="remarks"></a>Примечания

**Ctime** функция преобразует значение времени хранится как [time_t](../../c-runtime-library/standard-types.md) значение в символьную строку. *SourceTime* значение обычно получается из вызова [время](time-time32-time64.md), который возвращает количество секунд, истекших после полуночи (00: 00:00), 1 января 1970 года всеобщего скоординированного времени (UTC). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки ("\n") и нуль-символ ("\0") занимают две последние позиции строки.

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. В разделе [время](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), и [localtime](localtime-localtime32-localtime64.md) функции для получения сведений о настройке местного времени и [_tzset](tzset.md) функции для сведения об определении среды часового пояса и глобальных переменных.

Вызов **ctime** изменяет один статически выделенный буфер, используемый **gmtime** и **localtime** функции. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова. **CTime** делит статический буфер с **asctime** функции. Таким образом, вызов **ctime** уничтожает результаты любого предыдущего вызова **asctime**, **localtime**, или **gmtime**.

**_wctime** и **_wctime64** — это двухбайтовая версия **ctime** и **_ctime64**; возвращают указатель на строку расширенных символов. В противном случае **_ctime64**, **_wctime**, и **_wctime64** ведут себя идентично **ctime**.

Эти функции проверяют свои параметры. Если *sourceTime* является пустым указателем, или если *sourceTime* имеет отрицательное значение, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают **NULL** и задайте **errno** для **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**ctime**|**ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> или \<wchar.h>|
|**_wctime32**|\<time.h> или \<wchar.h>|
|**_wctime64**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
