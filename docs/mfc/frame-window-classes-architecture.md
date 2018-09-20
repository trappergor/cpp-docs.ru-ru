---
title: Классы окон (архитектура) кадра | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 117554b2c34853aa166c12d80b4821d3721e5992
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394131"
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

