---
title: Контейнеры элементов управления ActiveX | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7d8a6498edf33bbf51fa9ab0de04d5d58ebd11a
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45534850"
---
# <a name="activex-control-containers"></a>Контейнеры для элементов управления ActiveX
Контейнер элементов управления ActiveX — это контейнер, который полностью поддерживает элементы управления ActiveX и можно внедрять их в свой собственный windows или диалоговые окна. Элемент управления ActiveX является элементом многократного использования программного обеспечения, который можно использовать во многих проектах разработки. Элементы управления позволяют пользователю приложения доступа к базам данных, отслеживать данные и различные нужные значения в приложениях. Дополнительные сведения для элементов управления ActiveX см. в статье [элементы ActiveX в MFC](../mfc/mfc-activex-controls.md).  

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения см. в разделе [элементы управления ActiveX](activex-controls.md).
  
 Обычно контейнеры элементов управления может иметь две формы в проекте:  
  
-   Диалоговые окна и диалоговое окно подобные windows как формы представления, где элемент управления ActiveX используется где-то в диалоговом окне.  
  
-   Windows в приложении, где используется элемент управления ActiveX в панели инструментов или другом месте, в окне «пользователь».  
  
 ActiveX, контейнер элементов управления взаимодействует с элементом управления с помощью предоставляемых [методы](../mfc/mfc-activex-controls-methods.md) и [свойства](../mfc/mfc-activex-controls-properties.md). Эти методы и свойства, которые можно просматривать и изменять контейнер элементов управления, осуществляется через класс-оболочку в контейнере проекта элемента управления ActiveX. Внедренный элемент управления ActiveX также можно взаимодействовать с контейнером, срабатывание (отправка) [события](../mfc/mfc-activex-controls-events.md) для уведомления контейнер, в котором произошло действие. Контейнер элементов управления можно выбрать для обработки этих уведомлений или нет.  
  
 Дополнительные статьи рассматриваются несколько тем: от создания проекта контейнера элемента управления ActiveX для реализации основных проблем, связанных с контейнеры элементов управления ActiveX, построенных с помощью Visual C++:  
  
-   [Создание контейнеров элементов ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Контейнеры для элементов ActiveX](../mfc/containers-for-activex-controls.md)  
  
-   [Контейнеры элементов ActiveX. Включение вложения элемента ActiveX вручную](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [Контейнеры элементов ActiveX. Вставка элемента управления в приложение контейнера элемента управления](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [Контейнеры элементов ActiveX. Соединение элемента ActiveX с переменной-членом](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [Контейнеры элементов ActiveX: Обработка событий из ActiveX управления](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [Контейнеры элементов ActiveX. Просмотр и изменение свойств элементов управления](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [Контейнеры элементов ActiveX. Программирование элементов ActiveX в контейнере элементов ActiveX](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [Контейнеры элементов ActiveX. Использование элементов управления в контейнере без диалоговых окон](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Дополнительные сведения об использовании элементов управления ActiveX в диалоговом окне см. в разделе [редактор диалоговых окон](../windows/dialog-editor.md) разделы.  
  
 Список статей, которые подробно описывается разработка элементов управления ActiveX, с помощью Visual C++ и классы элементов управления ActiveX в MFC, см. в разделе [элементы управления ActiveX в MFC](../mfc/mfc-activex-controls.md). Статьи группируются по функциональным категориям.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

