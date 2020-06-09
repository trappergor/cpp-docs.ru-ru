---
title: Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: a8092a77020695163ce4fbacf7eeea2650ae9f86
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625106"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную

Если вы не включили поддержку элементов управления ActiveX при использовании мастера приложений MFC для создания приложения, вам потребуется добавить эту поддержку вручную. В этой статье описывается процесс добавления элемента управления ActiveX в существующее приложение контейнера OLE вручную. Если вы заранее знакомы с поддержкой элементов управления ActiveX в контейнере OLE, см. статью [Создание контейнера элементов управления ACTIVEX MFC](reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения о современных технологиях, которые заменяют ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

> [!NOTE]
> В этой статье используется проект контейнера элемента управления ActiveX с именем container и внедренный элемент управления с именем Circ в качестве примеров в процедурах и коде.

Для поддержки элементов управления ActiveX необходимо добавить одну строку кода в два файла проекта.

- Измените функцию главного диалогового окна `InitInstance` (находится в контейнере. CPP) с помощью мастера приложений MFC, выполняющего вызов [афксенаблеконтролконтаинер](reference/ole-initialization.md#afxenablecontrolcontainer), как показано в следующем примере:

   [!code-cpp[NVC_MFCOleContainer#34](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Добавьте следующий фрагмент в файл STDAFX проекта. Файл заголовка H:

   [!code-cpp[NVC_MFCOleContainer#36](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

После выполнения этих действий перестройте проект, щелкнув **Сборка** в меню **Сборка** .

## <a name="see-also"></a>См. также раздел

[Контейнеры элементов управления ActiveX](activex-control-containers.md)
