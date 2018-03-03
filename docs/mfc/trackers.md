---
title: "Средства отслеживания | Документы Microsoft"
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
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29e4d3c556a5f7b6b3aed5daa0285ea6c2c15447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="trackers"></a>Средства отслеживания
[CRectTracker](../mfc/reference/crecttracker-class.md) класс предоставляет пользовательский интерфейс между прямоугольной элементами в приложении и пользователей, предоставляя различные стили отображения. Эти стили включают сплошная, штриховая или пунктирная границ; заштрихованного шаблон, который охватывает элемента; и маркеры, которые могут находиться за пределами или внутри границы изменения размера. Средства отслеживания часто используется в сочетании с OLE-элементы, то есть объектов, производных от `COleClientItem`. Прямоугольников отслеживания предоставляют визуальные подсказки о текущем состоянии элемента.  
  
 Пример MFC OLE [OCLIENT](../visual-cpp-samples.md) демонстрирует общий интерфейс, с помощью средства отслеживания и OLE-элементы для клиента с точки зрения приложения контейнера. Для демонстрации различных стилей и возможности объекта отслеживания, см. в образце общие MFC [TRACKER](../visual-cpp-samples.md).  
  
 Дополнительные сведения о реализации средства отслеживания в приложении OLE см. в разделе [средства отслеживания: реализация средства отслеживания в OLE приложения](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>См. также  
 [OLE](../mfc/ole-in-mfc.md)   
 [Класс COleClientItem](../mfc/reference/coleclientitem-class.md)
