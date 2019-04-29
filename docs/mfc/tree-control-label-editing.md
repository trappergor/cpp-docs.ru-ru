---
title: Редактирование меток древовидного элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: 446db94ec49859e2213f00d205df57e332c85af2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388154"
---
# <a name="tree-control-label-editing"></a>Редактирование меток древовидного элемента управления

Пользователь может напрямую изменять метки элементов в виде дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) с **TVS_EDITLABELS** стиля. Пользователь начинает изменения, щелкнув метку элемента, который имеет фокус. Приложение начинает изменение с помощью [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) функция-член. Дерево отправляет уведомления при редактировании начинается и когда она отменена или завершена. После завершения редактирования вы несете ответственность за обновление метки элемента, если это необходимо.

Редактирование меток начала, отправляет дерево [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) сообщение уведомления. При обработке этого уведомления, можно разрешить редактирование некоторые метки и предотвращения внесения других изменений. Возвращено значение 0 разрешает изменение, и возвращает ненулевое значение предотвращает его.

Когда редактирование меток отменена или завершена, дерево отправляет [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit) сообщение уведомления. *LParam* параметр — это адрес [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) структуры. **Элемент** член является [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) структура, которая определяет элемент и включает в себя измененного текста. Вы несете ответственность за обновление элемента метки, при необходимости возможно после проверки отредактированную строку. *PszText* членом `TV_ITEM` равно 0, если изменение отменяется.

Во время редактирования метки, обычно в ответ на [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) сообщение уведомления, можно получить указатель на элемент управления редактирования, используемый для редактирования метки с помощью [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) член функция. Можно вызвать элемента управления поля ввода [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) функция-член для ограничения объема текста, пользователь может ввести или подкласс поле ввода для перехвата и отменить недопустимые символы. Обратите внимание, что элемент управления отображается только *после* **TVN_BEGINLABELEDIT** отправляется.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
