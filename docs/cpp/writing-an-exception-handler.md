---
title: "Написание обработчика исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling, exception handlers
- exception handling, exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5f3f81ff6ea954cda7270ff32650d5744280d918
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
