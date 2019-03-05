---
title: Классы перетаскивания и передачи данных OLE
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: e30a358da55b29f9519bc1ab8ee5c93ada308d98
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284428"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Классы перетаскивания и передачи данных OLE

Эти классы используются в передаче данных OLE. Они позволяют данные будут передаваться между приложениями с помощью буфера обмена или перетаскивания и drop.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
Управляет операциями перетаскивания и вставки от начала до конца. Этот класс определяет, когда начинается операция перетаскивания, и при ее окончании. Она также отображает курсор обратной связи во время операции перетаскивания и вставки.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
Используется, когда приложение предоставляет данные для передачи данных. `COleDataSource` может рассматриваться как объект объектно ориентированного буфер обмена.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
Представляет целевой объект операции перетаскивания и вставки. Объект `COleDropTarget` соответствует окна на экране. Он определяет, следует ли принимать любые данные перетаскиваются на него и реализует операции фактического удаления.

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
Использовать как на стороне получателя для `COleDataSource`. `COleDataObject` объекты предоставляют доступ к данным, хранящимся с `COleDataSource` объекта.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
