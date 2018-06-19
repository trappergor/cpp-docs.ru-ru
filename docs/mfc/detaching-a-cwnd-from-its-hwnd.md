---
title: Отсоединение CWnd от HWND | Документы Microsoft
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
ms.openlocfilehash: a776b4ff4799750c89a322379a063030db748eec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342684"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND
Для обхода объекта -`HWND` связь, MFC предоставляет другой `CWnd` функции-члена [отсоединения](../mfc/reference/cwnd-class.md#detach), отсоединяет объект window C++ из окна Windows. Это предотвращает деструктор уничтожение окна Windows при уничтожении объекта.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

