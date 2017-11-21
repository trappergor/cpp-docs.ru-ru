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
ms.openlocfilehash: 3d1f0635933d2cf27b824c8b0a93f66429e22ea8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Отсоединение CWnd от HWND
Для обхода объекта -`HWND` связь, MFC предоставляет другой `CWnd` функции-члена [отсоединения](../mfc/reference/cwnd-class.md#detach), отсоединяет объект window C++ из окна Windows. Это предотвращает деструктор уничтожение окна Windows при уничтожении объекта.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

