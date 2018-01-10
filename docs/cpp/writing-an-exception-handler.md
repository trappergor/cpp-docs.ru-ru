---
title: "Написание обработчика исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52d102f29a015ea077e9ec94a9f1ed63f44f7c1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-exception-handler"></a>Написание обработчика исключений
Обработчики исключений обычно используются для ответа на конкретные ошибки. Можно использовать синтаксис обработки исключений, чтобы фильтровать все исключения, отличные от тех, которые вы знаете, как обработать. Прочие исключения должны передаваться другим обработчикам (возможно, в библиотеке среды выполнения или ОС), созданным для поиска этих конкретных исключений.  
  
 Обработчики исключений используют оператор try-except.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Try-except инструкции](../cpp/try-except-statement.md)  
  
-   [Написание фильтра исключений](../cpp/writing-an-exception-filter.md)  
  
-   [Создание исключений программного обеспечения](../cpp/raising-software-exceptions.md)  
  
-   [Исключения оборудования](../cpp/hardware-exceptions.md)  
  
-   [Ограничения обработчиков исключений](../cpp/restrictions-on-exception-handlers.md)  
  
## <a name="see-also"></a>См. также  
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)