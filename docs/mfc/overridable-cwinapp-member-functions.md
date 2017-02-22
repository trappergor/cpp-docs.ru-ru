---
title: "Переопределяемые функции-члены CWinApp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application - класс"
  - "CWinApp - класс, переопределяемый"
  - "переопределение, переопределяемые функции в CWinApp"
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Переопределяемые функции-члены CWinApp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько ключевых функции\-члены переопределяемого метода \(`CWinApp` переопределяет эти члены от класса [CWinThread](../mfc/reference/cwinthread-class.md), из которого `CWinApp` вывода\):  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [Запуск](../Topic/Run%20Member%20Function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [OnIdle](../mfc/onidle-member-function.md)  
  
 Единственным функцию\-член `CWinApp`, необходимо переопределить `InitInstance`.  
  
## См. также  
 [CWinApp: класс приложений](../Topic/CWinApp:%20The%20Application%20Class.md)