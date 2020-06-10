---
title: Контейнеры для элементов управления ActiveX
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
ms.openlocfilehash: 42fa18c41ebd960aa8de080df00556ad5c909d40
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620755"
---
# <a name="activex-control-containers"></a>Контейнеры для элементов управления ActiveX

Контейнер элементов управления ActiveX — это контейнер, который полностью поддерживает элементы управления ActiveX и может включать их в свои окна или диалоговые окна. Элемент управления ActiveX — это многократно используемый программный элемент, который можно использовать во многих проектах разработки. Элементы управления позволяют пользователю приложения получать доступ к базам данных, отслеживать данные и выбирать различные варианты выбора в приложениях. Дополнительные сведения об элементах управления ActiveX см. в статье [элементы управления](mfc-activex-controls.md)ActiveX в MFC.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения см. в разделе [элементы управления ActiveX](activex-controls.md).

Контейнеры элементов управления обычно принимают две формы в проекте:

- Диалоговые окна и диалоговые окна, такие как представления форм, в которых в диалоговом окне используется элемент управления ActiveX.

- Windows в приложении, где элемент управления ActiveX используется на панели инструментов или в другом расположении в окне пользователя.

Контейнер элементов управления ActiveX взаимодействует с элементом управления через предоставляемые [методы](mfc-activex-controls-methods.md) и [свойства](mfc-activex-controls-properties.md). Доступ к этим методам и свойствам, которые могут быть доступны и изменены контейнером элементов управления, осуществляется через класс-оболочку в проекте контейнера элементов управления ActiveX. Внедренный элемент управления ActiveX также может взаимодействовать с контейнером путем срабатывания [событий](mfc-activex-controls-events.md) (отправки) для уведомления контейнера о том, что произошло действие. Контейнер элемента управления может использовать эти уведомления или нет.

В дополнительных статьях рассматриваются некоторые темы: Создание проекта контейнера элементов управления ActiveX с основными проблемами реализации, связанными с контейнерами элементов управления ActiveX, созданными с помощью Visual C++:

- [Создание контейнеров элементов управления MFC ActiveX](reference/creating-an-mfc-activex-control-container.md)

- [Контейнеры для элементов ActiveX](containers-for-activex-controls.md)

- [Контейнеры элементов ActiveX. Включение вложения элемента ActiveX вручную](activex-control-containers-manually-enabling-activex-control-containment.md)

- [Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления](inserting-a-control-into-a-control-container-application.md)

- [Контейнеры элементов ActiveX. Соединение элемента ActiveX с переменной-членом](activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [Контейнеры элементов управления ActiveX. Обработка событий из элемента управления ActiveX](activex-control-containers-handling-events-from-an-activex-control.md)

- [Контейнеры элементов управления ActiveX. Просмотр и изменение свойств элементов управления](activex-control-containers-viewing-and-modifying-control-properties.md)

- [Контейнеры элементов ActiveX. Программирование элементов ActiveX в контейнере элементов ActiveX](programming-activex-controls-in-a-activex-control-container.md)

- [Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере без диалоговых окон](activex-control-containers-using-controls-in-a-non-dialog-container.md)

Дополнительные сведения об использовании элементов управления ActiveX в диалоговом окне см. в разделах [редактора диалоговых окон](../windows/dialog-editor.md) .

Список статей, в которых объясняются сведения о разработке элементов управления ActiveX с помощью Visual C++ и классов элементов ActiveX MFC, см. в разделе [элементы управления ActiveX в MFC](mfc-activex-controls.md). Статьи группируются по функциональным категориям.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)
