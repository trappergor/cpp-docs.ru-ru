---
title: "CString Exception Cleanup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString objects, исключения"
  - "обработка исключений, cleanup code"
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CString Exception Cleanup
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В предыдущих версиях MFC, важно очищаете поиск объектов [CString](../atl-mfc-shared/reference/cstringt-class.md) после использования.  С версией MFC 3,0 и более поздней, явной очисткой больше не требуется.  
  
 Под механизмом обработки исключений C\+\+, теперь использует MFC, не следует беспокоиться об очистке после исключения.  Описание например C\+\+ "очистки" стек после того, как исключение перехватывается см. в разделе [попытка, catch и выписки хода](../cpp/try-throw-and-catch-statements-cpp.md).  Даже если используется MFC **TRY** и макросы **CATCH** вместо ключевых слов **try** и **catch** C\+\+, MFC использует механизм исключения C\+\+ под ними, поэтому вам не нужно очистить явным образом.  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)   
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)