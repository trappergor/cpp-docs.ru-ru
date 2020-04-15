---
title: Работа с элементом управления панели инструментов
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 371f1944fae655556bbc9f89d7ffcce7cc326e5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365247"
---
# <a name="working-with-the-toolbar-control"></a>Работа с элементом управления панели инструментов

В этой статье объясняется, как можно получить доступ к объекту [CToolBarCtrl,](../mfc/reference/ctoolbarctrl-class.md) лежащему в основе [CToolBar,](../mfc/reference/ctoolbar-class.md) для большего контроля над вашими панели инструментов. Это продвинутая тема.

## <a name="procedures"></a>Процедуры

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Для доступа к панели инструментов общий элемент управления, лежащий в основе объекта CToolBar

1. Позвоните [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl`возвращает ссылку на объект [CToolBarCtrl.](../mfc/reference/ctoolbarctrl-class.md) Ссылка может использоваться для вызова функций членов класса управления панелью инструментов.

> [!CAUTION]
> При `CToolBarCtrl` вызове **Функции Get** является безопасным, используйте осторожность, если вы называете **набор** функций. Это продвинутая тема. Обычно вам не нужно получать доступ к базовому элементу управления панели инструментов.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Элементы управления (общие элементы управления Windows)](../mfc/controls-mfc.md)

- [Общие сведения о панелях инструментов](../mfc/toolbar-fundamentals.md)

- [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)

- [Динамическое избавиние панели инструментов](../mfc/docking-and-floating-toolbars.md)

- [Советы инструмент инструментов панели инструментов](../mfc/toolbar-tool-tips.md)

- [Обновления оположении Flyby](../mfc/toolbar-tool-tips.md)

- [Обработка уведомлений всплывающих подсказок](../mfc/handling-tool-tip-notifications.md)

- Классы [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Обработка уведомлений о настройках](../mfc/handling-customization-notifications.md)

- [Несколько батончиков инструментов](../mfc/toolbar-fundamentals.md)

- [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)

- [Панели управления](../mfc/control-bars.md)

Для получения общей информации об использовании общих элементов управления Windows [см.](/windows/win32/Controls/common-controls-intro)

## <a name="see-also"></a>См. также раздел

[Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)
