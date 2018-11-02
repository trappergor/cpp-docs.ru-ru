---
title: Отсоединение CWnd от HWND
ms.date: 11/04/2016
f1_keywords:
- CWnd
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: fe4d9efa6adcec51d5944755e4a8abb1cc0784e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653977"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND

Если вам нужно обойти объект -`HWND` связи, MFC предоставляет другой `CWnd` функции-члена [отсоединения](../mfc/reference/cwnd-class.md#detach), которая отсоединяет объектом окна C++ из окна Windows. Это не позволяет деструктору уничтожение окна Windows, при уничтожении объекта.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон](../mfc/creating-windows.md)

- [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)

- [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)

