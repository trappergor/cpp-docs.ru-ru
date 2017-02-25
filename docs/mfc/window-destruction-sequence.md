---
title: "Последовательность деструкции окна | Microsoft Docs"
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
  - "CWnd-объекты, последовательность уничтожения"
  - "уничтожение окон"
  - "уничтожение, окна"
  - "последовательность [C++]"
  - "последовательность [C++], уничтожение окна"
  - "окна [C++], уничтожение"
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Последовательность деструкции окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В платформе MFC, когда пользователь закрывает фреймовое окно, обработчик [OnClose](../Topic/CWnd::OnClose.md) окна по умолчанию вызывает метод [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  Последний функция\-член вызывается при уничтожении окна Windows [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), который выполняет определенную очистку, вызывает функцию\-член [По умолчанию](../Topic/CWnd::Default.md) для выполнения очистки Windows, и наконец вызывается виртуальной функции\-члена [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md).  Реализация [CFrameWnd](../mfc/reference/cframewnd-class.md)`PostNcDestroy` удаляет объект окна C C\+\+.  
  
## Дополнительные сведения  
  
-   [Выбор и отмена распределение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Окончательное удаление CWnd от родительского HWND](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
## См. также  
 [Уничтожение объектов окон](../mfc/destroying-window-objects.md)