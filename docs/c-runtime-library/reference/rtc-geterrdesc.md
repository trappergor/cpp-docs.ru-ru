---
title: "_RTC_GetErrDesc | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_GetErrDesc"
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
apitype: "DLLExport"
f1_keywords: 
  - "RTC_GetErrDesc"
  - "_RTC_GetErrDesc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ошибки во время выполнения"
  - "_RTC_GetErrDesc - функция"
  - "RTC_GetErrDesc - функция"
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_GetErrDesc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает краткое описание типа проверки на ошибки во время выполнения \(RTC\).  
  
## Синтаксис  
  
```  
  
const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber   
errnum  
);  
  
```  
  
#### Параметры  
 *errnum*  
 Число от нуля до единицы и меньше значения, возвращаемого `_RTC_NumErrors`.  
  
## Возвращаемое значение  
 Строка символов, которая содержит краткое описание одного из типов ошибок, обнаруженного системой проверки на ошибки во время выполнения. Если ошибка меньше нуля или больше или равна значению, возвращенному [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md), `_RTC_GetErrDesc` возвращает NULL.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h\>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [Проверка ошибок во время выполнения](../Topic/Run-Time%20Error%20Checking.md)