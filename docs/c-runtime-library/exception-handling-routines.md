---
title: "Процедуры обработки исключений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений, процедуры"
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Процедуры обработки исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте функции обработки исключений C\+\+, чтобы выйти из непредвиденных событий во время выполнения программы.  
  
### Функции обработки исключений  
  
|Функция|Применение|Эквивалент в .NET Framework|  
|-------------|----------------|---------------------------------|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 \(структурированные исключения языка С\) как типизированные исключения языка С\+\+|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Устанавливает собственную процедуру завершения, чтобы ее можно было вызвать с помощью `terminate`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Устанавливает вашу собственную завершающую функцию, которая будет вызываться `unexpected`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Вызывается автоматически в некоторых случаях после возникновения исключения.  Функция `terminate` вызывает `abort` или заданную с помощью `set_terminate` функцию.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[unexpected](../Topic/unexpected%20\(CRT\).md)|Вызывает `terminate` или функцию, заданную с помощью `set_unexpected`.  Функция `unexpected` не используется в текущей реализации обработки исключений C\+\+ Microsoft.|[\<caps:sentence id\="tgt30" sentenceid\="ec8332f3bf55c7bd183338eca87744ec" class\="tgtSentence"\>System::Exception Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)