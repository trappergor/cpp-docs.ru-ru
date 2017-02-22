---
title: "Контейнеры для элементов управления ActiveX | Microsoft Docs"
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
  - "контейнер для элементов ActiveX [C++]"
  - "элементы управления OLE [C++], контейнеры"
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Контейнеры для элементов управления ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Контейнер элементов управления ActiveX контейнер, полностью поддерживает элементы управления ActiveX и может включать их в собственные окна и диалоговые окна.  Элемент управления ActiveX повторно элемент программного обеспечения, можно использовать во многих разрабатываемых проектах.  Элементы управления позволяют пользователю приложения к базам данных access, отслеживающих данные, а также различные выделения внутри приложений.  Дополнительные сведения об элементах управления ActiveX см. в статье [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md).  
  
 Контейнеры элементов управления обычно занимают 2 формы проекта:  
  
-   Отображаемые диалоговые окна и окна, например похожие на диалог представления формы, где элемент управления ActiveX используется где\-либо в диалоговом окне.  
  
-   В приложении Windows, где элемент управления ActiveX используется в панели инструментов, или в другом месте в окне пользователя.  
  
 Контейнер элементов управления ActiveX взаимодействует с элементом управления предоставляется через [методы](../mfc/mfc-activex-controls-methods.md) и [свойства](../mfc/mfc-activex-controls-properties.md).  Эти методы и свойства, которые доступны и изменяются контейнером элементов управления, доступных через этот класс\-оболочку в проекте контейнера элементов управления ActiveX.  Внедренный элемент управления ActiveX также может взаимодействовать с контейнером, происходит отправка \( [события](../mfc/mfc-activex-controls-events.md) \), чтобы убедиться, что контейнер выполнения действия.  Контейнер элементов управления может выбрать действовать от этих уведомлений или нет.  
  
 Дополнительные статьи, посвященные несколько разделов, создание проекта из контейнера элементов управления ActiveX в соответствующие базовым проблем реализации в построение контейнерам элемент управления ActiveX с Visual C\+\+:  
  
-   [Создание контейнера элемента управления ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Контейнеры элементов управления ActiveX](../Topic/Containers%20for%20ActiveX%20Controls.md)  
  
-   [Контейнеры элементов управления ActiveX. Включение вручную контейнер элементов управления ActiveX](../Topic/ActiveX%20Control%20Containers:%20Manually%20Enabling%20ActiveX%20Control%20Containment.md)  
  
-   [Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элементов управления](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [Контейнеры элементов управления ActiveX. Подключение элемента управления ActiveX в переменные\-члену](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [Контейнеры элементов управления ActiveX. Обработка событий из элементов управления ActiveX](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [Контейнеры элементов управления ActiveX. Просмотр и изменение свойств элемента управления](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [Контейнеры элементов управления ActiveX. Программирование элементов управления ActiveX в контейнере элементов управления ActiveX](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере, диалогового окна](../Topic/ActiveX%20Control%20Containers:%20Using%20Controls%20in%20a%20Non-Dialog%20Container.md)  
  
 Дополнительные сведения о с помощью элементов управления ActiveX в диалоговом окне см. в разделах [Редактор диалоговых окон](../mfc/dialog-editor.md).  
  
 Статьи Для списка, содержащие сведения о разработке элементов управления ActiveX с использованием Visual C\+\+ классы элементов управления ActiveX MFC см. в разделе [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md).  Статьи группированы функциональными по категориям.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)