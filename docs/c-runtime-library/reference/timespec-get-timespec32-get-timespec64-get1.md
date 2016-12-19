---
title: "timespec_get, _timespec32_get, _timespec64_get | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
  - "time/timespec_get"
  - "time/_timespec32_get"
  - "time/_timespec64_get"
  - "timespec"
  - "_timespec32"
  - "_timespec64"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "функция timespec_get"
  - "функция _timespec32_get"
  - "функция _timespec64_get"
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# timespec_get, _timespec32_get, _timespec64_get
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает интервал, на который указывает первый аргумент, в текущее календарное время в соответствии с заданной базой времени.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `time_spec`  
 Указатель на структуру, которой присваивается время в секундах и наносекундах с начала эпохи.  
  
 `base`  
 Зависящее от реализации ненулевое значение, определяющее базу времени.  
  
## Возвращаемое значение  
 Значение `base`, если функция выполнена успешно; в противном случае возвращает ноль.  
  
## Заметки  
 Функция `timespec_get` присваивает текущее время структуре, на которую указывает аргумент `time_spec`. Все версии этой структуры имеют два члена: `tv_sec` и `tv_nsec`. Члену `tv_sec` присваивается целое число секунд, а члену `tv_nsec` — целое число наносекунд, округленное до разрешения системных часов, с начала эпохи, указанной в параметре `base`.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Эти функции допускают только `TIME_UTC` в качестве значения `base`. При этом аргументу `time_spec` присваивается количество секунд и наносекунд с начала эпохи, то есть с полудня 1 января 1970 года в формате UTC. В `struct _timespec32` значение `tv_sec` имеет тип `__time32_t`. В `struct _timespec64` значение `tv_sec` имеет тип `__time64_t`. В `struct timespec` значение `tv_sec` имеет тип `time_t` длиной 32 или 64 бита в зависимости от того, определен ли макрос препроцессора \_USE\_32BIT\_TIME\_T. Функция `timespec_get` — это встроенная функция, которая вызывает `_timespec32_get`, если определен макрос \_USE\_32BIT\_TIME\_T; в противном случае она вызывает `_timespec64_get`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`timespec_get`, `_timespec32_get`, `_timespec64_get`|C: \<time.h\>, C\+\+: \<ctime\> или \<time.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)