---
title: Реализация строки состояния в MFC
ms.date: 11/04/2016
f1_keywords:
- COldStatusBar
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
ms.openlocfilehash: 25848e4467a0d767c40ffb00a1bd4d50a062d3a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496288"
---
# <a name="status-bar-implementation-in-mfc"></a>Реализация строки состояния в MFC

Объект [CStatusBar](../mfc/reference/cstatusbar-class.md) объект представляет собой панель управления со строкой панелей вывода текста. Панелей вывода обычно используются как строки сообщения и в качестве индикаторов состояния. Примеры включают справочное сообщение строки меню, которые содержит краткое описание команды меню и индикаторов, показывающих состояние SCROLL LOCK, NUM LOCK и другие ключи.

Начиная с MFC версии 4.0, строки состояния реализуются с помощью класса [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), который инкапсулирует общий элемент управления в строке состояния. Для обеспечения обратной совместимости MFC сохраняет старые реализация строки состояния в классе `COldStatusBar`. Описана в документации для более ранних версиях MFC `COldStatusBar` под `CStatusBar`.

[CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), функция-член новые MFC 4.0, позволяет воспользоваться преимуществами поддержки Windows распространенных элемента управления для настройки и дополнительную функциональность в строке состояния. `CStatusBar` функции-члены обеспечивают большинство функций Windows стандартных элементов управления; Тем не менее, при вызове `GetStatusBarCtrl`, можно предоставить в строках состояния даже несколько характеристик строки состояния. При вызове `GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` объекта. Можно использовать эту ссылку для управления строки состояния.

На следующем рисунке показана строка состояния, в которой содержится несколько индикаторы.

![Строка состояния](../mfc/media/vc37dy1.gif "vc37dy1") строки состояния

Как и панели инструментов объект строки состояния внедряется в его родительское окно фрейма и будет создан автоматически при создании окна фрейма. Строка состояния, как и все панели элементов управления, будет удален автоматически также при уничтожении родительского фрейма.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Обновление на панель строки состояния](../mfc/updating-the-text-of-a-status-bar-pane.md)

- Классы MFC [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [Панели элементов управления](../mfc/control-bars.md)

- [Диалоговые панели](../mfc/dialog-bars.md)

- [Панели инструментов (реализация панели инструментов MFC)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>См. также

[Строки состояния](../mfc/status-bars.md)

