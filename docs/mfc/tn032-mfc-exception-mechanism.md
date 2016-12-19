---
title: "TN032. Механизм исключений MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CException - класс, использование"
  - "MFC - библиотека, исключения"
  - "TN032"
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN032. Механизм исключений MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В предыдущих версиях Visual C\+\+ не поддержке C — стандартный механизм исключения C\+\+, в MFC макрос **TRY\/CATCH\/THROW**, которые были использованы вместо.  Данная версия Visual C\+\+ полностью поддерживает исключения C C\+\+.  Эта заметка покрыла некоторые из дополнительных подробностей реализации предыдущих макросов, включая объекты автоматически на основе стека очистки.  Поскольку исключения C\+\+ поддерживают развертывание стека по умолчанию это техническом примечании больше не нужен.  
  
 Дополнительные сведения см. в разделе [Исключения: С помощью макросов MFC исключения C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) о различиях между макросами MFC новыми словами C\+\+.  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)