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
ms.openlocfilehash: 9b1244b03dc3f6f418730dd782050448f3bf8934
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621917"
---
# <a name="destroying-the-dialog-box"></a>Уничтожение диалогового окна

Модальные диалоговые окна обычно создаются в кадре стека и уничтожаются при завершении функции, создавшей их. Деструктор объекта диалогового окна вызывается, когда объект выходит из области действия.

Модальные диалоговые окна обычно создаются и принадлежат родительскому представлению или окну фрейма — главному фрейму приложения или окну фрейма документа. Обработчик [OnClose](reference/cwnd-class.md#onclose) по умолчанию вызывает [дестройвиндов](reference/cwnd-class.md#destroywindow), который уничтожает окно диалогового окна. Если диалоговое окно является единственным, без указателей на него или другой особой семантики владения, следует переопределить [постнкдестрой](reference/cwnd-class.md#postncdestroy) для уничтожения объекта диалогового окна C++. Следует также переопределить метод [OnCancel](reference/cdialog-class.md#oncancel) и вызвать `DestroyWindow` из него. В противном случае владелец диалогового окна должен уничтожить объект C++, когда он больше не нужен.

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
