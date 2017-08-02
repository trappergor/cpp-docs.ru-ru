---
title: "Проверка ошибок во время выполнения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 3aa56b70b02500998665289e69480570cfa39166
ms.contentlocale: ru-ru
ms.lasthandoff: 06/08/2017

---
# <a name="run-time-error-checking"></a>Проверка ошибок во время выполнения
Библиотека времени выполнения C содержит функции, поддерживающие проверку ошибок во время выполнения (RTC). Проверка ошибок во время выполнения позволяет строить программы так, чтобы получать сообщения о некоторых типах ошибок, возникающих во время выполнения. Можно указать, каким образом происходит уведомление об ошибках, а также типы этих ошибок. Дополнительная информация есть в статье [Практическое руководство. Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
 Для настройки выполнения проверок на ошибки во время выполнения используются следующие функции.  
  
### <a name="run-time-error-checking-functions"></a>Функции проверки на ошибки во время выполнения  
  
|Функция|Применение|  
|--------------|---------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Возвращает краткое описание типа проверки на ошибки во время выполнения.|  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Возвращает общее количество ошибок, которые могут быть обнаружены путем проверки во время выполнения.|  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения.|  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Связывает обнаруженную проверкой во время выполнения ошибку с типом.|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC (проверки ошибок во время выполнения)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [Процедуры отладки](../c-runtime-library/debug-routines.md)
