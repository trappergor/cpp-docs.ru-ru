---
title: Время инициализации объектов CWnd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6445190ab3da6ed84dbdd83cd0acab0ba98691f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388437"
---
# <a name="when-to-initialize-cwnd-objects"></a>Время инициализации объектов CWnd

Нельзя создавать свои собственные дочерние окна или вызывать любые функции Windows API в конструкторе класса `CWnd`-объект, производный от. Это обусловлено `HWND` для `CWnd` объект еще не создан. Наиболее Windows инициализации, например добавление дочерних окон, должна быть выполнена в [OnCreate](../mfc/reference/cwnd-class.md#oncreate) обработчик сообщений.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Создание документа или представления](../mfc/document-view-creation.md)

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)

