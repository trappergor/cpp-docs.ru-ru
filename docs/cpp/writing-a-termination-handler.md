---
title: "Написание обработчика завершения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a4a90c28f9bb2a681e88463dfd6bd9d3ff0a1d99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="writing-a-termination-handler"></a>Написание обработчика завершения
В отличие от обработчика исключений, обработчик завершения выполняется всегда независимо от того, завершен ли в обычном режиме защищенный блок кода. Единственным назначением обработчика завершения должна быть проверка правильности закрытия таких ресурсов, как память, дескрипторы и файлы, независимо от того, как завершается выполнение фрагмента кода.  
  
 Обработчики завершения используют оператор try-finally.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Оператор try-finally](../cpp/try-finally-statement.md)  
  
-   [Освобождение ресурсов](../cpp/cleaning-up-resources.md)  
  
-   [Время действий в обработке исключений](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [Ограничения обработчиков завершения](../cpp/restrictions-on-termination-handlers.md)  
  
## <a name="see-also"></a>См. также  
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)