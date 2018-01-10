---
title: "Ограничения обработчиков исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9e55ba9c36fdbc5f3c19e7ad81373599ab138e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений
Главное ограничение на использование обработчиков в коде состоит в том, что оператор `goto` не может использоваться для перехода в блок оператора `__try`. Входить в этот блок необходимо только через обычный поток управления. При желании вы можете переходить из блока оператора `__try`, а также создавать вложенные обработчики исключений.  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)