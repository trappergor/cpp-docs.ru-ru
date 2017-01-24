---
title: "Windows | Microsoft Docs"
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
  - "MFC [C++], окна"
  - "объекты [C++], окно"
  - "объекты окон [С++], Платформа MFC"
  - "окна [C++]"
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это семейство статей охватывает объекты окна в платформе MFC.  Все окна MFC являются производными от класса [CWnd](../Topic/CWnd%20Class.md), включая фреймовые окна, представления, диалоговые окна и элементы управления.  
  
 Первая команда в составе статьи описаны в [объекты окна](../mfc/window-objects.md).  В разделе эта команда общие сведения об объектах окна C\+\+, как они инкапсулируют HWND и как они используются для создания собственных окна, как дочерние окна.  
  
 Вторая группа в составе статьи [фреймовые окна](../mfc/frame-windows.md)— окна описывает, что кадр вокруг содержимого — в частности.  Эта команда см. сведения о способах платформы MFC управляет фреймовые окна и содержимое, они кадр, включая панели элементов управления и представления.  
  
## Дополнительные сведения  
 *Разделы для объектов окна обычно*  
  
-   [Объекты окна](../mfc/window-objects.md)  
  
-   [Связь между объектами окна C\+\+ дескрипторами HWND.](../Topic/Relationship%20Between%20a%20C++%20Window%20Object%20and%20an%20HWND.md)  
  
-   [Производные классы окна](../Topic/Derived%20Window%20Classes.md)  
  
-   [Создание объектов окна](../Topic/Creating%20Windows.md)  
  
-   [Уничтожения объектов окна](../mfc/destroying-window-objects.md)  
  
-   [Окно» регистрация «класс»](../mfc/registering-window-classes.md)  
  
-   [Работа с объектами окна](../Topic/Working%20with%20Window%20Objects.md)  
  
-   [Контексты устройств](../Topic/Device%20Contexts.md): объекты, которые позволяют создавать Windows является независимым  
  
-   [Графические объекты](../mfc/graphic-objects.md): перья, кисти шрифты, растровые изображения палитры, области  
  
 *Разделы фреймового окна*  
  
-   [Фреймовые окна](../mfc/frame-windows.md): объекты окна, которые предоставляют фреймы  
  
-   [Фреймовые окна и представления](../mfc/frame-windows.md)  
  
-   [Классы фреймового окна](../mfc/frame-window-classes.md)  
  
-   [Стили фреймового окна](../Topic/Frame-Window%20Styles%20\(C++\).md)  
  
-   [Изменение стилей окна создание MFC](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)  
  
-   [Какие фреймовые окна делают](../mfc/what-frame-windows-do.md)  
  
-   [С помощью фреймовые окна](../Topic/Using%20Frame%20Windows.md)  
  
-   [Окно MD\/Child \(окно MDICLIENT\)](../mfc/managing-mdi-child-windows.md)  
  
-   [Элемент управления меню, панели элементов управления и сочетания клавиш](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [Использование представления](../mfc/using-views.md)  
  
-   [Типы многооконного, представления и фреймовые окна \(окна\-разделители\)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Сообщения \(сопоставления и функции обработчика\)](../mfc/messages.md)  
  
 *Создание и уничтожить Windows*  
  
-   [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)  
  
-   [Удалите объекты окна](../mfc/destroying-window-objects.md)  
  
-   [Создайте фреймы окна документа](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
-   [Удалите фреймовые окна](../mfc/destroying-frame-windows.md)  
  
 *Создайте окна\-разделители*  
  
-   [Создайте окна\-разделители](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *Управление дочерние окна и текущее представление*  
  
-   [Управление дочерние окна MDI](../mfc/managing-mdi-child-windows.md)  
  
-   [Управление текущее представление](../mfc/managing-the-current-view.md)  
  
-   [Элемент управления меню, панели элементов управления и сочетания клавиш](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *Работа с контекстами устройств и окна " управление стилями "*  
  
-   [Используйте перья и другие графические объекты в контексте устройства](../mfc/graphic-objects.md)  
  
-   [Изменение стилей окна с MFC](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)  
  
## См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Панели инструментов](../mfc/toolbars.md)   
 [Строки состояния](../mfc/status-bars.md)   
 [Диалоговые панели](../mfc/dialog-bars.md)