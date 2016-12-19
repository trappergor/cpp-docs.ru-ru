---
title: "Общая последовательность создания окна | Microsoft Docs"
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
  - "окна фрейма [C++], создание"
  - "последовательность [C++]"
  - "последовательность [C++], создание окна"
  - "окна [C++], создание"
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 8
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Общая последовательность создания окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании окна приложения, например дочернее окно платформа использует во многом так же, как процесс, описанный в [Создание документов и представлений](../mfc/document-view-creation.md).  
  
 Все классы, предоставляемые окна MFC используется [двухшаговое построения](../mfc/one-stage-and-two-stage-construction-of-objects.md).  То есть во время вызова оператора **новый** C\+\+ и выделяет конструктор инициализирует объект C\+\+, но не создает соответствующее поле Windows.  Это делается того, вызвав функцию\-член [Создать](../Topic/CWnd::Create.md) объекта окна.  
  
 Функцию\-член **Создать** выполняет окно Windows и сохраняет его `HWND` в члене данных [m\_hWnd](../Topic/CWnd::m_hWnd.md) открытых объектов C C\+\+.  **Создать** предоставляет полную гибкость по сравнению с параметрами создания.  Перед вызовом **Создать**, может потребоваться регистрация класса окна с глобальной функцией [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md), чтобы задать стили Значка и класса для кадра.  
  
 Для фреймовых windows можно использовать функцию\-член [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) вместо **Создать**.  `LoadFrame` результате окно Windows с помощью меньшее количество параметров.  Он получает многие значения по умолчанию из ресурсов, включая заголовок, Значок кадра, таблицы сочетаний клавиш и меню.  
  
> [!NOTE]
>  Значок, в таблице сочетаний клавиш и ресурсов меню должны иметь общее идентификатора ресурса, например **IDR\_MAINFRAME**, для них, который загружается LoadFrame.  
  
## Дополнительные сведения  
  
-   [Объекты окна](../mfc/window-objects.md)  
  
-   [Окно» регистрация «класс»](../mfc/registering-window-classes.md)  
  
-   [Уничтожения объектов окна](../mfc/destroying-window-objects.md)  
  
-   [Создание фреймы окна документа](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
## См. также  
 [Создание окон](../Topic/Creating%20Windows.md)