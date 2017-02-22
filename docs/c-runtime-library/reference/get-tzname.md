---
title: "_get_tzname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_tzname"
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
  - "_get_tzname"
  - "get_tzname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_tzname - функция"
  - "get_tzname - функция"
  - "часовые пояса"
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_tzname
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает представление в виде символьной строки имени часового пояса или имени зоны стандартного летнего времени \(DST\).  
  
## Синтаксис  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### Параметры  
 \[исходящий\] `pReturnValue`  
 Длина строки `timeZoneName`, включая конечный нуль\-символ.  
  
 \[исходящий\] `timeZoneName`  
 Адрес символьной строки для представления имени часового пояса или имени зоны стандартного летнего времени \(DST\), в зависимости от `index`.  
  
 \[входящий\] `sizeInBytes`  
 Размер символьной строки `timeZoneName` в байтах.  
  
 \[входящий\] `index`  
 Индекс одного из двух имен часового пояса, который необходимо извлечь.  
  
## Возвращаемое значение  
 Ноль в случае успеха, в противном случае значение типа `errno`.  
  
 Если либо `timeZoneName` равно `NULL`, либо `sizeInBytes` равно нулю или меньше нуля \(но не и то, и то\), вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `EINVAL`.  
  
### Условия возникновения ошибки  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Возвращаемое значение|Содержимое `timeZoneName`.|  
|--------------------|--------------------|-------------------|-------------|---------------------------|--------------------------------|  
|размер имени TZ|`NULL`|0|0 или 1|0|без изменений|  
|размер имени TZ|any|\> 0|0 или 1|0|имя TZ|  
|без изменений|`NULL`|\> 0|any|`EINVAL`|без изменений|  
|без изменений|any|нуль|any|`EINVAL`|без изменений|  
|без изменений|any|\> 0|\> 1|`EINVAL`|без изменений|  
  
## Заметки  
 Функция `_get_tzname` извлекает представление в виде символьной строки имени часового пояса или имени зоны стандартного летнего времени \(DST\) в адрес `timeZoneName`, в зависимости от значения индекса, а также размера строки в `pReturnValue`.  Если `timeZoneName` равно `NULL`, и `sizeInBytes` равно нулю, размер строки в байтах любого часового пояса возвращается в `pReturnValue`.  Значения индекса должны быть либо 0 для зоны стандартного времени, либо 1 для зоны стандартного летнего времени; все остальные значения индекса приводят к неопределённым результатам.  
  
### Значения индекса  
  
|`index`|Содержимое `timeZoneName`.|Значение `timeZoneName` по умолчанию|  
|-------------|--------------------------------|------------------------------------------|  
|0|Имя часового пояса|"PST"|  
|1|Имя зоны стандартного летнего времени|"PDT"|  
|\> 1 или \< 0|`errno` принимает значение `EINVAL`.|без изменений|  
  
 Если значения явно не изменяются во время выполнения, значения по умолчанию равны «PST» и «PDT» соответственно.  Размеры этих массивов символов управляются значением `TZNAME_MAX`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_tzname`|\<time.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME\_MAX](../Topic/TZNAME_MAX.md)