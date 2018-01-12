---
title: "Отсоединение CWnd от HWND | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWnd
dev_langs: C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6aa24e0e9a0d9ee50a0c5c69e280ea7a727ca38b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND
Для обхода объекта -`HWND` связь, MFC предоставляет другой `CWnd` функции-члена [отсоединения](../mfc/reference/cwnd-class.md#detach), отсоединяет объект window C++ из окна Windows. Это предотвращает деструктор уничтожение окна Windows при уничтожении объекта.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

