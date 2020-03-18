---
title: Инициализация частей объекта CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: a5b65a2bbb68eaa7058f3514bb95a5209a0e5e71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444452"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Инициализация частей объекта CStatusBarCtrl

По умолчанию в строке состояния отображаются сведения о состоянии с помощью отдельных панелей. Эти панели (также называемые частями) могут содержать текстовую строку, значок или и то, и другое.

Используйте [сетпартс](../mfc/reference/cstatusbarctrl-class.md#setparts) , чтобы определить, сколько частей и длина строки состояния будут иметь значение. После создания частей строки состояния выполните вызовы [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) и [сетикон](../mfc/reference/cstatusbarctrl-class.md#seticon) , чтобы задать текст или значок для определенной части строки состояния. После успешной установки части элемент управления автоматически перерисовывается.

В следующем примере инициализируется существующий объект `CStatusBarCtrl` (`m_StatusBarCtrl`) с четырьмя панелями, а затем задается значок (IDI_ICON1) и некоторый текст во второй части.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Дополнительные сведения о том, как установить режим объекта `CStatusBarCtrl` в значение SIMPLE, см. в разделе [Установка режима для объекта CStatusBarCtrl](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
