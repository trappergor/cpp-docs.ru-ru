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
ms.openlocfilehash: 2e0484698654cd14f22a92be76a80f71c0f9adf5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621846"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND

Если необходимо обойти объектную `HWND` связь, MFC предоставляет другую функцию- `CWnd` член, [отсоединенную](reference/cwnd-class.md#detach), которая отключает объект окна C++ от окна Windows. Это не дает деструктору уничтожить окно Windows при уничтожении объекта.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание окон](creating-windows.md)

- [Последовательность уничтожения окна](window-destruction-sequence.md)

- [Выделение и освобождение памяти окна](allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>См. также раздел

[Объекты окна](window-objects.md)
