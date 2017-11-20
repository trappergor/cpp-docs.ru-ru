---
title: "Надежность | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime
dev_langs: C++
helpviewer_keywords: robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27412403fe6ce0f1884a2ea99790376acb1c5236
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="robustness"></a>Устойчивость
Используйте следующие функции библиотеки времени выполнения языка C, чтобы повысить надежность своей программы.  
  
### <a name="run-time-robustness-functions"></a>Функции повышения надежности во время выполнения  
  
|Функция|Применение|  
|--------------|---------|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Передает управление механизму обработки ошибок, если оператору `new` не удается выделить память.|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++.|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [terminate](../c-runtime-library/reference/terminate-crt.md).|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [unexpected](../c-runtime-library/reference/unexpected-crt.md).|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)