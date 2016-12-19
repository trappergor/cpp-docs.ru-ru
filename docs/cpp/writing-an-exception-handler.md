---
title: "Написание обработчика исключений | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений, обработчики исключений"
  - "структурированная обработка исключений, обработчики исключений"
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Написание обработчика исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обработчики исключений обычно используются для ответа на конкретные ошибки.  Можно использовать синтаксис обработки исключений, чтобы фильтровать все исключения, отличные от тех, которые вы знаете, как обработать.  Прочие исключения должны передаваться другим обработчикам \(возможно, в библиотеке среды выполнения или ОС\), созданным для поиска этих конкретных исключений.  
  
 Обработчики исключений используют оператор try\-except.  
  
## Дополнительные сведения  
  
-   [Оператор try\-except](../cpp/try-except-statement.md)  
  
-   [Написание фильтра исключений](../cpp/writing-an-exception-filter.md)  
  
-   [Создание программных исключений](../cpp/raising-software-exceptions.md)  
  
-   [Аппаратные исключения](../cpp/hardware-exceptions.md)  
  
-   [Ограничения, действующие в отношении обработчиков исключений](../cpp/restrictions-on-exception-handlers.md)  
  
## См. также  
 [Структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md)