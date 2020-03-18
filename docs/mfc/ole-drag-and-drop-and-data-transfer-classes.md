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
ms.openlocfilehash: 7e01b6d5a7d14e0af4ca760e6e601e91359c8ab1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447625"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Классы перетаскивания и передачи данных OLE

Эти классы используются при передаче данных OLE. Они позволяют передавать данные между приложениями с помощью буфера обмена или перетаскиванием.

[коледропсаурце](../mfc/reference/coledropsource-class.md)<br/>
Управляет операцией перетаскивания от начала до конца. Этот класс определяет, когда начинается операция перетаскивания и когда она завершается. В нем также отображается обратная связь курсора во время операции перетаскивания.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
Используется, когда приложение предоставляет данные для обмена данными. `COleDataSource` можно просмотреть как объектно-ориентированный объект буфера обмена.

[коледроптаржет](../mfc/reference/coledroptarget-class.md)<br/>
Представляет целевой объект операции перетаскивания. Объект `COleDropTarget` соответствует окну на экране. Он определяет, следует ли принимать любые данные, переброшенные в него, и реализует фактическую операцию удаления.

[коледатаобжект](../mfc/reference/coledataobject-class.md)<br/>
Используется в качестве получателя для `COleDataSource`. `COleDataObject` объекты предоставляют доступ к данным, хранящимся в объекте `COleDataSource`.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
