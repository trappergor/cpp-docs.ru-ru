---
title: Классы, связанные с OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 6f6db6ce133b440a5ed86e7c1642396888744540
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621023"
---
# <a name="ole-related-classes"></a>Классы, связанные с OLE

Эти классы предоставляют ряд различных служб, от исключений до входных и выходных файлов.

[COleObjectFactory](reference/coleobjectfactory-class.md)<br/>
Используется для создания элементов по запросу из других контейнеров. Этот класс выступает в качестве базового класса для более конкретных типов фабрик, включая `COleTemplateServer` .

[COleMessageFilter](reference/colemessagefilter-class.md)<br/>
Используется для управления параллелизмом с помощью вызовов OLE-облегченного удаленного вызова процедур (ЛРПК).

[COleStreamFile](reference/colestreamfile-class.md)<br/>
Использует интерфейс COM `IStream` для предоставления `CFile` доступа к составным файлам. Этот класс (производный от `CFile` ) позволяет СЕРИАЛИЗАЦИИ MFC использовать структурированное хранилище OLE.

[CRectTracker](reference/crecttracker-class.md)<br/>
Используется для разрешения перемещения, изменения размера и ориентации элементов на месте.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
