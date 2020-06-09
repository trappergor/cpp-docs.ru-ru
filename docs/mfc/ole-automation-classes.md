---
title: Классы автоматизации OLE
ms.date: 11/04/2016
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
ms.openlocfilehash: 04cb93b8ce3699b579342d33c0dae77176878379
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625300"
---
# <a name="ole-automation-classes"></a>Классы автоматизации OLE

Эти классы поддерживают клиентов автоматизации (приложений, управляющих другими приложениями). Серверы автоматизации (приложения, которые могут управляться другими приложениями) поддерживаются с помощью [карт диспетчеризации](reference/dispatch-maps.md).

[COleDispatchDriver](reference/coledispatchdriver-class.md)<br/>
Используется для вызова серверов автоматизации из клиента автоматизации. При добавлении класса этот класс используется для создания строго типизированных классов для серверов автоматизации, предоставляющих библиотеку типов.

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
Исключение, полученное в результате ошибки при OLE Automation. Исключения автоматизации генерируются серверами службы автоматизации и перехватываются клиентами автоматизации.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
