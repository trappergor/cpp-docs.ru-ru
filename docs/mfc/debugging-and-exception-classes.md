---
title: Классы исключений для отладки и | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7c88c5d12f56318bbb37a825e28c2bfcbc132d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418181"
---
# <a name="debugging-and-exception-classes"></a>Классы для отладки и работы с исключениями

Эти классы обеспечивают поддержку для отладки динамическое выделение памяти, а также для передачи сведений об исключении из функции, где исключения функции где оно перехватывается.

Используйте классы [CDumpContext](../mfc/reference/cdumpcontext-class.md) и [CMemoryState](../mfc/reference/cmemorystate-structure.md) во время разработки для помощи при отладке, как описано в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques). Используйте [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) определить класс любого объекта во время выполнения, как описано в статье [доступ к сведениям о классе среды выполнения](../mfc/accessing-run-time-class-information.md). Инфраструктура использует `CRuntimeClass` для динамического создания объектов определенного класса.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

