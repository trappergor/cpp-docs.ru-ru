---
title: Изменение стилей элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 2ba9ae81f7b1693be0df3565256a65e4e3561fd3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344468"
---
# <a name="changing-list-control-styles"></a>Изменение стилей элемента управления "Список"

Можно изменить стиль окна элемента управления списка ([CListCtrl](../mfc/reference/clistctrl-class.md)) в любое время после его создания. Можно изменить стиль окна, измените тип представления, которые использует элемент управления. Например, для эмуляции в обозревателе, можно предоставить пункты меню или кнопки панели инструментов для переключения управления между различными представлениями: значки, представление списка и т. д.

Например, когда пользователь выбирает элемент меню, позволяющих улучшить вызов [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) для получения текущего стиля элемента управления, а затем вызвать [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) сбросить стиль. Дополнительные сведения см. в разделе [с помощью элементов управления представления списком](/windows/desktop/Controls/using-list-view-controls) в пакете Windows SDK.

Доступные стили, перечислены в [создать](../mfc/reference/clistctrl-class.md#create). Стили **только**, **LVS_SMALLICON**, **LVS_LIST**, и **LVS_REPORT** назначить четыре списки управления.

## <a name="extended-styles"></a>Расширенные стили

Помимо стандартных стили для элемента управления списка доступен другой набор, называют расширенные стили. Эти стили, рассматриваемые в [расширенных стилей представления списка](/windows/desktop/Controls/extended-list-view-styles) в пакете Windows SDK предоставляют широкий набор полезных функций, определяющих поведение списка элемента управления. Чтобы реализовать поведение определенного стиля (например, выбор при наведении указателя мыши), отправьте вызов в [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), передавая необходимый стиль. В следующем примере демонстрируется вызов функции:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
>  Для выбора при наведении указателя мыши для работы, вам также потребуется **LVS_EX_ONECLICKACTIVATE** или **LVS_EX_TWOCLICKACTIVATE** включен.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
