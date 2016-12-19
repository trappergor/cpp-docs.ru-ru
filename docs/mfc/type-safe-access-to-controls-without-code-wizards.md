---
title: "Типобезопасный доступ к элементам управления без мастеров кода | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления диалогового окна, доступ"
  - "диалоговые окна, доступ к элементам управления"
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Типобезопасный доступ к элементам управления без мастеров кода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Первый подход к созданию типобезопасный доступ к элементам управления использует встроенный функции\-члена, чтобы привести возвращаемый тип функции\-члена `CWnd``GetDlgItem` класса к соответствующему типу элемента управления C\+\+, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Можно использовать данный функцию\-член к элементу управления в типобезопасном способом с кодом примерно следующим образом:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## См. также  
 [Типобезопасный доступ к элементам управления в диалоговом окне](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)   
 [Типобезопасный доступ к элементам управления с использованием мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)