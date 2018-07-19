---
title: Уничтожение диалогового окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66a3ef9a72107ffb36a75834a6e197aba394c420
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343932"
---
# <a name="destroying-the-dialog-box"></a>Уничтожение диалогового окна
Модальные диалоговые окна обычно создаются в кадре стека и удаляются при завершении выполнения функции, в котором они созданы. Когда объект выходит за пределы области, вызывается деструктор объекта диалогового окна.  
  
 Безрежимные диалоговые окна обычно создаются и контролируются родительского представления или фрейм окна — главное окно приложения или окне фрейма документа. Значение по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), который удаляет диалогового окна. Если окно является изолированным, не указателями на его или другие специальные права владения семантику, должны переопределять [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) для уничтожения объекта C++ диалогового окна. Следует также переопределить [OnCancel](../mfc/reference/cdialog-class.md#oncancel) и вызвать `DestroyWindow` из внутри него. В противном случае владелец диалогового окна должен удаляет этот объект C++, когда он больше не требуется.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

