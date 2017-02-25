---
title: "Реализация строки состояния в MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COldStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COldStatusBar - класс"
  - "CStatusBar - класс, и класс CStatusBarCtrl"
  - "CStatusBar - класс, и строки состояния MFC"
  - "CStatusBarCtrl - класс, и класс CStatusBar"
  - "CStatusBarCtrl - класс, и строки состояния MFC"
  - "строки состояния, и класс CStatusBarCtrl"
  - "строки состояния, обратная совместимость"
  - "строки состояния, реализация в MFC"
  - "строки состояния, старый с классом COldStatusBar"
  - "строки состояния, реализация Windows 95"
  - "индикаторы статуса"
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Реализация строки состояния в MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объект [CStatusBar](../mfc/reference/cstatusbar-class.md) панель элементов управления со строкой областей текстового вывода.  Области вывода часто используются как линии сообщения и как индикаторы состояния.  Примеры включают линии справка\- сообщения меню, краткое описание выбранной команду меню и индикаторы, в которой отображается состояние SCROLL LOCK, NUM LOCK и других ключей.  
  
 Начиная с версии MFC 4.0, строки состояния реализованы с помощью класса [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), который инкапсулирует общий элемент управления строки состояния.  Для обеспечения обратной совместимости MFC сохраняет старую реализация строки состояния в классе **COldStatusBar**.  Документация для более ранних версий MFC описание **COldStatusBar** в `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md) вызывается функция\-член новый с MFC 4.0, позволяющий использует поддержку общего элемента управления Windows для настройки строки состояния, а также дополнительные функции.  функции\-члены `CStatusBar` ведут себя большинство функций общих элементов управления Windows; однако при вызове `GetStatusBarCtrl`, можно задать для строки состояния даже несколько характеристик строки состояния.  При вызове `GetStatusBarCtrl`, оно возвращает ссылку на объект `CStatusBarCtrl`.  Можно использовать, — для управления элемент управления в строке состояния.  
  
 На следующем рисунке показана строка состояния, отображающую несколько индикаторов.  
  
 ![Строка состояния](../mfc/media/vc37dy1.png "vc37DY1")  
Строка состояния  
  
 Как и панель инструментов, объект строки состояния внедряется в текущем родительском окне фреймовом и создается автоматически при построении фреймовое окно.  Строка состояния, как и другие панели элементов управления, разрушена также автоматически, когда родительский кадр уничтожается.  
  
## Дополнительные сведения  
  
-   [Обновление текст области строки состояния](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   Классы [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) библиотеки MFC  
  
-   [Панели элементов управления](../Topic/Control%20Bars.md)  
  
-   [Диалоговые панели](../mfc/dialog-bars.md)  
  
-   [Панели инструментов \(реализация панели инструментов MFC\)](../mfc/mfc-toolbar-implementation.md)  
  
## См. также  
 [Строки состояния](../mfc/status-bars.md)