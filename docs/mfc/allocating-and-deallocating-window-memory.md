---
title: "Выделение и освобождение памяти окна | Microsoft Docs"
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
  - "выделение памяти, объекты окон"
  - "освобождение памяти"
  - "освобождение памяти, память окон"
  - "хранение для объектов окна"
  - "хранение для объектов окна, выделение"
  - "объекты окон, выделение памяти для"
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Выделение и освобождение памяти окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Не используйте оператор **удалить** C\+\+ для удаления фреймовое окно или представление.  Вместо этого вызовите функцию\-член `DestroyWindow``CWnd`.  Фреймовые окна, поэтому должны быть созданы в куче с помощью оператора **новый**.  Тщательно подбирайте фреймовые окна в кадре стека или глобально.  Другие окна должны быть созданы в кадре стека, когда это возможно.  
  
## Дополнительные сведения  
  
-   [Создание окна](../Topic/Creating%20Windows.md)  
  
-   [Последовательность уничтожении окна](../mfc/window-destruction-sequence.md)  
  
-   [Окончательное удаление CWnd от родительского HWND](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
## См. также  
 [Уничтожение объектов окон](../mfc/destroying-window-objects.md)