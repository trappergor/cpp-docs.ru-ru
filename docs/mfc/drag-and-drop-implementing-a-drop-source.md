---
title: 'Перетаскивание: реализация источника перетаскивания | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e77119ac5b662165fd965047ae60fc2d5818cc1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928984"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Перетаскивание. Реализация источника сброса
В этой статье объясняется, как для приложения для предоставления данных для выполнения операции перетаскивания и вставки.  
  
 Базовая реализация источника перетаскивания относительно проста. Первым шагом является определение, какие события начать операцию перетаскивания. Рекомендуется использовать рекомендации по пользовательскому интерфейсу определить начала операции перетаскивания, как выбор данных и **WM_LBUTTONDOWN** событие, которое происходит в точке внутри выбранных данных. В примерах MFC OLE [OCLIENT](../visual-cpp-samples.md) и [HIERSVR](../visual-cpp-samples.md) придерживайтесь следующих правил.  
  
 Если приложение является контейнером и выбранных данных связанных или внедренных объектов типа `COleClientItem`, вызовите его `DoDragDrop` функции-члена. В ином случае строится `COleDataSource` объекта, инициализируйте его с выбором и вызвать объект источника данных `DoDragDrop` функции-члена. Если приложение является сервером, используйте `COleServerItem::DoDragDrop`. Сведения о настройке стандартного поведения перетаскивания и вставки, см. в статье [перетаскивание: Настройка](../mfc/drag-and-drop-customizing.md).  
  
 Если `DoDragDrop` возвращает **DROPEFFECT_MOVE**, немедленно удалите исходные данные из исходного документа. Не возвращает значение из `DoDragDrop` влияет на источника перетаскивания.  
  
 Дополнительные сведения:  
  
-   [Реализация объекта-приемника](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Настройка операции перетаскивания](../mfc/drag-and-drop-customizing.md)  
  
-   [Создание и уничтожение объектов данных OLE и источников данных](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Управление объектов OLE и источников данных](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>См. также  
 [Перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

