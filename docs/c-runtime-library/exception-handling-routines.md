---
title: "Подпрограммы обработки исключений | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3dd5d8dd77f2b62a6b0ea52e7d056b3d779cd2f4
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="exception-handling-routines"></a>Процедуры обработки исключений
Использование функций обработки исключений C++ для восстановления после непредвиденных событий во время выполнения программы.  
  
### <a name="exception-handling-functions"></a>Функции обработки исключений  
  
|Функция|Применение|  
|--------------|---------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Установите собственную подпрограмму завершения, чтобы ее можно было вызвать с помощью функции `terminate`|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Установите собственную функцию завершения, чтобы ее можно было вызвать с помощью функции `unexpected`|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Вызывается автоматически при определенных условиях после исключения. Эта функция `terminate` вызывает функцию `abort` или функцию, указанную с помощью `set_terminate`|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Вызывает функцию `terminate` или функцию, заданную с помощью `set_unexpected`. Функция `unexpected` не используется в текущей реализации обработчика исключений Microsoft C++|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
