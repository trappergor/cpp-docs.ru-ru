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
ms.openlocfilehash: 60f99c01c7a311c31602269b49efaf434d16827a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267801"
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна

Не используйте C++ **удалить** оператор для уничтожения окна фрейма или представления. Вместо этого необходимо вызвать `CWnd` функция-член `DestroyWindow`. Окна фрейма, таким образом, необходимо выделить в куче с оператором **новый**. Будьте внимательны при выделении окна фрейма в стеке или глобально. Другие окна должны быть оборудованы в кадре стека, когда это возможно.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон](../mfc/creating-windows.md)

- [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)

- [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>См. также

[Уничтожение объектов окон](../mfc/destroying-window-objects.md)
