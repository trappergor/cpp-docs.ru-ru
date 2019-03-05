---
title: Инициализация частей объекта CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: 0f00aee03a74799bf14563653b50c487ff001d02
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264343"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Инициализация частей объекта CStatusBarCtrl

По умолчанию строка состояния отображаются сведения о состоянии, с помощью отдельных панелей. Эти области (называемый также частей) может содержать строку текста, значок или оба.

Используйте [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) для определения, сколько частей и длину, строка состояния будет иметь. После создания частей строки состояния, выполнять вызовы [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) и [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) для установки текста или значка для определенной части строки состояния. После части был успешно установлен, элемент управления перерисовывается автоматически.

Следующий пример инициализирует существующий `CStatusBarCtrl` объекта (`m_StatusBarCtrl`) с помощью четырех панелей и затем задает значок (IDI_ICON1) и текст во второй части.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Дополнительные сведения о настройке режима `CStatusBarCtrl` объекта на простой, обратитесь к разделу [Установка режима объекта CStatusBarCtrl](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
