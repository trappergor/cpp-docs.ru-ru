---
title: Классы окна фрейма (архитектура)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 483112d197b7c7211989ecda8b774deb9f30d49e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624596"
---
# <a name="frame-window-classes-architecture"></a>Классы окна фрейма (архитектура)

В архитектуре "документ-представление" окна фрейма — это окна, содержащие окно представления. Они также поддерживают наличие прикрепленных к ним панелей управления.

В приложениях с многодокументным интерфейсом (MDI) основное окно является производным от `CMDIFrameWnd` . Он косвенно содержит кадры документов, которые являются `CMDIChildWnd` объектами. `CMDIChildWnd`Объекты, в свою очередь, содержат представления документов.

В приложениях с одним документом (SDI) главное окно, производное от `CFrameWnd` , содержит представление текущего документа.

[CFrameWnd](reference/cframewnd-class.md)<br/>
Базовый класс для основного окна фрейма приложения SDI. Кроме того, базовый класс для всех других классов окон фрейма.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
Базовый класс для главного окна фрейма приложения MDI.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
Базовый класс для окон фрейма документа приложения MDI.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Предоставляет окно фрейма для представления, когда серверный документ редактируется на месте.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
