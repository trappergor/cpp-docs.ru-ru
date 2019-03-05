---
title: Уничтожение объектов окон
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: f50d198f9868a70d25370f6c1399b66efaa5490b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289849"
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
