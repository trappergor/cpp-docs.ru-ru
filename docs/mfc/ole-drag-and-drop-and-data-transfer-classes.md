---
title: Классы перетаскивания и передачи данных OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 530b1772dfb623689facd5b14eebe9ed1eacd4fd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624145"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Классы перетаскивания и передачи данных OLE

Эти классы используются при передаче данных OLE. Они позволяют передавать данные между приложениями с помощью буфера обмена или перетаскиванием.

[COleDropSource](reference/coledropsource-class.md)<br/>
Управляет операцией перетаскивания от начала до конца. Этот класс определяет, когда начинается операция перетаскивания и когда она завершается. В нем также отображается обратная связь курсора во время операции перетаскивания.

[COleDataSource](reference/coledatasource-class.md)<br/>
Используется, когда приложение предоставляет данные для обмена данными. `COleDataSource`можно просмотреть как объектно-ориентированный объект буфера обмена.

[COleDropTarget](reference/coledroptarget-class.md)<br/>
Представляет целевой объект операции перетаскивания. `COleDropTarget`Объект соответствует окну на экране. Он определяет, следует ли принимать любые данные, переброшенные в него, и реализует фактическую операцию удаления.

[COleDataObject](reference/coledataobject-class.md)<br/>
Используется как получатель на стороне `COleDataSource` . `COleDataObject`объекты предоставляют доступ к данным, хранящимся в `COleDataSource` объекте.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
