---
title: OLE-перетаскивания и передачи данных классов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d55d6d171f490631afe17a605f50607fb55f070b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Классы перетаскивания и передачи данных OLE
Эти классы используются в передаче данных OLE. Они позволяют данные будут передаваться между приложениями с помощью буфера обмена или перетаскивания и drop.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Определяет операцию перетаскивания и вставки от начала до конца. Этот класс определяет при запуске операции перетаскивания и при ее завершении. Она также отображает курсоров во время операции перетаскивания и вставки.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Используется, когда приложение предоставляет данные для передачи данных. `COleDataSource` может рассматриваться как объект объектно ориентированного буфер обмена.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Представляет целевой объект операции перетаскивания и вставки. Объект `COleDropTarget` объект соответствует окна на экране. Он определяет, следует ли принять все данные перетаскиваются на него и реализует операции фактическое drop.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Используется в качестве стороне получателя для `COleDataSource`. `COleDataObject` объекты предоставляют доступ к данным, хранящимся в `COleDataSource` объекта.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

