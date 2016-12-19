---
title: "Уничтожение объектов окон | Microsoft Docs"
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
  - "окна фрейма, уничтожение"
  - "объекты окон, удаление"
  - "объекты окон, уничтожение"
  - "объекты окон, удаление"
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Уничтожение объектов окон
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Необходимо соблюдать осторожность собственными дочерними окнами для удаления объекта окна C\+\+, когда пользователь завершил работу с окном.  Если эти объекты не удаляется, приложение не возьмет их память.  Удачно, среда управляет уничтожение, так и создание окна для фреймовых окон, представлений и диалоговых окон.  При создании дополнительных окна, то ответственность за удалить их.  
  
## Дополнительные сведения  
  
-   [Последовательность уничтожении окна](../mfc/window-destruction-sequence.md)  
  
-   [Выбор и отмена распределение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Окончательное удаление CWnd от родительского HWND](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
-   [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)  
  
-   [Уничтожения фреймовые окна](../mfc/destroying-frame-windows.md)  
  
## См. также  
 [Объекты окон](../mfc/window-objects.md)