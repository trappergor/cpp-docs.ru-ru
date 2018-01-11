---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97c6f5f4c827ca315eb1de36ee8d4f19d94214bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Доступны более безопасные версии этих функций; см. раздел [ctime_s _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `timer`  
 Указатель на сохраненное время.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на результирующую строку символов. Значение `NULL` возвращается в следующих случаях:  
  
-   `time` представляет дату перед полуночью 1-го января 1970 года, в формате UTC.  
  
-   Если используется функция `_ctime32` или `_wctime32`, а `time` представляет дату после 23:59:59 18-го января 2038 года.  
  
-   Если используется функция `_ctime64` или `_wctime64` и `time` представляет дату после 23:59:59 31-го декабря 3000 года (в формате UTC).  
  
 `ctime` — встроенная функция, которая принимает значение `_ctime64`; функция `time_t` эквивалентна функции `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `ctime` будет вычисляться как `_ctime32`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.  
  
## <a name="remarks"></a>Примечания  
 Функция `ctime` преобразует значение времени, хранящееся в виде [time_t](../../c-runtime-library/standard-types.md), в символьную строку. Значение `timer` обычно получается из вызова функции [time](../../c-runtime-library/reference/time-time32-time64.md), которая возвращает количество секунд, истекших после полуночи (00:00:00) 1-го января 1970 года (в формате UTC). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки ("\n") и нуль-символ ("\0") занимают две последние позиции строки.  
  
 Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Подробные сведения о настройке местного времени см. в описании функций `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [_tzset](../../c-runtime-library/reference/tzset.md).  
  
 Вызов функции `ctime` изменяет один статически выделенный буфер, используемый функциями `gmtime` и `localtime`. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова. Функция `ctime` делит статический буфер с функцией `asctime`. Таким образом, вызов функции `ctime` уничтожает результаты любого предыдущего вызова функций `asctime`, `localtime` или `gmtime`.  
  
 `_wctime` и `_wctime64` — версии функций `ctime` и `_ctime64` для расширенных символов; возвращают указатель на строку из расширенных символов. В остальном поведение функций `_ctime64`, `_wctime` и `_wctime64` совпадает с поведением функции `ctime`.  
  
 Эти функции проверяют свои параметры. Если параметр `timer` представляет собой указатель NULL или значение таймера отрицательно, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр `errno` в значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`ctime`|\<time.h>|  
|`_ctime32`|\<time.h>|  
|`_ctime64`|\<time.h>|  
|`_wctime`|\<time.h> или \<wchar.h>|  
|`_wctime32`|\<time.h> или \<wchar.h>|  
|`_wctime64`|\<time.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)