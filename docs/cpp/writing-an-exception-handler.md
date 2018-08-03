---
title: Написание обработчика исключений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb06c23e17f16bdf33fe469327351105d6a4571c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461053"
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