---
title: Печать и предварительный просмотр | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aad5c69f6466ea8803cb466c5e5529f3dce1340
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374457"
---
# <a name="printing-and-print-preview"></a>Печать и предварительный просмотр печати

MFC поддерживает печать и предварительный просмотр для документов программы с помощью класса [CView](../mfc/reference/cview-class.md). Для основных печати и предварительного просмотра, просто заменить класс представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член, который необходимо выполнить в любом случае. Эту функцию можно рисовать в представление на экране, контекст устройства принтера для фактические печатающие, или контекста устройства, которое имитирует принтера на экране.

Можно также добавить код для управления многостраничный документ печати и предварительного просмотра, разбивать на страницы на печатных документах и добавлять в них верхние и нижние колонтитулы.

Этот сборник статей описывается, как печати реализуется в Microsoft Foundation Class Library (MFC) и воспользоваться архитектурой печати, уже встроены в платформу. Статьи также объясняется, как MFC поддерживает простая реализация функции предварительного просмотра, и как можно использовать и изменять функциональные возможности.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Печать](../mfc/printing.md)

- [Архитектура предварительного просмотра](../mfc/print-preview-architecture.md)

- [Пример](../visual-cpp-samples.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
