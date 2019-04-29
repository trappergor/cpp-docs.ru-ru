---
title: Общие сведения о состояниях элемента древовидного элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: 57c6714073f4939ffb791a78454e9eac6342309b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392470"
---
# <a name="tree-control-item-states-overview"></a>Общие сведения о состояниях элемента древовидного элемента управления

Каждый элемент в виде дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) находится в текущем состоянии. Например элемент можно выбрать, отключено, развернутое и т. д. В большинстве случаев дерево автоматически задает состояние элемента в соответствии с действиями пользователя, такие как выбор элемента. Тем не менее, можно также задать состояние элемента с помощью [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) функция-член и извлечь текущее состояние элемента с помощью [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) функция-член. Полный список состояний элементов, см. в разделе [константы элемента управления представления дерева](/windows/desktop/Controls/tree-view-control-item-states) в пакете Windows SDK.

Текущее состояние элемента определяется *nState* параметра. Дерево может изменить состояние элемента в соответствии с действием пользователя, например Выбор элемента или для установки фокуса на элемент. Кроме того приложение может изменить состояние элемента Чтобы отключить или скрыть элемент или задать наложение изображения или изображения состояния.

Если указать или изменить состояние элемента, *nStateMask* параметр указывает, какое состояние битов для задания и *nState* параметр содержит новые значения для этих файлов. Например, следующий пример изменяет текущее состояние родительского элемента (определяется *hParentItem*) в `CTreeCtrl` объекта (`m_treeCtrl`) для `TVIS_EXPANDPARTIAL`:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Еще одним примером изменения состояния следует задать изображение для наложения элемента. Чтобы выполнить это, *nStateMask* должен включать `TVIS_OVERLAYMASK` значение, и *nState* должен включать от единицы индекс изображение для наложения сдвинуты влево восемь битов с помощью [ INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос. Индекс может быть 0, чтобы указать изображение для наложения. Изображение для наложения должны были добавлены список элемента управления дерева наложение изображений с предыдущим вызовом [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функции. Эта функция определяет от единицы индекс изображения, чтобы добавить; Это индекс, используемый с макросом INDEXTOOVERLAYMASK. Дерево может иметь до четырех наложения изображений.

Чтобы задать изображения состояния элемента, *nStateMask* должен включать `TVIS_STATEIMAGEMASK` значение, и *nState* должен включать от единицы индекс изображения сдвинуты влево биты 12 с помощью [ INDEXTOSTATEIMAGEMASK](/windows/desktop/api/commctrl/nf-commctrl-indextostateimagemask) макрос. Индекс может быть 0 для указания не изображения состояния. Дополнительные сведения о наложении, чтобы состояние изображений, см. в разделе [списки изображений элемента управления дерева](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
