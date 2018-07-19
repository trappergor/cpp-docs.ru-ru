---
title: Выделение и освобождение памяти окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1364b4d29e2ccd2c9563359716eba6880df5436
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341463"
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна
Не используйте C++ **удалить** оператор для уничтожения окна фрейма или представления. Вместо этого необходимо вызвать `CWnd` функции-члена `DestroyWindow`. Окна фрейма, таким образом, необходимо выделить в куче с оператором **новый**. Будьте внимательны при выделении фреймов глобально или в кадре стека. Другие окна необходимо выделить в кадре стека, когда это возможно.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>См. также  
 [Уничтожение объектов окон](../mfc/destroying-window-objects.md)

