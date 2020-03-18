---
title: Классы, связанные с OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: dfcc07b3fbd0c5badce8e397f4d52bc7d8d3028c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447608"
---
# <a name="ole-related-classes"></a>Классы, связанные с OLE

Эти классы предоставляют ряд различных служб, от исключений до входных и выходных файлов.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
Используется для создания элементов по запросу из других контейнеров. Этот класс выступает в качестве базового класса для более конкретных типов фабрик, в том числе `COleTemplateServer`.

[колемессажефилтер](../mfc/reference/colemessagefilter-class.md)<br/>
Используется для управления параллелизмом с помощью вызовов OLE-облегченного удаленного вызова процедур (ЛРПК).

[колестреамфиле](../mfc/reference/colestreamfile-class.md)<br/>
Использует интерфейс COM `IStream` для предоставления `CFile` доступа к составным файлам. Этот класс (производный от `CFile`) позволяет сериализации MFC использовать структурированное хранилище OLE.

[кректтраккер](../mfc/reference/crecttracker-class.md)<br/>
Используется для разрешения перемещения, изменения размера и ориентации элементов на месте.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
