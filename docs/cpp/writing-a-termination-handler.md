---
title: "Написание обработчика завершения | Microsoft Docs"
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
  - "обработка исключений, обработчики завершения"
  - "исключения, завершение"
  - "обработчики"
  - "обработчики, завершение"
  - "структурированная обработка исключений, обработчики завершения"
  - "обработчики завершения"
  - "обработчики завершения, написание"
  - "try-catch - ключевое слово [C++], обработчики завершения"
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Написание обработчика завершения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В отличие от обработчика исключений, обработчик завершения выполняется всегда независимо от того, завершен ли в обычном режиме защищенный блок кода.  Единственным назначением обработчика завершения должна быть проверка правильности закрытия таких ресурсов, как память, дескрипторы и файлы, независимо от того, как завершается выполнение фрагмента кода.  
  
 Обработчики завершения используют оператор try\-finally.  
  
## Дополнительные сведения  
  
-   [Оператор try\-finally](../cpp/try-finally-statement.md)  
  
-   [Очистка ресурсов](../cpp/cleaning-up-resources.md)  
  
-   [Время действий в обработке исключений](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [Ограничения, накладываемые на обработчики завершения](../cpp/restrictions-on-termination-handlers.md)  
  
## См. также  
 [Структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md)