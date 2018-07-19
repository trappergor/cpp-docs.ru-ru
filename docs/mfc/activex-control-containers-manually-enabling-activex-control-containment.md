---
title: 'Контейнеры элементов управления ActiveX: Включение вложения элемента управления ActiveX вручную | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: fde0ee4dc740826c9efdf7b86cd2f021699f8820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339895"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>Контейнеры элементов управления ActiveX. Включение вложения элемента управления ActiveX вручную
Если при использовании мастера приложений MFC для создания приложения не была включена поддержка элементов управления ActiveX, необходимо вручную добавить такую поддержку. В этой статье описывается процесс вручную добавлять вложения элемента управления ActiveX в приложение контейнера OLE. Если заранее известно, что требуется поддержка элементов управления ActiveX в OLE-контейнер, см. в статье [создание контейнеров элементов управления MFC ActiveX](../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
> [!NOTE]
>  В этой статье используется на базе диалогового окна проекта элемента управления ActiveX контейнер с именем контейнера и внедренный элемент управления с именем Circ в качестве примеров в процедурах и кода.  
  
 Для поддержки элементов управления ActiveX, необходимо добавить одну строку кода для двух файлов проекта.  
  
-   Изменения в главном диалоговом окне `InitInstance` функции (находится в КОНТЕЙНЕРЕ. CPP) с помощью мастера приложений MFC вызова [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), как показано в следующем примере:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   Добавьте следующую строку STDAFX проекта. Файл заголовка:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 После завершения этих шагов заново постройте проект, щелкнув **построения** на **построения** меню.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

