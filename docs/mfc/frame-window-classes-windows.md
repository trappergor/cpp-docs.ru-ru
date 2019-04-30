---
title: Классы окна фрейма (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 3e56bd0f449992118db75a44c39b6e0e15cb0d86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392797"
---
# <a name="frame-window-classes-windows"></a>Классы окна фрейма (Windows)

Окна фрейма — это окна, которые кадров приложения или его части приложения. Окна фрейма обычно содержат другие окна, например представлений, панелей инструментов и строки состояния. В случае использования `CMDIFrameWnd`, они могут содержать `CMDIChildWnd` косвенно объектов.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Базовый класс для окна главного фрейма приложения SDI. Кроме того базовый класс для всех других классы окна фрейма.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Базовый класс для окна главного фрейма приложения MDI.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Базовый класс для окна фрейма документа MDI-приложения.

[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)<br/>
Окна фрейма половинной высоты, отображается на плавающих панелей инструментов.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Предоставляет окна фрейма для представления, при редактировании серверного документа в месте.

## <a name="related-class"></a>Связанный класс

Класс `CMenu` предоставляет интерфейс, через который осуществляется доступ к меню приложения. Это полезно для динамически Управление меню во время выполнения; Например, при добавлении или удалении элементов меню в соответствии с контекстом. Несмотря на то, что меню чаще всего используются с окна фрейма, они также могут использоваться с диалоговыми окнами и других окнах nonchild.

[CMenu](../mfc/reference/cmenu-class.md)<br/>
Инкапсулирует `HMENU` дескриптор для меню и контекстные меню приложения.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
