---
title: Добавление столбцов в элемент управления (представление отчета) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3e81de52856d67760ffe58f29e4c39ac79213c4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221948"
---
# <a name="adding-columns-to-the-control-report-view"></a>Добавление столбцов в элемент управления (представление отчета)
> [!NOTE]
>  Следующая процедура применяется либо [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../mfc/reference/clistctrl-class.md) объекта.  
  
 Когда элемент управления списка находится в представлении отчетов, отображаются столбцы, предоставление метода организации различных подэлементов элемента для каждого элемента управления списка. Такая организация реализуется с помощью однозначного соответствия между столбцом в элементе управления списком и связанный вложенного элемента для элемента управления. Дополнительные сведения о дополнительных данных, см. в разделе [Добавление элементов к элементу управления](../mfc/adding-items-to-the-control.md). Пример элемента управления списка в представлении отчетов обеспечивается представление сведений, в Windows 95 и Windows 98 Explorer. В первом столбце перечислены папки, значки файлов и метки. Другие столбцы перечисляют размер файла, тип файла, дату последнего изменения и т. д.  
  
 Несмотря на то, что столбцы можно добавить к элементу управления списка в любое время, они отображаются только в том случае, если элемент управления имеет `LVS_REPORT` включен бит стиля.  
  
 Каждый столбец содержит заголовок, связанный элемент (см. в разделе [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) объект, который помечает столбец и позволяет пользователю изменить размер столбца.  
  
 Если элемент управления списка поддерживает представление отчета, необходимо добавить столбец для каждого из возможных подэлемента в элемент управления списка. Добавьте столбец, Подготовка [LV_COLUMN](/windows/desktop/api/commctrl/ns-commctrl-taglvcolumna) структуры и затем сделать вызов к [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). После добавления необходимых столбцов (иногда называют элементов заголовка), их можно упорядочить с помощью функции-члены и стили, принадлежащих embedded заголовка элемента управления. Дополнительные сведения см. в разделе [упорядочение элементов в элементе управления заголовка](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  Если элемент управления списка создается с помощью **LVS_NOCOLUMNHEADER** стиль, любая попытка вставить столбцы будут игнорироваться.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

