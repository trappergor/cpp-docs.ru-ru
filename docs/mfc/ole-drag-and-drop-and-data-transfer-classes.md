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
ms.openlocfilehash: 7520881314da9568f6130f5fe2ccf0a3e0e88e2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475195"
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

