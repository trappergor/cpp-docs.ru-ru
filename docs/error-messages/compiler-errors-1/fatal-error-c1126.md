---
title: "Неустранимая ошибка C1126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1126"
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": автоматическое выделение памяти превышает допустимый размер  
  
 Пространство, выделенное для локальных переменных функции \(а также ограниченное пространство, используемое компилятором, например, дополнительные 20 Б для изменяемых функций\), превышает максимально допустимое значение.  
  
 Чтобы исправить данную ошибку, для выделения большого объема памяти для данных следует использовать `malloc` или `new`.