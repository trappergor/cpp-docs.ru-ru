---
title: Выделение и освобождение памяти окна
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: a9bbf92a586a910dfa4e81774ce4817c9cf458e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582500"
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна

Не используйте C++ **удалить** оператор для уничтожения окна фрейма или представления. Вместо этого необходимо вызвать `CWnd` функция-член `DestroyWindow`. Окна фрейма, таким образом, необходимо выделить в куче с оператором **новый**. Будьте внимательны при выделении окна фрейма в стеке или глобально. Другие окна должны быть оборудованы в кадре стека, когда это возможно.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон](../mfc/creating-windows.md)

- [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)

- [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>См. также

[Уничтожение объектов окон](../mfc/destroying-window-objects.md)

