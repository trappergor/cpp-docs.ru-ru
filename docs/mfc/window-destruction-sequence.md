---
title: Последовательность деструкции окна
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: d4592e6ac0077d6bc335b50f2d67b140402b4fe2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287665"
---
# <a name="window-destruction-sequence"></a>Последовательность деструкции окна

В платформе MFC, когда пользователь закрывает окно фрейма окна по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Последняя функция-член вызывается при уничтожении окна Windows является [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), выполняющий очистку, вызывает [по умолчанию](../mfc/reference/cwnd-class.md#default) член функции для выполнения очистки Windows и наконец вызывает виртуальная функция-член [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) реализация `PostNcDestroy` удаляет объектом окна C++.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)

- [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>См. также

[Уничтожение объектов окон](../mfc/destroying-window-objects.md)
