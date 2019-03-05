---
title: Практическое руководство. Загрузка ресурса ленты из приложения MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: b7691d4168101209b0e2d2500012a2b4a8e47788
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289563"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Практическое руководство. Загрузка ресурса ленты из приложения MFC

Чтобы использовать ресурс ленты в приложении, измените приложение, чтобы загрузить ресурс ленты.

### <a name="to-load-a-ribbon-resource"></a>Для загрузки в ресурс ленты

1. Объявите `Ribbon Control` объекта в `CMainFrame` класса.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. В `CMainFrame::OnCreate`, создать и инициализировать элемент управления на ленте.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>См. также

[Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)
