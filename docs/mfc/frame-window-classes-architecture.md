---
title: Классы окна фрейма (архитектура)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: e3ae432c1adc881a5c67d6a6c292dc1f6a583ab3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441251"
---
# <a name="frame-window-classes-architecture"></a>Классы окна фрейма (архитектура)

В архитектуре "документ-представление" окна фрейма — это окна, содержащие окно представления. Они также поддерживают наличие прикрепленных к ним панелей управления.

В приложениях с многодокументным интерфейсом (MDI) основное окно является производным от `CMDIFrameWnd`. Он косвенно содержит кадры документов, которые являются `CMDIChildWnd` объектами. `CMDIChildWnd` объекты, в свою очередь, содержат представления документов.

В приложениях с одним документом (SDI) главное окно, производное от `CFrameWnd`, содержит представление текущего документа.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Базовый класс для основного окна фрейма приложения SDI. Кроме того, базовый класс для всех других классов окон фрейма.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Базовый класс для главного окна фрейма приложения MDI.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Базовый класс для окон фрейма документа приложения MDI.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Предоставляет окно фрейма для представления, когда серверный документ редактируется на месте.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
