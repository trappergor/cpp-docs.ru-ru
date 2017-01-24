---
title: "Ограничения обработчиков исключений | Microsoft Docs"
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
  - "ограничения, обработчики исключений"
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ограничения обработчиков исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Главное ограничение на использование обработчиков в коде состоит в том, что оператор `goto` не может использоваться для перехода в блок оператора `__try`.  Входить в этот блок необходимо только через обычный поток управления.  При желании вы можете переходить из блока оператора `__try`, а также создавать вложенные обработчики исключений.  
  
## См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md)