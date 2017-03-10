---
title: "Подпрограммы обработки исключений | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
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
ms.openlocfilehash: fe4946a8d3785c6295cb7537de0a11e06cd7a1cc
ms.lasthandoff: 02/24/2017

---
# <a name="exception-handling-routines"></a>Процедуры обработки исключений
Использование функций обработки исключений C++ для восстановления после непредвиденных событий во время выполнения программы.  
  
### <a name="exception-handling-functions"></a>Функции обработки исключений  
  
|Функция|Применение|Эквивалент .NET Framework|  
|--------------|---------|-------------------------------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Установите собственную подпрограмму завершения, чтобы ее можно было вызвать с помощью функции `terminate`|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Установите собственную функцию завершения, чтобы ее можно было вызвать с помощью функции `unexpected`|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Вызывается автоматически при определенных условиях после исключения. Эта функция `terminate` вызывает функцию `abort` или функцию, указанную с помощью `set_terminate`|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Вызывает функцию `terminate` или функцию, заданную с помощью `set_unexpected`. Функция `unexpected` не используется в текущей реализации обработчика исключений Microsoft C++|[Класс System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
