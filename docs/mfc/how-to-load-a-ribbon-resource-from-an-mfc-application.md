---
title: Практическое руководство. Загрузка ресурса ленты из приложения MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 14ba37952d6f8849c51b36901a6bc17404f938e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515158"
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

