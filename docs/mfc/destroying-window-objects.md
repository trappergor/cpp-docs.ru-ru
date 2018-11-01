---
title: Уничтожение объектов окон
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: 363ff2a4cee48b1660de87714d73c93e795017cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488816"
---
# <a name="destroying-window-objects"></a>Уничтожение объектов окон

Будьте осторожны с собственные дочерние окна для уничтожения объектом окна C++, когда пользователь завершил работу с окном. Если эти объекты не уничтожаются, приложение не восстановит их память. К счастью среда управляет уничтожение окна, а также создание окон фрейма, представлений и диалоговых окон. Если вы создаете дополнительные окна, вы несете ответственность для уничтожение.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)

- [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)

- [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)

- [Уничтожение окон фрейма](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)

