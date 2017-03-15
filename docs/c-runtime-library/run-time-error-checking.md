---
title: "Проверка ошибок во время выполнения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e5ffb6d3321637b662790a32cce65e6908b4778d
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-error-checking"></a>Проверка ошибок во время выполнения
Библиотека времени выполнения C содержит функции, поддерживающие проверку ошибок во время выполнения (RTC). Проверка ошибок во время выполнения позволяет строить программы так, чтобы получать сообщения о некоторых типах ошибок, возникающих во время выполнения. Можно указать, каким образом происходит уведомление об ошибках, а также типы этих ошибок. Дополнительные сведения см. в статье о [проверках ошибок во время выполнения](http://msdn.microsoft.com/Library/dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1).  
  
 Для настройки выполнения проверок на ошибки во время выполнения используются следующие функции.  
  
### <a name="run-time-error-checking-functions"></a>Функции проверки на ошибки во время выполнения  
  
|Функция|Применение|Эквивалент .NET Framework|  
|--------------|---------|-------------------------------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Возвращает краткое описание типа проверки на ошибки во время выполнения.||  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Возвращает общее количество ошибок, которые могут быть обнаружены путем проверки во время выполнения.||  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения.||  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Связывает обнаруженную проверкой во время выполнения ошибку с типом.||  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC (проверки ошибок во время выполнения)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [RTC Sample: Run-Time Error Checks](http://msdn.microsoft.com/en-us/b3415b09-f6fd-43dc-8c02-9a910bc2574e)  (Образец RTC: проверки ошибок во время выполнения)  
 [Процедуры отладки](../c-runtime-library/debug-routines.md)
