---
title: Добавление элементов к элементу управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab0c7cb1aebf1675d078aa99941edfd9afdc5a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341369"
---
# <a name="adding-items-to-the-control"></a>Добавление элементов в элемент управления
Для добавления элементов управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)), вызовите один из нескольких версий [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) функция-член, в зависимости от того, какая информация имеется. Принимает одну версию [LV_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) структуры, который вы подготавливаете. Поскольку `LV_ITEM` структура содержит много элементов, получить больший контроль над атрибуты для элемента управления.  
  
 Две важные члены (отношении представление отчета) `LV_ITEM` структуры являются `iItem` и `iSubItem` члены. `iItem` Член является отсчитываемый от нуля индекс элемента, создание ссылок на структуры и `iSubItem` член является от единицы индекс подэлемент, или нуль, если структура содержит сведения об элементе. С этими двумя элементами определения, для каждого элемента, тип и значение сведения подэлементов, отображаемый, когда элемент управления списком находится в представлении отчета. Дополнительные сведения см. в разделе [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem).  
  
 Дополнительные члены укажите текст, значок, состояние и данные элемента элемента. «Данные об элементе» является определяемые приложением значения, связанные с элемента представления списка. Дополнительные сведения о `LV_ITEM` структуры см. в разделе [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem).  
  
 Другие версии `InsertItem` принимать один или несколько отдельных значений, соответствующим членам в `LV_ITEM` структуры, что позволяет инициализировать только тех элементов, которые требуется поддерживать. Как правило список управления управляет хранением для элементов списка, но можно сохранить часть информации в приложении вместо этого с помощью «обратного вызова элементов». Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](../mfc/callback-items-and-the-callback-mask.md) в этом разделе и [элементы обратного вызова и маска обратного вызова](http://msdn.microsoft.com/library/windows/desktop/bb774736) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [Добавление представление списка элементов и подэлементов](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

