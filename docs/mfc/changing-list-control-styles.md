---
title: Изменение стилей элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 5f45e0549c3fc0f5747f8dd12a6310fafd7dd7bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370805"
---
# <a name="changing-list-control-styles"></a>Изменение стилей элемента управления "Список"

Вы можете изменить стиль управления списком[(CListCtrl)](../mfc/reference/clistctrl-class.md)в любое время после его создания. Изменяя стиль окна, вы меняете вид представления, который использует элемент управления. Например, чтобы подражать Explorer, можно предоставить элементы меню или кнопки панели инструментов для переключения управления между различными представлениями: представлениезначных, представление списка и так далее.

Например, когда пользователь выбирает элемент меню, можно позвонить [в GetWindowLong,](/windows/win32/api/winuser/nf-winuser-getwindowlongw) чтобы получить текущий стиль управления, а затем вызвать [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) для сбросить стиль. Для получения дополнительной информации в SDK Windows можно [ознакомиться на элементах управления представлениями.](/windows/win32/Controls/using-list-view-controls)

Доступные стили перечислены в [Create](../mfc/reference/clistctrl-class.md#create). Стили **LVS_ICON,** **LVS_SMALLICON,** **LVS_LIST**и **LVS_REPORT** обозначают представления управления четырьмя списками.

## <a name="extended-styles"></a>Расширенные стили

В дополнение к стандартным стилям для управления списком, есть еще один набор, называемый расширенными стилями. Эти стили, обсуждаемые в [расширенных стилях представления списка](/windows/win32/Controls/extended-list-view-styles) в SDK Windows, предоставляют различные полезные функции, которые настраивает поведение элемента управления списком. Чтобы реализовать поведение определенного стиля (например, выбор нависшие), позвоните в [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), передай необходимый стиль. Следующий пример демонстрирует вызов функции:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> Для того чтобы навести выбор на ведомый для работы, вы также должны иметь или **LVS_EX_ONECLICKACTIVATE** или **LVS_EX_TWOCLICKACTIVATE** включено.

## <a name="see-also"></a>См. также раздел

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
