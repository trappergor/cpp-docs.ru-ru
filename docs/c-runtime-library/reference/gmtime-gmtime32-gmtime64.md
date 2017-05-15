---
title: "gmtime, _gmtime32, _gmtime64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
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
ms.openlocfilehash: d6acd03622ffd309e394fc076c2922492ac2475b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64
Преобразует значение времени в структуру. Существуют более безопасные версии этих функций; см. раздел [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `timer`  
 Указатель на хранимое время. Время представляется в виде секунд, истекших после полуночи (00:00:00) 1-го января 1970 года, время в формате UTC.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру типа [tm](../../c-runtime-library/standard-types.md). Поля возвращаемой структуры содержат вычисленное значение аргумента `timer` в формате UTC, а не по местному времени. Каждое из полей структуры имеет тип `int`, как описано далее:  
  
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
 Всегда 0 для `gmtime`.  
  
 32- и 64-разрядные версии функций `gmtime`, `mktime`, `mkgmtime` и `localtime` для преобразования используют одну общую для каждого потока структуру `tm`. Каждый вызов одной из этих функций уничтожает результат любого предыдущего вызова. Если `timer` представляет дату перед полночью 1-го января 1970 года, функция `gmtime` возвращает значение `NULL`. Ошибка не возвращается.  
  
 Функция `_gmtime64`, которая использует структуру `__time64_t`, поддерживает даты до 23:59:59 31 декабря 3000 года в формате UTC; при этом функция `_gmtime32` представляет даты только до 23:59:59 18 января 2038 года в формате UTC. Полночь 1-ого января 1970 года — нижняя граница диапазона дат для обеих функций.  
  
 `gmtime` — это подставляемая функция, эквивалентная функции `_gmtime64`; функция `time_t` эквивалентна функции `__time64_t`, если не определена директива `_USE_32BIT_TIME_T`. Если необходимо, чтобы компилятор принудительно интерпретировал структуру `time_t` как старую 32-разрядную структуру `time_t`, можно определить директиву `_USE_32BIT_TIME_T`, но это приводит к тому, что функция `gmtime` подставляется в код как функция `_gmtime32`, а структура `time_t` определяется как `__time32_t`. Рекомендуется не делать этого, поскольку данная возможность не поддерживается на 64-разрядных платформах и, в любом случае, ваше приложение может завершиться с ошибкой после 18-го января 2038 года.  
  
 Эти функции проверяют свои параметры. Если параметр `timer` представляет собой указатель NULL или значение таймера отрицательно, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр `errno` в значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_gmtime32` разбирает значение `timer` и сохраняет его в статически выделенной структуре типа `tm`, определенной в файле TIME.H. Значение параметра `timer` обычно получается из вызова функции `time`.  
  
> [!NOTE]
>  В большинстве случаев целевая среда пытается определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
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
  
int main( void )  
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
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
