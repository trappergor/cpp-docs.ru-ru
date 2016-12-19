---
title: "When Do I Need to Call AtlAxWinInit? | Microsoft Docs"
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
  - "AtlAxWinInit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinInit method"
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinInit?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinInit](../Topic/AtlAxWinInit.md) регистрирует класс окна **"AtlAxWin80"** \(плюс несколько пользовательских сообщений окна\), поэтому эту функцию следует вызывать перед попыткой создания окна основного приложения.  Однако не всегда необходимо явно вызывать эту функцию, поскольку API размещения \(и классы, которые их используют\) часто вызывают эту функцию автоматически.  В этой функции нет вред вызывать несколько раз.  Дополнительные сведения см. в разделе [API Размещения, что Элемент управления\- библиотеки ATL?](../atl/what-is-the-atl-control-hosting-api-q.md).  
  
## См. также  
 [When Do I Need to Call AtlAxWinTerm?](../atl/when-do-i-need-to-call-atlaxwinterm-q.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)