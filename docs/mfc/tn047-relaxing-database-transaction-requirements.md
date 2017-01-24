---
title: "TN047. Уменьшение требований к транзакциям баз данных | Microsoft Docs"
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
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN047"
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN047. Уменьшение требований к транзакциям баз данных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обратите внимание, что эта техника обсудила требования к транзакции классов MFC базы данных ODBC, теперь является устаревшим.  Перед MFC 4.2, классы базы данных требуют, чтобы курсоры были сохранены в наборах записей после операции **CommitTrans** или **Откат**.  Если драйвер ODBC и СУБД не поддерживает этот уровень сохранение курсора, классы базы данных не включено транзакции.  
  
 Начиная с версии MFC 4.2, классы базы данных ослабляли ограничение для хранения курсора.  Транзакции будут включены, если драйвер поддерживает их.  Однако теперь необходимо проверить результат операции **CommitTrans** или **Откат** на общих наборах записей.  В разделе функций\-членов [CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md) и [CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md) для получения дополнительных сведений.  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)