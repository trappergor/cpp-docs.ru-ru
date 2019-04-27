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
ms.openlocfilehash: d42fa475fca7c92e4ba46b164a9beda9869231c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219786"
---
# <a name="frame-window-classes"></a>Классы окна фрейма

Каждое приложение имеет один «фрейма главного окна», окно рабочего стола, который обычно имеет имя приложения в его заголовок. Обычно каждый документ имеет один «окна фрейма документа». Окном фрейма документа содержит по крайней мере одно представление, в которой приведены данные документа.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Windows кадра в SDI и MDI-приложения

Для приложения SDI имеется одно окно фрейма, производный от класса [CFrameWnd](../mfc/reference/cframewnd-class.md). Это окно будет фрейма главного окна и окна фрейма документа. Приложение MDI, фрейма главного окна является производным от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), и окна фрейма документа, которые являются дочерними окнами MDI, являются производными от класса [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Класс окна фрейма или являются производными от него

Эти классы обеспечивают большинство функций окна фрейма, необходимые для ваших приложений. В обычных условиях по умолчанию поведение и внешний вид, которые они предоставляют будет удовлетворить эту потребность. Если для получения дополнительной функциональности, производные от этих классов.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Классы окна фрейма, создаваемые с помощью мастера приложений](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

- [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>См. также

[Окна фрейма](../mfc/frame-windows.md)
