---
title: Контейнеры элементов ActiveX. Включение вложения элемента управления ActiveX вручную
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 80ca25192f3dbda711b0398917cfa68571cd2c55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394940"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>Контейнеры элементов ActiveX. Включение вложения элемента управления ActiveX вручную

Если не была включена поддержка элементов управления ActiveX, при использовании мастера приложений MFC для создания приложения, необходимо вручную добавить поддержку этих функций. В этой статье описывается процесс для вручную добавлять вложения элемента управления ActiveX в приложение контейнера OLE. Если заранее известно, что требуется поддержка элементов управления ActiveX в OLE-контейнер, ознакомьтесь со статьей [создание контейнеров элементов управления MFC ActiveX](../mfc/reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

> [!NOTE]
>  В этой статье используется на базе диалогового окна проекта элемента управления ActiveX контейнер с именем контейнера и внедренный элемент управления с именем Кр в качестве примеров в процедурах и кода.

Для поддержки элементов управления ActiveX, необходимо добавить одну строку кода до двух файлов проекта.

- Изменения в главном диалоговом окне `InitInstance` функция (находится в КОНТЕЙНЕРЕ. CPP) с помощью мастера приложений MFC, делая вызов к [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), как показано в следующем примере:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Добавьте следующий код STDAFX проекта. Файл заголовка:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

После завершения этих действий, перестройте проект, нажав кнопку **построения** на **построения** меню.

## <a name="see-also"></a>См. также

[Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)
