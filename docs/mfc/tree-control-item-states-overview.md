---
title: Общие сведения о состояниях элемента древовидного элемента управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bc62308642492aa00a139fb15cc9e6cdcfc3247
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-states-overview"></a>Общие сведения о состояниях элемента древовидного элемента управления
Каждый элемент в виде дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) находится в текущем состоянии. Например элемент можно выбрать, отключенные, развернутыми и т. д. В большинстве случаев дерево автоматически устанавливает состояние элемента в соответствии с действиями пользователя, такие как выбор элемента. Тем не менее, можно также задать состояние элемента с помощью [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) функция-член и получить текущее состояние элемента с помощью [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) функции-члена. Полный список состояний элементов см. в разделе [дерево управления константы](http://msdn.microsoft.com/library/windows/desktop/bb759985) в Windows SDK.  
  
 Текущее состояние элемента определяется `nState` параметра. Дерево может изменить состояние элемента с учетом действий пользователя, например, при выборе элемента или фокуса к элементу. Кроме того приложение может изменить состояние элемента отключить или скрыть элемент, или указать наложения изображения или изображения состояния.  
  
 Если задать или изменить состояние элемента `nStateMask` параметр указывает, какое состояние битов для задания и `nState` параметр содержит новые значения для этих файлов. Например, в следующем примере изменяется текущее состояние родительского элемента (определяется `hParentItem`) в `CTreeCtrl` объекта (`m_treeCtrl`) для **TVIS_EXPANDPARTIAL**:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 Еще один пример изменения состояния можно задать изображение наложения элементов. Чтобы выполнить это, `nStateMask` должен включать `TVIS_OVERLAYMASK` значение, и `nState` должен включать единицы индекс изображение перекрытия сдвиг влево восьми бит, используя [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) макрос. Индекс может быть 0, чтобы указать изображение без перекрытия. Изображение перекрытия должны были добавлены список элемента управления дерева наложение изображений с предыдущим вызовом [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функции. В функции указан от единицы индекс образа для добавления. Это индекс, используемый с **INDEXTOOVERLAYMASK** макрос. Дерево может иметь до четырех изображения перекрытия.  
  
 Чтобы задать изображение состояния элемента, `nStateMask` должен включать `TVIS_STATEIMAGEMASK` значение, и `nState` должен содержать от единицы индекс изображения сдвиг влево биты 12 с помощью [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597) макрос. Индекс может быть 0, чтобы указать изображение для состояния. Дополнительные сведения об образах наложения и состояния см. в разделе [списки изображений элемента управления дерева](../mfc/tree-control-image-lists.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

