---
title: "_mkgmtime, _mkgmtime32, _mkgmtime64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs:
- C++
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7eec9b123c47b13c73836fd41a2c490951e4fecd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64
Преобразует время в формате UTC, представленное типом `tm struct`, во время в формате UTC, представленное типом `time_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      time_t _mkgmtime(  
   struct tm* timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm* timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm* timeptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `timeptr`  
 Указатель на время в формате UTC в виде `struct tm` для преобразования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа `__time32_t` или `__time64_t`, представляющее количество секунд, истекших после полуночи 1 января 1970 года, в формате UTC. Если дата выходит за пределы диапазона (см. в разделе "Примечания") или входные данные не могут восприниматься как допустимое время, возвращается значение-1.  
  
## <a name="remarks"></a>Примечания  
 Функции `_mkgmtime32` и `_mkgmtime64` преобразовывают время в формате UTC в тип `__time32_t` или `__time64_t`, представляющий время в формате UTC. Для преобразования местного времени во время в формате UTC вместо этого используйте `mktime`, `_mktime32` и `_mktime64`.  
  
 `_mkgmtime` — встроенная функция, которая принимает значение `_mkgmtime64` и `time_t` эквивалентна `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. Это не рекомендуется, так как приложение может завершиться ошибкой после 18 января 2038 года (максимальный диапазон 32-разрядного значения `time_t`), и оно абсолютно не допускается на 64-разрядных платформах.  
  
 Переданная структура времени будет изменена следующим образом, точно так же, как они изменяются с помощью функций `_mktime`: поля `tm_wday` и `tm_yday` принимают новые значения, основанные на значениях `tm_mday` и `tm_year`. При указании времени структуры `tm` задайте для поля `tm_isdst` значение:  
  
-   нуль (0), чтобы указать, что действует стандартное время;  
  
-   значение больше нуля, чтобы указать, что действует переход на зимнее время;  
  
-   значение меньше нуля, чтобы указать, что код библиотеки времени выполнения языка C должен вычислить, действует ли стандартное время или переход на зимнее время.  
  
 Библиотека времени выполнения языка C использует переменную среды TZ для определения правильного летнего времени. Если TZ не задана, для получения верного регионального поведения по летнему времени отправляется запрос операционной системе. `tm_isdst` — это обязательное поле. Если оно не задано, его значение не определено, и возвращаемое значение `mktime` непредсказуемо.  
  
 Диапазон функции `_mkgmtime32` — от полуночи 1 января 1970 года, время в формате UTC, до 23:59:59 18 января 2038 года, время в формате UTC. Диапазон `_mkgmtime64` — от полуночи 1 января 1970 года, время в формате UTC, до 23:59:59 31 декабря 3000 года, время в формате UTC. Дата вне диапазона результатов возвращается значение-1. Диапазон `_mkgmtime` зависит от того, определено ли значение `_USE_32BIT_TIME_T`. Если оно не определено (по умолчанию), диапазон тот же, что у `_mkgmtime64`; в противном случае диапазон ограничен 32-разрядным диапазоном `_mkgmtime32`.  
  
 Следует отметить, что `gmtime` и `localtime` используют для преобразования один статически выделенный буфер. Если предоставить этот буфер `mkgmtime`, его предыдущее содержимое удаляется.  
  
## <a name="example"></a>Пример  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 В следующем примере показано, как неполная структура заполняется вычисленными значения дня недели и дня года.  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)