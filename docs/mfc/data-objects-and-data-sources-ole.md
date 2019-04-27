---
title: Объекты и источники данных (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: 485fa5c62aafa4c116a76547238325d2979bfdc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241214"
---
# <a name="data-objects-and-data-sources-ole"></a>Объекты и источники данных (OLE)

При выполнении передачи данных, либо с помощью буфера обмена или перетаскивания, данных имеет источник и назначение. Одно приложение предоставляет данные для копирования и принимает его другим приложением для вставки. Каждая сторона передачи необходимо выполнять различные операции на те же данные для передачи для успешного выполнения. Библиотека Microsoft Foundation Class (MFC) предоставляет два класса, представляющие каждой стороне этой передачи:

- Источники данных (как реализованный `COleDataSource` объекты) представляют исходной стороны передачи данных. Они создаются исходным приложением, когда данные копируются в буфер обмена, или когда данные предоставляются для операции перетаскивания и вставки.

- Объекты данных (как реализованный `COleDataObject` объекты) представляют передачи данных на стороне назначения. Они создаются в конечном приложении есть данные, удалить, в него, или ответ на запрос для выполнения операции вставки из буфера обмена.

Следующие статьи объясняется, как использовать объекты и источники данных в приложениях. Эти сведения относятся к контейнеру и серверных приложений, так как оба консультацией можно обращаться для копирования и вставки данных.

- [Объекты и источники данных. Создание и удаление](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Объекты и источники данных. Управление](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>В этом разделе

[Перетаскивание](../mfc/drag-and-drop-ole.md)

[Буфер обмена](../mfc/clipboard.md)

## <a name="see-also"></a>См. также

[OLE](../mfc/ole-in-mfc.md)<br/>
[Класс COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
[Класс COleDataSource](../mfc/reference/coledatasource-class.md)
