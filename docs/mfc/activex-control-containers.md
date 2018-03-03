---
title: "Контейнеры элементов управления ActiveX | Документы Microsoft"
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
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee24d39c8769eaf2216ca4f64b9856b778a51ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers"></a>Контейнеры для элементов управления ActiveX
Контейнер элементов управления ActiveX — это контейнер, который полностью поддерживает элементы управления ActiveX и их можно включить в свой собственный windows или диалоговые окна. Элемент управления ActiveX — это повторно используемые программные элемент, который можно использовать во многих проектах разработки. Элементы управления позволяют пользователю приложения доступа к базам данных, мониторинг данных и выбора различных приложений. Дополнительные сведения для элементов управления ActiveX см. в статье [элементы управления MFC ActiveX](../mfc/mfc-activex-controls.md).  
  
 Контейнеры элементов управления, как правило, принимают две формы в проекте:  
  
-   Диалоговые окна и как диалоговое окно windows например представления, формы, где элемент управления ActiveX используется где-либо в диалоговом окне.  
  
-   Windows в приложении, где используется элемент управления ActiveX в панели инструментов или другое местоположение в окне «пользователь».  
  
 Предоставляемые ActiveX, контейнер элемента управления взаимодействует с элементом управления посредством [методы](../mfc/mfc-activex-controls-methods.md) и [свойства](../mfc/mfc-activex-controls-properties.md). Эти методы и свойства, которые могут использоваться и изменяться в качестве контейнера элемента управления, осуществляется через класс-оболочку в контейнере проекта элемента управления ActiveX. Внедренный элемент управления ActiveX также можно взаимодействовать с контейнером, срабатывание (отправка) [события](../mfc/mfc-activex-controls-events.md) известить контейнера, в котором произошло действие. Можно выбрать контейнер элемента управления обрабатывают эти уведомления или нет.  
  
 Дополнительные статьи рассматриваются несколько разделов, создав проект контейнера элемента управления ActiveX на базовую реализацию проблемы, связанные с контейнеры элементов управления ActiveX, созданных с помощью Visual C++:  
  
-   [Создание контейнеров элементов ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Контейнеры для элементов ActiveX](../mfc/containers-for-activex-controls.md)  
  
-   [Контейнеры элементов ActiveX. Включение вложения элемента ActiveX вручную](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [Контейнеры элементов ActiveX. Вставка элемента управления в приложение контейнера элемента управления](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [Контейнеры элементов ActiveX. Соединение элемента ActiveX с переменной-членом](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [Контейнеры элементов управления ActiveX: Обработка событий с версии ActiveX элемента управления](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [Контейнеры элементов ActiveX. Просмотр и изменение свойств элементов управления](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [Контейнеры элементов ActiveX. Программирование элементов ActiveX в контейнере элементов ActiveX](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [Контейнеры элементов ActiveX. Использование элементов управления в контейнере без диалоговых окон](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Дополнительные сведения об использовании элементов управления ActiveX в диалоговом окне см. в разделе [редактор диалоговых окон](../windows/dialog-editor.md) разделы.  
  
 Список статей, которые объясняют подробности о разработке элементов управления ActiveX, с помощью Visual C++ и классы элементов управления MFC ActiveX см. в разделе [элементы управления MFC ActiveX](../mfc/mfc-activex-controls.md). Статьи, сгруппированы по функциональным категориям.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

