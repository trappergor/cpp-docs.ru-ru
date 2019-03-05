---
title: Время инициализации объектов CWnd
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: aa396ade2e8ab4e1245e161423de7bd5bfafaaf8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291355"
---
# <a name="when-to-initialize-cwnd-objects"></a>Время инициализации объектов CWnd

Нельзя создавать свои собственные дочерние окна или вызывать любые функции Windows API в конструкторе класса `CWnd`-объект, производный от. Это обусловлено `HWND` для `CWnd` объект еще не создан. Наиболее Windows инициализации, например добавление дочерних окон, должна быть выполнена в [OnCreate](../mfc/reference/cwnd-class.md#oncreate) обработчик сообщений.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Создание документа или представления](../mfc/document-view-creation.md)

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)
