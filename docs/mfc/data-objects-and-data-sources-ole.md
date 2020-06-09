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
ms.openlocfilehash: dfe400dddfecce3e52337f7f449e975dff2ca83e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616223"
---
# <a name="data-objects-and-data-sources-ole"></a>Объекты и источники данных (OLE)

При выполнении переноса данных с помощью буфера обмена или перетаскивания данные имеют источник и назначение. Одно приложение предоставляет данные для копирования, а другое приложение принимает его для их ввода. Каждая сторона перемещения должна выполнять различные операции с теми же данными для достижения успешности перемещения. Библиотека Microsoft Foundation Class (MFC) предоставляет два класса, представляющих каждую сторону этого перемещения:

- Источники данных (реализованные `COleDataSource` объектами) представляют исходную сторону передаваемых данных. Они создаются исходным приложением, когда данные должны быть скопированы в буфер обмена, или когда для операции перетаскивания предоставляются данные.

- Объекты данных (реализованные `COleDataObject` объектами) представляют конечную сторону для перемещения данных. Они создаются, когда в целевом приложении отбрасываются данные или когда ему предлагается выполнить операцию вставки из буфера обмена.

В следующих статьях объясняется, как использовать объекты данных и источники данных в приложениях. Эти сведения применяются как к контейнерным, так и к серверным приложениям, так как они могут быть вызваны для копирования и вставки данных.

- [Объекты и источники данных. Создание и уничтожение](data-objects-and-data-sources-creation-and-destruction.md)

- [Объекты и источники данных. Манипуляция](data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>В этом разделе

[Перетаскивание](drag-and-drop-ole.md)

[Буфер обмена](clipboard.md)

## <a name="see-also"></a>См. также раздел

[OLE](ole-in-mfc.md)<br/>
[Класс Коледатаобжект](reference/coledataobject-class.md)<br/>
[Класс COleDataSource](reference/coledatasource-class.md)
