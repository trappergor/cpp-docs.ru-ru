---
title: Классы для отладки и работы с исключениями
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 328d7a38c544b56f83ea3e8b1136b1122c4dfa14
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271415"
---
# <a name="debugging-and-exception-classes"></a>Классы для отладки и работы с исключениями

Эти классы обеспечивают поддержку для отладки динамическое выделение памяти, а также для передачи сведений об исключении из функции, где исключения функции где оно перехватывается.

Используйте классы [CDumpContext](../mfc/reference/cdumpcontext-class.md) и [CMemoryState](../mfc/reference/cmemorystate-structure.md) во время разработки для помощи при отладке, как описано в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques). Используйте [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) определить класс любого объекта во время выполнения, как описано в статье [доступ к сведениям о классе среды выполнения](../mfc/accessing-run-time-class-information.md). Инфраструктура использует `CRuntimeClass` для динамического создания объектов определенного класса.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
