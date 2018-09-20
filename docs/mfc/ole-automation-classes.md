---
title: Классы автоматизации OLE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea35e51296b2fc528657c4dd9f9b9b76b84aae83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391518"
---
# <a name="ole-automation-classes"></a>Классы автоматизации OLE

Эти классы поддерживают клиенты автоматизации (приложения, которые управляют другие приложения). Серверы автоматизации (приложения, которыми можно управлять другими приложениями) поддерживаются с помощью [съемы](../mfc/reference/dispatch-maps.md).

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
Использовать для вызова серверы автоматизации из клиента автоматизации. При добавлении класса, этот класс используется для создания строго типизированные классы для серверов автоматизации, которые предоставляют библиотеку типов.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Исключение, полученный в результате ошибки во время процесса OLE-автоматизации. Автоматизации исключения, порождаемые серверы автоматизации и перехватываются клиенты автоматизации.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

