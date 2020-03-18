---
title: Установка режима объекта CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: 79b499533196447898ce62ea9dc86c1674fc0302
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446418"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Установка режима объекта CStatusBarCtrl

Существует два режима для объекта `CStatusBarCtrl`: простой и непростой. В большинстве случаев элемент управления "строка состояния" будет содержать одну или несколько частей, а также текст и, возможно, значок или значки. Это называется непростым режимом. Дополнительные сведения об этом режиме см. [в разделе Инициализация частей объекта CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Однако бывают случаи, когда нужно отобразить только одну строку текста. В этом случае достаточно простого режима для ваших нужд. Чтобы изменить режим объекта `CStatusBarCtrl` на Simple, выполните вызов функции-члена [сетсимпле](../mfc/reference/cstatusbarctrl-class.md#setsimple) . Когда элемент управления "строка состояния" находится в простом режиме, задайте текст, вызвав функцию-член `SetText`, передав 255 в качестве значения параметра *нпане* .

Для определения режима, в котором находится объект `CStatusBarCtrl`, можно использовать функцию [простое_имя](../mfc/reference/cstatusbarctrl-class.md#issimple) .

> [!NOTE]
>  Если объект строки состояния изменяется с непростого на простой или наоборот, то окно немедленно перерисовывается и, если применимо, все определенные части автоматически восстанавливаются.

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
