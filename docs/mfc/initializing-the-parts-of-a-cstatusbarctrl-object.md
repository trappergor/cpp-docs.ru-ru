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
ms.openlocfilehash: bd099a67d9f11cc3657a91b4141d3f18c6fa719d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621653"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Инициализация частей объекта CStatusBarCtrl

По умолчанию в строке состояния отображаются сведения о состоянии с помощью отдельных панелей. Эти панели (также называемые частями) могут содержать текстовую строку, значок или и то, и другое.

Используйте [сетпартс](reference/cstatusbarctrl-class.md#setparts) , чтобы определить, сколько частей и длина строки состояния будут иметь значение. После создания частей строки состояния выполните вызовы [SetText](reference/cstatusbarctrl-class.md#settext) и [сетикон](reference/cstatusbarctrl-class.md#seticon) , чтобы задать текст или значок для определенной части строки состояния. После успешной установки части элемент управления автоматически перерисовывается.

Следующий пример Инициализирует существующий `CStatusBarCtrl` объект ( `m_StatusBarCtrl` ) с четырьмя панелями, а затем задает значок (IDI_ICON1) и некоторый текст во второй части.

[!code-cpp[NVC_MFCControlLadenDialog#31](codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Дополнительные сведения о задании `CStatusBarCtrl` простого режима объекта см. в разделе [Установка режима для объекта CStatusBarCtrl](setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](using-cstatusbarctrl.md)<br/>
[Элементы управления](controls-mfc.md)
