---
title: 'Контейнеры элементов ActiveX: Включение вложения элемента управления ActiveX вручную | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 845ad544b83f3f73c31eebd00218945c6028a622
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45534980"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную
Если не была включена поддержка элементов управления ActiveX, при использовании мастера приложений MFC для создания приложения, необходимо вручную добавить поддержку этих функций. В этой статье описывается процесс для вручную добавлять вложения элемента управления ActiveX в приложение контейнера OLE. Если заранее известно, что требуется поддержка элементов управления ActiveX в OLE-контейнер, ознакомьтесь со статьей [создание контейнеров элементов управления MFC ActiveX](../mfc/reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, которые следуют за ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).  
  
> [!NOTE]
>  В этой статье используется на базе диалогового окна проекта элемента управления ActiveX контейнер с именем контейнера и внедренный элемент управления с именем Кр в качестве примеров в процедурах и кода.  
  
 Для поддержки элементов управления ActiveX, необходимо добавить одну строку кода до двух файлов проекта.  
  
-   Изменения в главном диалоговом окне `InitInstance` функция (находится в КОНТЕЙНЕРЕ. CPP) с помощью мастера приложений MFC, делая вызов к [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), как показано в следующем примере:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   Добавьте следующий код STDAFX проекта. Файл заголовка:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 После завершения этих действий, перестройте проект, нажав кнопку **построения** на **построения** меню.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

