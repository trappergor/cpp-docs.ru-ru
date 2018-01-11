---
title: "Добавление столбцов в элемент управления (представление отчета) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c08a497b80b01523dd66bb02b657d611193ed11c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-columns-to-the-control-report-view"></a>Добавление столбцов в элемент управления (представление отчета)
> [!NOTE]
>  Следующая процедура применяется либо [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../mfc/reference/clistctrl-class.md) объекта.  
  
 Если элемент управления списка в представлении отчета, столбцы отображаются предоставление метода организации различных суб-элементов для каждого элемента управления списка. Эта организация реализуется с помощью однозначное соответствие между столбцом в элементе управления списком и вложенного элемента связанного элемента управления списка. Дополнительные сведения о дополнительных данных см. в разделе [Добавление элементов к элементу управления](../mfc/adding-items-to-the-control.md). Пример элемента управления списка в представлении отчетов обеспечивается представление сведений в Windows 95 и Windows 98 обозревателя. В первом столбце перечислены папки, значки файлов и меток. Другие столбцы списка размер файла, тип файла, дату последнего изменения и т. д.  
  
 Несмотря на то, что столбцы могут быть добавлены к элементу управления список в любое время, они отображаются только в том случае, если элемент управления имеет `LVS_REPORT` включен бит стиля.  
  
 Каждый столбец имеет связанный заголовок элемента (в разделе [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) объект, который метки столбца и дает пользователям возможность изменить размер столбца.  
  
 Если элемент управления списка поддерживает представление отчетов, необходимо добавить столбец для каждого из возможных подэлемента в элемент управления списка. Добавьте столбец, Подготовка [LV_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) структуры и затем вызова [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). После добавления необходимых столбцов (иногда называют элементов заголовка), их можно упорядочить с помощью функций-членов и стили, принадлежащих внедренные заголовка элемента управления. Дополнительные сведения см. в разделе [упорядочение элементов в элементе управления заголовка](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  Если элемент управления списком создается с **LVS_NOCOLUMNHEADER** стиля, любая попытка вставить столбцы будут игнорироваться.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

