---
title: "localtime_s, _localtime32_s, _localtime64_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e068c6711630976a2d8b3baea01010bc5e34ed6e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s
Преобразует значение времени и корректирует его для местного часового пояса. Это версии функций [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `_tm`  
 Указатель на структуру времени, которую требуется заполнить.  
  
 `time`  
 Указатель на хранимое время.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`_tm`|`time`|Возвращаемое значение|Значение в `_tm`|Вызывает обработчик недопустимого параметра|  
|-----------|------------|------------------|--------------------|---------------------------------------|  
|`NULL`|любые|`EINVAL`|Без изменений|Да|  
|Не `NULL` (указывает на допустимую память)|`NULL`|`EINVAL`|Во всех полях заданы значения –1|Да|  
|Не `NULL` (указывает на допустимую память)|имеет значение меньше 0 или больше `_MAX__TIME64_T`|`EINVAL`|Во всех полях заданы значения –1|Нет|  
  
 В случае первых двух условий ошибки вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_localtime32_s` преобразует время, хранящееся в виде значения [time_t](../../c-runtime-library/standard-types.md), и сохраняет результат в структуре типа `tm`. Значение `long` типа `timer` представляет секунды, прошедшие с полуночи (00:00:00) 1-го января 1970 года в формате UTC. Это значение обычно получается из функции `time`.  
  
 Функция `_localtime32_s` выполняет коррекцию для местного часового пояса, если пользователь сначала задает глобальную переменную среды `TZ`. Если переменная `TZ` задана, автоматически устанавливаются три других переменных среды (`_timezone`, `_daylight` и `_tzname`). Если переменная `TZ` не задана, функция `localtime32_s` пытается использовать данные часового пояса, определенные в приложении Дата/время в Панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](../../c-runtime-library/reference/tzset.md). `TZ` представляет собой расширение Microsoft и не является частью стандарта ANSI для `localtime`.  
  
> [!NOTE]
>  Целевая среда должна попытаться определить, действует ли летнее время.  
  
 Функция `_localtime64_s`, которая использует структуру `__time64_t`, допускает даты до 23:59:59 18 декабря 3001 года в формате UTC, тогда как функция `_localtime32_s` представляет даты до 23:59:59 18 января 2038 года в формате UTC.  
  
 `localtime_s` — подставляемая функция, эквивалентная функции `_localtime64_s`; функция `time_t` эквивалентна функции `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `localtime_s` будет вычисляться как `_localtime32_s`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.  
  
 Поля структуры типа [tm](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых имеет тип `int`.  
  
 `tm_sec`  
 Секунды после минуты (0 - 59).  
  
 `tm_min`  
 Минуты после часа (0 - 59).  
  
 `tm_hour`  
 Часы после полуночи (0 - 23).  
  
 `tm_mday`  
 День месяца (1-31).  
  
 `tm_mon`  
 Месяц (0 – 11; Январь = 0).  
  
 `tm_year`  
 Год (текущий год минус 1900).  
  
 `tm_wday`  
 День недели (0 – 6; Воскресенье = 0).  
  
 `tm_yday`  
 День года (0 – 365; 1 января = 0).  
  
 `tm_isdst`  
 Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно. Если задана переменная среды `TZ`, для реализации перехода на летнее время (DST) в библиотеке времени выполнения C принимаются правила, подходящие для США.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`localtime_s`|\<time.h>|  
|`_localtime32_s`|\<time.h>|  
|`_localtime64_s`|\<time.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)

