---
title: "Перетаскивание: реализация источника перетаскивания | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 301980f7f5a901aa4e2cba40357b18311eef581e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Перетаскивание. Реализация источника сброса
В этой статье объясняется, как для приложения для предоставления данных для выполнения операции перетаскивания и вставки.  
  
 Базовая реализация источника перетаскивания относительно проста. Первым шагом является определение, какие события начать операцию перетаскивания. Рекомендуется использовать рекомендации по пользовательскому интерфейсу определить начала операции перетаскивания, как выбор данных и `WM_LBUTTONDOWN` событие, которое происходит в точке внутри выбранных данных. В примерах MFC OLE [OCLIENT](../visual-cpp-samples.md) и [HIERSVR](../visual-cpp-samples.md) придерживайтесь следующих правил.  
  
 Если приложение является контейнером и выбранных данных связанных или внедренных объектов типа `COleClientItem`, вызовите его `DoDragDrop` функции-члена. В ином случае строится `COleDataSource` объекта, инициализируйте его с выбором и вызвать объект источника данных `DoDragDrop` функции-члена. Если приложение является сервером, используйте `COleServerItem::DoDragDrop`. Сведения о настройке стандартного поведения перетаскивания и вставки, см. в статье [перетаскивание: Настройка](../mfc/drag-and-drop-customizing.md).  
  
 Если `DoDragDrop` возвращает `DROPEFFECT_MOVE`, немедленно удалите исходные данные из исходного документа. Не возвращает значение из `DoDragDrop` влияет на источника перетаскивания.  
  
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

