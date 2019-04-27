---
title: Печать и предварительный просмотр печати
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 70740922ec7f2030d14eebee72144a373550aacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218720"
---
# <a name="printing-and-print-preview"></a>Печать и предварительный просмотр печати

MFC поддерживает печать и предварительный просмотр для документов программы с помощью класса [CView](../mfc/reference/cview-class.md). Для основных печати и предварительного просмотра, просто заменить класс представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член, который необходимо выполнить в любом случае. Эту функцию можно рисовать в представление на экране, контекст устройства принтера для фактические печатающие, или контекста устройства, которое имитирует принтера на экране.

Можно также добавить код для управления многостраничный документ печати и предварительного просмотра, разбивать на страницы на печатных документах и добавлять в них верхние и нижние колонтитулы.

Этот сборник статей описывается, как печати реализуется в Microsoft Foundation Class Library (MFC) и воспользоваться архитектурой печати, уже встроены в платформу. Статьи также объясняется, как MFC поддерживает простая реализация функции предварительного просмотра, и как можно использовать и изменять функциональные возможности.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Печать](../mfc/printing.md)

- [Архитектура предварительного просмотра](../mfc/print-preview-architecture.md)

- [Пример](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
