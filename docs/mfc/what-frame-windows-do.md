---
title: Функция окон фрейма
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 594700ef1cbe0030bbe452adaa40b29b4a72f4d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405681"
---
# <a name="what-frame-windows-do"></a>Функция окон фрейма

Помимо просто кадрирования представления, окон фреймов несут ответственность за многочисленные задачи, связанные с координацию фрейма с ее представлением, а также с приложением. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) наследовать от [CFrameWnd](../mfc/reference/cframewnd-class.md)и поэтому имеют `CFrameWnd` возможности, а также новые возможности, добавляющие их. Дочерние окна примеры представлений, элементов управления, таких как кнопки и списки с множественным и панели элементов управления, включая диалоговое окно панелей, панели инструментов и строки состояния.

Окна фрейма отвечает за управление макет из его дочерних окон. В платформе MFC окна фрейма помещает любой панели элементов управления, представления и другие дочерние окна внутри клиентской области.

Фрейм окна также перенаправляет команды, чтобы его представлений и может обрабатывать сообщения уведомления из элемента управления windows.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Панели элементов управления (их месте в окне фрейма)](../mfc/control-bars.md)

- [Управление меню, панелей элементов управления и ускорители (их месте в окне фрейма)](../mfc/managing-menus-control-bars-and-accelerators.md)

- [Маршрутизация команд (из окна фрейма для ее просмотра и другие целевые объекты команд)](../mfc/command-routing.md)

- [Архитектура документа/View](../mfc/document-view-architecture.md)

- [Панели элементов управления](../mfc/control-bars.md)

- [Элементы управления](../mfc/controls-mfc.md)

## <a name="see-also"></a>См. также

[Окна фрейма](../mfc/frame-windows.md)
