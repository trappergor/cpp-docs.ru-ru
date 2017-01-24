---
title: "Уничтожение окон фрейма | Microsoft Docs"
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
  - "PostNcDestroy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Default - метод"
  - "уничтожение окон фрейма"
  - "DestroyWindow - метод"
  - "окна фрейма документа, уничтожение"
  - "окна фрейма [C++], уничтожение"
  - "MFC [C++], окна фрейма"
  - "OnClose - метод"
  - "OnNcDestroy - метод, и окна фрейма"
  - "PostNcDestroy - метод"
  - "окна [C++], уничтожение"
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Уничтожение окон фрейма
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Управляет уничтожение платформы MFC, так и создание окна для этих окон, связанных с документами и представлениями платформы.  При создании дополнительных окна, то ответственность за удалить их.  
  
 В платформе, когда пользователь закрывает фреймовое окно, обработчик [OnClose](../Topic/CWnd::OnClose.md) окна по умолчанию вызывает метод [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  Последний функция\-член вызывается при уничтожении окна Windows [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), который выполняет определенную очистку, вызывает функцию\-член [По умолчанию](../Topic/CWnd::Default.md) для выполнения очистки Windows, и наконец вызывается виртуальной функции\-члена [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md).  Реализация [CFrameWnd](../mfc/reference/cframewnd-class.md)`PostNcDestroy` удаляет объект окна C C\+\+.  Никогда не следует использовать оператор **удалить** C фреймовом C\+\+ в окне.  Взамен рекомендуется использовать `DestroyWindow`.  
  
 Если главного окна закрывает, приложение закрывает.  Если измененные несохраненные документы, платформа показывает окно сообщения для запроса, если документы должны сохраняются и гарантирует, что соответствующие документы сохраняются при необходимости.  
  
## Дополнительные сведения  
  
-   [Создание фреймы окна документа](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
## См. также  
 [Использование окон фрейма](../Topic/Using%20Frame%20Windows.md)