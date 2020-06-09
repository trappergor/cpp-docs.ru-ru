---
title: Классы для отладки и работы с исключениями
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 6c7d1fc20556993c3c6690122786d7a767d895ad
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625939"
---
# <a name="debugging-and-exception-classes"></a>Классы для отладки и работы с исключениями

Эти классы обеспечивают поддержку отладки выделения динамической памяти и передачи сведений об исключениях из функции, в которой исключение вызывается для функции, в которой оно перехвачено.

Используйте классы [CDumpContext](reference/cdumpcontext-class.md) и [CMemoryState](reference/cmemorystate-structure.md) во время разработки, чтобы упростить отладку, как описано в разделе [Отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques). Используйте [крунтимекласс](reference/cruntimeclass-structure.md) для определения класса любого объекта во время выполнения, как описано в статье [доступ к сведениям о классе времени выполнения](accessing-run-time-class-information.md). Платформа использует `CRuntimeClass` для динамического создания объектов определенного класса.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
