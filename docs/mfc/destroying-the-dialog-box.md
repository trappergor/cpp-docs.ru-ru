---
title: "Уничтожение диалогового окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1b6c94c4c7efe3bc3300d6c8c5c34fbe890fb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-dialog-box"></a>Уничтожение диалогового окна
Модальные диалоговые окна обычно создаются в кадре стека и удаляются при завершении выполнения функции, в котором они созданы. Когда объект выходит за пределы области, вызывается деструктор объекта диалогового окна.  
  
 Безрежимные диалоговые окна обычно создаются и контролируются родительского представления или фрейм окна — главное окно приложения или окне фрейма документа. Значение по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), который удаляет диалогового окна. Если окно является изолированным, не указателями на его или другие специальные права владения семантику, должны переопределять [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) для уничтожения объекта C++ диалогового окна. Следует также переопределить [OnCancel](../mfc/reference/cdialog-class.md#oncancel) и вызвать `DestroyWindow` из внутри него. В противном случае владелец диалогового окна должен удаляет этот объект C++, когда он больше не требуется.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

