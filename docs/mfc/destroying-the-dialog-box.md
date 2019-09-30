---
title: Уничтожение диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: 8b407c6e832dde7a5865146e7cc12d1840d3234a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685856"
---
# <a name="destroying-the-dialog-box"></a>Уничтожение диалогового окна

Модальные диалоговые окна обычно создаются в кадре стека и уничтожаются при завершении функции, создавшей их. Деструктор объекта диалогового окна вызывается, когда объект выходит из области действия.

Модальные диалоговые окна обычно создаются и принадлежат родительскому представлению или окну фрейма — главному фрейму приложения или окну фрейма документа. Обработчик [OnClose](../mfc/reference/cwnd-class.md#onclose) по умолчанию вызывает [дестройвиндов](../mfc/reference/cwnd-class.md#destroywindow), который уничтожает окно диалогового окна. Если диалоговое окно является единственным, без указателей на него или другой особой семантики владения, следует переопределить [постнкдестрой](../mfc/reference/cwnd-class.md#postncdestroy) для уничтожения объекта C++ диалогового окна. Следует также переопределить метод [OnCancel](../mfc/reference/cdialog-class.md#oncancel) и вызвать `DestroyWindow` из него. В противном случае владелец диалогового окна должен уничтожить C++ объект, если он больше не нужен.

## <a name="see-also"></a>См. также

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
