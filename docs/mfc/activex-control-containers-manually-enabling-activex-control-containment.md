---
title: Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 94ad6e8356b5dab54ae97dbdd90812039d1425c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322067"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную

Если вы не поддерживали поддержку управления ActiveX при использовании MFC Application Wizard для создания приложения, вам придется добавлять эту поддержку вручную. В этой статье описывается процесс ручного добавления элемента управления ActiveX в существующее контейнерное приложение OLE. Если вы заранее знаете, что вам нужна поддержка управления ActiveX в контейнере OLE, смотрите статью [Создание контейнера управления MFC ActiveX.](../mfc/reference/creating-an-mfc-activex-control-container.md)

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

> [!NOTE]
> В этой статье в качестве примеров в процедурах и коде используется проект контейнера для управления ActiveX на основе диалога ActiveX под названием Container и встроенный элемент управления с именем Circ.

Для поддержки элементов управления ActiveX необходимо добавить одну строку кода к двум файлам проекта.

- Измените функцию основного `InitInstance` диалога (находится в CONTAINER. CPP) Мастером приложения MFC, который звонит в [AfxEnableControlContainer,](reference/ole-initialization.md#afxenablecontrolcontainer)как в следующем примере:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Добавьте следующее в STDAFX вашего проекта. H файл заголовка:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

После завершения этих шагов перестроить проект, нажав на меню **Build.** **Build**

## <a name="see-also"></a>См. также раздел

[Контейнеры управления ActiveX](../mfc/activex-control-containers.md)
