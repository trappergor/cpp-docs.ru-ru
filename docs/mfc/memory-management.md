---
title: Управление памятью
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: b5b91245d08c6c4a17c9ba96a0ca4dcf19932d9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461386"
---
# <a name="memory-management"></a>Управление памятью

Эта группа статей описывается, как пользоваться преимуществами общего назначения службы из Microsoft Foundation Class Library (MFC) связанных с управлением памятью. Выделение памяти можно разделить на две основные категории: кадров выделения и выделения памяти из кучи.

Основное различие между способами два выделения — это что с выделение кадров, которыми вы обычно работаете фактический объем памяти блок, пока с выделение кучи, всегда получают указатель на блок памяти. Другой основное отличие между двумя различными схемами является то, что объекты кадров будут автоматически удалены, пока кучи объекты должны быть явно удалены программистом.

Не MFC сведения об управлении памятью в приложениях для Windows, см. в разделе [управление памятью](https://msdn.microsoft.com/library/windows/desktop/aa366779) в пакете Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Выделение кадров](../mfc/memory-management-frame-allocation.md)

- [Выделение кучи](../mfc/memory-management-heap-allocation.md)

- [Выделение памяти для массива](../mfc/memory-management-examples.md)

- [Выделение памяти для массива из кучи](../mfc/memory-management-examples.md)

- [Выделение памяти для структуры данных](../mfc/memory-management-examples.md)

- [Выделение памяти для объекта](../mfc/memory-management-examples.md)

- [Изменяемые блоки памяти](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)

