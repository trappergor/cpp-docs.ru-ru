---
title: 'Практическое: загрузка ресурса ленты из приложения MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1643989a96a9003847fb53de624bff12cd51cd88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434300"
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

