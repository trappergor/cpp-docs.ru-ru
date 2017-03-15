---
title: "Необходимо ли создавать новые классы как производные от CObject? | Microsoft Docs"
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
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject - класс, условия использования"
  - "производные классы, из CObject"
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Необходимо ли создавать новые классы как производные от CObject?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Нет, не требуется.  
  
 Унаследуйте класс от [CObject](../Topic/CObject%20Class.md), если требуются он предоставляет средства, такие как сериализация или динамическое creatability.  Многие классы данных для сериализации в файлы, поэтому часто хорошей практикой является производной от `CObject`.  Пример класс, производный от `CObject` см. в разделе [Образец Scribble](../top/visual-cpp-samples.md).  
  
## См. также  
 [Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)