---
title: Средства отслеживания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0a0cc52e3a5150702af4acd293def38df758fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381541"
---
# <a name="trackers"></a>Средства отслеживания
[CRectTracker](../mfc/reference/crecttracker-class.md) класс предоставляет пользовательский интерфейс между прямоугольной элементами в приложении и пользователей, предоставляя различные стили отображения. Эти стили включают сплошная, штриховая или пунктирная границ; заштрихованного шаблон, который охватывает элемента; и маркеры, которые могут находиться за пределами или внутри границы изменения размера. Средства отслеживания часто используется в сочетании с OLE-элементы, то есть объектов, производных от `COleClientItem`. Прямоугольников отслеживания предоставляют визуальные подсказки о текущем состоянии элемента.  
  
 Пример MFC OLE [OCLIENT](../visual-cpp-samples.md) демонстрирует общий интерфейс, с помощью средства отслеживания и OLE-элементы для клиента с точки зрения приложения контейнера. Для демонстрации различных стилей и возможности объекта отслеживания, см. в образце общие MFC [TRACKER](../visual-cpp-samples.md).  
  
 Дополнительные сведения о реализации средства отслеживания в приложении OLE см. в разделе [средства отслеживания: реализация средства отслеживания в OLE приложения](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>См. также  
 [OLE](../mfc/ole-in-mfc.md)   
 [Класс COleClientItem](../mfc/reference/coleclientitem-class.md)
