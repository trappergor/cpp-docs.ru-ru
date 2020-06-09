---
title: Классы окна фрейма (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 1c0a1e1e93433e0fbe07c11eb350216173e74d84
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625843"
---
# <a name="frame-window-classes-windows"></a>Классы окна фрейма (Windows)

Окна фрейма — это окна, которые обрабатывают приложение или часть приложения. Окна фрейма обычно содержат другие окна, такие как представления, панели инструментов и строки состояния. В случае `CMDIFrameWnd` они могут содержать `CMDIChildWnd` объекты с непрямыми пределами.

[CFrameWnd](reference/cframewnd-class.md)<br/>
Базовый класс для основного окна фрейма приложения SDI. Кроме того, базовый класс для всех других классов окон фрейма.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
Базовый класс для главного окна фрейма приложения MDI.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
Базовый класс для окон фрейма документа приложения MDI.

[CMiniFrameWnd](reference/cminiframewnd-class.md)<br/>
Оконная рамка половинной высоты, обычно отображаемая вокруг плавающих панелей инструментов.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Предоставляет окно фрейма для представления, когда серверный документ редактируется на месте.

## <a name="related-class"></a>Связанный класс

Класс `CMenu` предоставляет интерфейс, с помощью которого можно получить доступ к меню приложения. Это полезно для динамического манипулирования меню во время выполнения. Например, при добавлении или удалении пунктов меню в соответствии с контекстом. Хотя меню чаще всего используются с окнами фрейма, их также можно использовать с диалоговыми окнами и другими дочерними окнами.

[CMenu](reference/cmenu-class.md)<br/>
Инкапсулирует `HMENU` маркер в строку меню приложения и всплывающие меню.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
