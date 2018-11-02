---
title: Классы, связанные с OLE
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 2c3aa5ea4e720b14c5fdc4cb3285cd812eb550e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584656"
---
# <a name="ole-related-classes"></a>Классы, связанные с OLE

Эти классы предоставляют ряд различных служб, от исключений в файл входных и выходных данных.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
Используется для создания элементов при запросе от других контейнеров. Этот класс служит базовым классом для более конкретные типы фабрик, в том числе `COleTemplateServer`.

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
Использовать для управления параллелизмом с помощью OLE упрощенного удаленной процедуры вызовы (LRPC).

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
Использует COM `IStream` интерфейс, чтобы предоставить `CFile` доступ к составные файлы. Этот класс (производный от `CFile`) включает сериализацию MFC для использования СТРУКТУРИРОВАННОГО хранилища.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Используется, чтобы разрешить перемещение, изменение размера и переукомплектации элементов на месте.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

