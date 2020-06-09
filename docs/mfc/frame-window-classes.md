---
title: Классы окна фрейма
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
ms.openlocfilehash: ffa5b966ee042120213896dc7ad9d81c048ef928
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625812"
---
# <a name="frame-window-classes"></a>Классы окна фрейма

Каждое приложение имеет одно «главное окно фрейма», окно рабочего стола, которое обычно содержит имя приложения в его заголовке. Каждый документ обычно имеет одно окно фрейма документа. Окно фрейма документа содержит по крайней мере одно представление, представляющее данные документа.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Окна фрейма в приложениях SDI и MDI

Для приложения SDI существует одно окно фрейма, производное от класса [CFrameWnd](reference/cframewnd-class.md). Это окно является как основным, так и окном фрейма документа. Для приложения MDI основное окно фрейма является производным от класса [CMDIFrameWnd](reference/cmdiframewnd-class.md), а окна фрейма документа, которые являются дочерними окнами MDI, являются производными от класса [CMDIChildWnd](reference/cmdichildwnd-class.md).

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Используйте класс окна фрейма или производные от него

Эти классы предоставляют большую часть функциональных возможностей окна кадров, необходимых для приложений. При нормальных обстоятельствах поведение по умолчанию и внешний вид, которые они предоставляют, будут соответствовать вашим потребностям. Если требуются дополнительные функции, производные от этих классов.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Классы окон фрейма, созданные мастером приложений](frame-window-classes-created-by-the-application-wizard.md)

- [Стили окна фрейма](frame-window-styles-cpp.md)

- [Изменение стилей окна, созданного MFC](changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>См. также раздел

[Окна фрейма](frame-windows.md)
