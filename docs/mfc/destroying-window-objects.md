---
title: Уничтожение объектов окон | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 704122f028cd744f0ce064f0153825830144d5b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401645"
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

