---
title: "Объекты и источники данных (OLE) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04619ee7851d2e2d6ad569583dfbb2e619d37026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-objects-and-data-sources-ole"></a>Объекты и источники данных (OLE)
При выполнении передачи данных, либо с помощью буфера обмена или перетаскивания, что данные содержат источник и назначение. Одно приложение предоставляет данные для копирования, и другое приложение принимает это значение для вставки. Каждая сторона передачи необходимо выполнять различные операции на тех же данных, для передачи данных для успешного выполнения. Библиотека Microsoft Foundation Class (MFC) предоставляет двух классов, представляющих каждой стороны передачи:  
  
-   Источники данных (как это реализовано `COleDataSource` объекты) представляют отправителе передачи данных. Они создаются исходным приложением, когда данные копируются в буфер обмена или данные, предоставленные для операции перетаскивания и вставки.  
  
-   Объекты данных (как это реализовано `COleDataObject` объекты) представляют стороны назначения передачи данных. Они создаются, если конечное приложение имеются данные, удаляются в него или ответ на запрос для выполнения операции вставки из буфера обмена.  
  
 Следующие статьи объясняется, как использовать объекты и источники данных в приложениях. Эти сведения относятся к контейнеру и серверных приложений, так как оба может быть вызван для копирования и вставки данных.  
  
-   [Объекты и источники данных. Создание и уничтожение](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Объекты и источники данных. Манипуляция](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перетаскивание](../mfc/drag-and-drop-ole.md)  
  
 [Буфер обмена](../mfc/clipboard.md)  
  
## <a name="see-also"></a>См. также  
 [OLE](../mfc/ole-in-mfc.md)   
 [Класс COleDataObject](../mfc/reference/coledataobject-class.md)   
 [Класс COleDataSource](../mfc/reference/coledatasource-class.md)
