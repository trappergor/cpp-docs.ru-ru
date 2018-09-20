---
title: Отсоединение CWnd от HWND | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c69703d8c528d82a696fc94be76ac4a569628b4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392652"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND

Если вам нужно обойти объект -`HWND` связи, MFC предоставляет другой `CWnd` функции-члена [отсоединения](../mfc/reference/cwnd-class.md#detach), которая отсоединяет объектом окна C++ из окна Windows. Это не позволяет деструктору уничтожение окна Windows, при уничтожении объекта.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон](../mfc/creating-windows.md)

- [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)

- [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)

