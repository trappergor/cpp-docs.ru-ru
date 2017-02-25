---
title: "Перетаскивание. Реализация источника перетаскивания | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "перетаскивание, вызов DoDragDrop"
  - "перетаскивание, источник перетаскивания"
  - "перетаскивание, инициация операций перетаскивания"
  - "перетаскивание OLE, вызов DoDragDrop"
  - "перетаскивание OLE, источник перетаскивания"
  - "перетаскивание OLE, инициация операций перетаскивания"
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Перетаскивание. Реализация источника перетаскивания
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается, как получить доступ к приложению предоставлять данные операции перетаскивания.  
  
 Базовая реализация источника размещения относительно проста.  Сначала необходимо определить, какие события начала операции перетаскивания.  Рекомендуемые правила пользовательского интерфейса определяют начало операции перетаскивания в качестве выделения данных и события `WM_LBUTTONDOWN`, выполненных в точке внутри выбранные данных.  Примеры MFC OLE [OCLIENT](../top/visual-cpp-samples.md) и [HIERSVR](../top/visual-cpp-samples.md) выполняют следующие рекомендации.  
  
 Если приложение контейнера и выбранные данные привязаны или внедренные объекты типа `COleClientItem`, следует вызвать функцию\-член `DoDragDrop`.  В противном случае создайте объект `COleDataSource`, инициализировать его с выделением и вызовите функцию\-член `DoDragDrop` объекта источника данных.  Если приложение сервера следует использовать `COleServerItem::DoDragDrop`.  Дополнительные сведения о настраивать расширение функциональности стандарта перетаскивания см. в статье [Перетаскивания: Настраивать](../Topic/Drag%20and%20Drop:%20Customizing.md).  
  
 Если `DoDragDrop` возвращает `DROPEFFECT_MOVE`, удалите источники данных из исходного документа немедленно.  Ни одно возвращаемое значение в `DoDragDrop` не влияет на источнике перетаскивания.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Реализация целевой объект перетаскивания](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Настраивать перетаскивания](../Topic/Drag%20and%20Drop:%20Customizing.md)  
  
-   [Создание и уничтожения объектов OLE данных и источников данных](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Управление OLE объекты данных и источников данных](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## См. также  
 [Перетаскивание \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)   
 [CView::OnDragLeave](../Topic/CView::OnDragLeave.md)