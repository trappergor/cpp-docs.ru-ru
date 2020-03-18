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
ms.openlocfilehash: 644a4930eb55636ba6e87b949ed610b725334661
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447678"
---
# <a name="ole-automation-classes"></a>Классы автоматизации OLE

Эти классы поддерживают клиентов автоматизации (приложений, управляющих другими приложениями). Серверы автоматизации (приложения, которые могут управляться другими приложениями) поддерживаются с помощью [карт диспетчеризации](../mfc/reference/dispatch-maps.md).

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
Используется для вызова серверов автоматизации из клиента автоматизации. При добавлении класса этот класс используется для создания строго типизированных классов для серверов автоматизации, предоставляющих библиотеку типов.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Исключение, полученное в результате ошибки при OLE Automation. Исключения автоматизации генерируются серверами службы автоматизации и перехватываются клиентами автоматизации.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
