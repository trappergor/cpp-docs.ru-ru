---
title: "Исключения. Исключения в конструкторах | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "конструкторы [C++], исключения"
  - "исключения, в конструкторах"
  - "создание исключений, в конструкторах"
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Исключения. Исключения в конструкторах
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При порождении исключения в конструкторе, очистка все объекты и выделения памяти, сделанные до возникновения исключения, как описано в разделе [Исключения: При порождении исключения из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 При порождении исключения в конструкторе, сама память для объекта уже была выбрана к моменту конструктор.  Таким образом, компилятор автоматически отменить память занятая объектом после того, как исключение будет вызвано.  
  
 Дополнительные сведения см. в разделе [Исключения: Освобождение объектов в исключениях](../Topic/Exceptions:%20Freeing%20Objects%20in%20Exceptions.md).  
  
## См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)