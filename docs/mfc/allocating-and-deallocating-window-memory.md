---
title: "Выделение и освобождение памяти окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 294de3c4d4ecdfcb31f6e8c227bd8a3c6764268d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна
Не используйте C++ **удалить** оператор для уничтожения окна фрейма или представления. Вместо этого необходимо вызвать `CWnd` функции-члена `DestroyWindow`. Окна фрейма, таким образом, необходимо выделить в куче с оператором **новый**. Будьте внимательны при выделении фреймов глобально или в кадре стека. Другие окна необходимо выделить в кадре стека, когда это возможно.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>См. также  
 [Уничтожение объектов окон](../mfc/destroying-window-objects.md)

