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
ms.openlocfilehash: f84e36a2a002610c294653012c40707fddcaba54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607471"
---
# <a name="destroying-the-dialog-box"></a>Уничтожение диалогового окна

Модальные диалоговые окна обычно создаются в кадре стека и удаляются при завершении выполнения функции, которое их создало. Деструктор объекта диалогового окна вызывается в том случае, когда объект выходит за пределы области действия.

Обычно создаются и владельцем родительского представления или фрейм окна немодальных диалоговых окон — окна главного фрейма приложения или окне фрейма документа. Значение по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), который удаляет диалогового окна. Если окно является изолированным, не указателями или другую семантику специальные права владения, следует переопределить [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) для уничтожения объекта C++ диалогового окна. Следует также переопределить [OnCancel](../mfc/reference/cdialog-class.md#oncancel) и вызвать `DestroyWindow` из внутри него. В противном случае владельца диалогового окна должен уничтожить объект C++, когда он больше не требуется.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

