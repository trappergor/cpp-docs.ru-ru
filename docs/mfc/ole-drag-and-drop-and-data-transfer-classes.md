---
title: "OLE-перетаскивания и передачи данных классов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e8c5a54184bcf6450bf39b39a6b90d7865c09d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Классы перетаскивания и передачи данных OLE
Эти классы используются в передаче данных OLE. Они позволяют данные будут передаваться между приложениями с помощью буфера обмена или перетаскивания и drop.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Определяет операцию перетаскивания и вставки от начала до конца. Этот класс определяет при запуске операции перетаскивания и при ее завершении. Она также отображает курсоров во время операции перетаскивания и вставки.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Используется, когда приложение предоставляет данные для передачи данных. `COleDataSource`может рассматриваться как объект объектно ориентированного буфер обмена.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Представляет целевой объект операции перетаскивания и вставки. Объект `COleDropTarget` объект соответствует окна на экране. Он определяет, следует ли принять все данные перетаскиваются на него и реализует операции фактическое drop.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Используется в качестве стороне получателя для `COleDataSource`. `COleDataObject`объекты предоставляют доступ к данным, хранящимся в `COleDataSource` объекта.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

