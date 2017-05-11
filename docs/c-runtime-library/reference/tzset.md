---
title: "_tzset | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tzset
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
- _tzset
dev_langs:
- C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 669b7d41234c21c3fb4e9a1a28f6b8d1a33c036b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="tzset"></a>_tzset
Задает переменные среды, относящиеся ко времени.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье                  [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>Примечания  
 Функция `_tzset` использует текущую настройку переменной среды `TZ` для присвоения значения трем глобальным переменным: `_daylight`, `_timezone`и `_tzname`. Эти переменные используются функциями [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) для внесения коррекций из времени в формате UTC в местное время, а также функцией `time` для вычисления времени в формате UTC на основе системного времени. Для задания переменной среды `TZ` используйте следующий синтаксис:  
  
 `set` `TZ`=`tzn`[+ &#124; -]`hh`[`:``mm`[`:``ss`] ][`dzn`]  
  
 `tzn`  
 Трехбуквенное имя часового пояса, например, PST. Необходимо указать правильное смещение локального времени относительно времени в формате UTC.  
  
 `hh`  
 Различие в часах между временем в формате UTC и местным временем. Знак (+) для положительных значений необязателен.  
  
 `mm`  
 Минуты. Отделяются от `hh` двоеточием (`:`).  
  
 `ss`  
 Секунды. Отделяются от `mm` двоеточием (`:`).  
  
 `dzn`  
 Трехбуквенный часовой пояс с переходом на летнее время, например, PDT. Если в местоположении летнее время не действует, установите `TZ` без значения для `dzn`. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).  
  
> [!NOTE]
>  Не забывайте о вычислении знака разницы во времени. Поскольку разница во времени является смещением локального времени относительно времени в формате UTC (а не наоборот), ее знак может отличаться от интуитивно ожидаемого. Для часовых поясов до пояса времени в формате UTC разница во времени отрицательная; для часовых поясов после пояса времени в формате UTC разница положительная.  
  
 Например, чтобы задать переменную среды `TZ` в соответствии с текущим часовым поясом в Германии, введите в командной строке:  
  
```  
set TZ=GST-1GDT  
```  
  
 Эта команда использует GST для указания немецкого стандартного времени, учитывая, что время в формате UTC отстает на один час от времени в Германии (или, другими словами, что время в Германии на один час опережает время в формате UTC) и учитывая, что Германия использует переход на летнее время.  
  
 Если `TZ` значение не задано, `_tzset` пытается использовать данные часового пояса, определенные операционной системой. В операционной системе Windows эти данные определяются в приложении Дата/время в Панели управления. Если функция `_tzset` не сможет получить эти сведения, она использует PST8PDT по умолчанию, что означает тихоокеанский часовой пояс.  
  
 На основе значения переменной среды `TZ` при вызове функции `_daylight`глобальным переменным `_timezone`, `_tzname` и `_tzset` присваиваются следующие значения:  
  
|Глобальная переменная|Описание|Значение по умолчанию|  
|---------------------|-----------------|-------------------|  
|`_daylight`|Ненулевое значение, если в параметре `TZ` задан часовой пояс с переходом на летнее время; в противном случае — значение 0.|1|  
|`_timezone`|Разница в секундах между местным временем и временем в формате UTC.|28800 (28800 секунд равны 8 часам)|  
|`_tzname`[0]|Строковое значение имени часового пояса из переменной среды `TZ` ; пусто, если переменная `TZ` не задана.|PST|  
|`_tzname`[1]|Строковое значение часового пояса с переходом на летнее время; пусто, если часовой пояс с переходом на летнее время опущен в переменной среды `TZ` .|PDT|  
  
 Значения по умолчанию, указанные в предыдущей таблице для `_daylight` , и массив `_tzname` соответствуют "PST8PDT". Если в переменной среды `TZ` зона летнего времени опущена, значение `_daylight` равно 0, и функции `_ftime`, `gmtime`и `localtime` возвращают значение 0 для флагов летнего времени.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_tzset`|\<time.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_tzset.cpp  
// This program uses _tzset to set the global variables  
// named _daylight, _timezone, and _tzname. Since TZ is  
// not being explicitly set, it uses the system time.  
  
#include <time.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    _tzset();  
    int daylight;  
    _get_daylight( &daylight );  
    printf( "_daylight = %d\n", daylight );  
    long timezone;  
    _get_timezone( &timezone );  
    printf( "_timezone = %ld\n", timezone );  
    size_t s;  
    char tzname[100];  
    _get_tzname( &s, tzname, sizeof(tzname), 0 );  
    printf( "_tzname[0] = %s\n", tzname );  
    exit( 0 );  
}  
```  
  
```Output  
_daylight = 1  
_timezone = 28800  
_tzname[0] = Pacific Standard Time  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)
