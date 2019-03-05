---
title: Классы окна фрейма (архитектура)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: affa217f481cc6d9e125d526f1b97be9120e0990
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298013"
---
# <a name="frame-window-classes-architecture"></a>Классы окна фрейма (архитектура)

В архитектуре документ/представление окна фрейма, windows, которые содержат в окно представления. Они также поддерживают того, элемент управления панели, присоединенными к ним.

В нескольких приложениях интерфейса (MDI) документа, главное окно является производным от `CMDIFrameWnd`. Оно косвенно содержит кадры документов, которые являются `CMDIChildWnd` объектов. `CMDIChildWnd` Объекты, в свою очередь, содержат представлений документов.

В один документ приложения с интерфейсом (SDI), главного окна, производным от `CFrameWnd`, содержащей представление текущего документа.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Базовый класс для окна главного фрейма приложения SDI. Кроме того базовый класс для всех других классы окна фрейма.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Базовый класс для окна главного фрейма приложения MDI.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Базовый класс для окна фрейма документа MDI-приложения.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Предоставляет окна фрейма для представления, при редактировании серверного документа в месте.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
