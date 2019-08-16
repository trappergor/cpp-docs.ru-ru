---
title: Изменение стилей элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: b3cc65ce6ef0e84eaa2f6738cb18b6b862a6473a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509050"
---
# <a name="changing-list-control-styles"></a>Изменение стилей элемента управления "Список"

Стиль окна элемента управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)) можно изменить в любое время после его создания. Изменяя стиль окна, вы изменяете вид представления, используемого элементом управления. Например, для эмуляции обозревателя можно указать пункты меню или кнопки панели инструментов для переключения элемента управления между различными представлениями: представление значков, представление списка и т. д.

Например, когда пользователь выбирает пункт меню, можно вызвать [жетвиндовлонг](/windows/win32/api/winuser/nf-winuser-getwindowlongw) , чтобы получить текущий стиль элемента управления, а затем вызвать [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) для сброса стиля. Дополнительные сведения см. в разделе [Использование элементов управления "представление списка](/windows/win32/Controls/using-list-view-controls) " в Windows SDK.

Доступные стили перечислены в окне [создать](../mfc/reference/clistctrl-class.md#create). Стили **только когда**, **LVS_SMALLICON**, **LVS_LIST**и **LVS_REPORT** обозначают четыре представления элементов управления списка.

## <a name="extended-styles"></a>Расширенные стили

В дополнение к стандартным стилям для элемента управления "список" существует другой набор, называемый расширенными стилями. Эти стили, обсуждаемые в [расширенных стилях представления списка](/windows/win32/Controls/extended-list-view-styles) в Windows SDK, предоставляют разнообразные полезные функции, которые настраивают поведение элемента управления "список". Чтобы реализовать поведение определенного стиля (например, выбора при наведении), выполните вызов [CListCtrl:: сетекстендедстиле](../mfc/reference/clistctrl-class.md#setextendedstyle), передав необходимый стиль. В следующем примере демонстрируется вызов функции:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
>  Для работы выбора при наведении необходимо также включить **LVS_EX_ONECLICKACTIVATE** или **LVS_EX_TWOCLICKACTIVATE** .

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
