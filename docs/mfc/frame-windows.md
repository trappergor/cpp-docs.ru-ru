---
title: "Окна фрейма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 14dabd345f47b064f78a4e9a3dede834bddeb9d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="frame-windows"></a>Окна фрейма
Если приложение выполняется под управлением Windows, пользователь взаимодействует с документов, которые отображаются в окнах фрейма. Окно фрейма документа состоит из двух основных компонентов: фрейма и содержимое, он кадры. Окно фрейма документа может быть [однооконный интерфейс](../mfc/sdi-and-mdi.md) окна фрейма (SDI) или [многодокументного интерфейса](../mfc/sdi-and-mdi.md) дочернее окно (MDI). Windows управляет большей частью взаимодействие пользователя с окном фрейма: перемещение и изменение размеров окна и что сводит к минимуму и закрытие его увеличения. Управление содержимое внутри рамки.  
  
## <a name="frame-windows-and-views"></a>Окна фрейма и представления  
 Платформа MFC использует фреймов для содержат представления. Эти два компонента — страницы и содержимое, представляются и управляется два различных классов в MFC. Класс окна фрейма управляет рамки, а класс представления управляет содержимое. В окне представления является дочерним для окна фрейма. Рисование и других взаимодействия с пользователем в документе выполняются в клиентской области представления, не клиентской области окна фрейма. Окна фрейма предоставляет видимой рамку вокруг представление строки заголовка и стандартное окно элементы управления, такие как элемент управления меню, кнопки, чтобы свернуть или развернуть окно и управляет для изменения размера окна. «Содержимое» состоит из клиентской области окна, которой полностью занятую дочернее окно — представление. На следующем рисунке показана связь между окно фрейма и представления.  
  
 ![Представление окна фрейма](../mfc/media/vc37fx1.gif "vc37fx1")  
Окна фрейма и представления  
  
## <a name="frame-windows-and-splitter-windows"></a>Окна фрейма и окна разделителей  
 Другой общий подход является фрейм окна фрейма несколько представлений, обычно с помощью [окна-разделителя](../mfc/multiple-document-types-views-and-frame-windows.md). В окне разделителя клиентской области окна фрейма занятую окна-разделителя, который в свою очередь имеет несколько дочерних окон, панелей, которые являются представления вызывается.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
 **Окна фрейма общие разделы**  
  
-   [Объекты окон](../mfc/window-objects.md)  
  
-   [Классы окна фрейма](../mfc/frame-window-classes.md)  
  
-   [Классы окна фрейма, созданные с помощью мастера приложений](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
-   [Окон фрейма](../mfc/what-frame-windows-do.md)  
  
 **Разделы об использовании окна фрейма**  
  
-   [Использование окон фрейма](../mfc/using-frame-windows.md)  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
-   [Уничтожение окон фрейма](../mfc/destroying-frame-windows.md)  
  
-   [Управление дочерними окнами MDI](../mfc/managing-mdi-child-windows.md)  
  
-   [Управление текущим представлением](../mfc/managing-the-current-view.md) в окне фрейма, который содержит несколько представлений  
  
-   [Управление меню, панелей элементов управления и ускорителями (другие объекты, которые совместно используют пространство фрейм окна)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **Разделы по возможности специальные фрейм окна**  
  
-   [Перетаскивание файлов](../mfc/dragging-and-dropping-files-in-a-frame-window.md) из проводника или диспетчера файлов в окне фрейма  
  
-   [Реакция на динамический обмен данными (DDE)](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [Полумодальные состояния: контекстно-зависимые справки Windows (Оркестрация других действий окна)](../mfc/orchestrating-other-window-actions.md)  
  
-   [Полумодальные состояния: печать и предварительный просмотр (Оркестрация других действий окна)](../mfc/orchestrating-other-window-actions.md)  
  
 **Щелкните ссылку на другие типы окон**  
  
-   [Использование представлений](../mfc/using-views.md)  
  
-   [Диалоговые окна](../mfc/dialog-boxes.md)  
  
-   [Элементы управления](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Windows](../mfc/windows.md)

