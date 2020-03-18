---
title: Отсоединение CWnd от HWND
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: f7a6f97ba9f1dd3a928a5450c1a899ce09a4ac5f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446957"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND

Если необходимо обойти связь Object-`HWND`, MFC предоставляет еще одну `CWnd` функцию-член, [отсоединенную](../mfc/reference/cwnd-class.md#detach), которая отключает объект C++ окна от окна Windows. Это не дает деструктору уничтожить окно Windows при уничтожении объекта.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание Windows](../mfc/creating-windows.md)

- [Последовательность уничтожения окна](../mfc/window-destruction-sequence.md)

- [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>См. также раздел

[Объекты окон](../mfc/window-objects.md)
