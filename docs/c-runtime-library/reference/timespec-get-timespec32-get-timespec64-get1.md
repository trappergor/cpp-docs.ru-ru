---
title: "timespec_get, _timespec32_get, _timespec64_get1 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
dev_langs:
- C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13b85eef72ed1a2180af1b41bf93eefe499967bd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get
Устанавливает интервал, на который указывает первый аргумент, в текущее календарное время в соответствии с заданной базой времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `time_spec`  
 Указатель на структуру, которой присваивается время в секундах и наносекундах с начала эпохи.  
  
 `base`  
 Зависящее от реализации ненулевое значение, определяющее базу времени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `base` , если функция выполнена успешно; в противном случае возвращает ноль.  
  
## <a name="remarks"></a>Примечания  
 Функция `timespec_get` присваивает текущее время структуре, на которую указывает аргумент `time_spec` . Все версии этой структуры имеют два члена: `tv_sec` и `tv_nsec`. Члену `tv_sec` присваивается целое число секунд, а члену `tv_nsec` — целое число наносекунд, округленное до разрешения системных часов, с начала эпохи, указанной в параметре `base`.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Эти функции допускают только `TIME_UTC` в качестве значения `base` . При этом аргументу `time_spec` присваивается количество секунд и наносекунд с начала эпохи, то есть с полудня 1 января 1970 года в формате UTC. В `struct _timespec32`значение `tv_sec` имеет тип `__time32_t` . В `struct _timespec64`значение `tv_sec` имеет тип `__time64_t` . В `struct timespec`значение `tv_sec` имеет тип `time_t` длиной 32 или 64 бита в зависимости от того, определен ли макрос препроцессора _USE_32BIT_TIME_T. Функция `timespec_get` — это встроенная функция, которая вызывает `_timespec32_get` , если определен макрос _USE_32BIT_TIME_T; в противном случае она вызывает `_timespec64_get`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`timespec_get`значение `_timespec32_get`значение `_timespec64_get`|C: \<time.h>, C++: \<ctime> или \<time.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)