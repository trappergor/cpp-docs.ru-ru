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
ms.openlocfilehash: e09a7bd274c44df2da48bbc007a95802fadd8cf0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365418"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Установка режима объекта CStatusBarCtrl

Для объекта существует два `CStatusBarCtrl` режима: простой и непростой. В большинстве случаев, ваш статус бар управления будет иметь одну или несколько частей, наряду с текстом и, возможно, значок или значки. Это называется непростым режимом. Для получения дополнительной информации [Initializing the Parts of a CStatusBarCtrl Object](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)об этом режиме см.

Однако есть случаи, когда нужно отображать только одну строку текста. В этом случае простого режима достаточно для ваших нужд. Чтобы изменить режим `CStatusBarCtrl` объекта на простой, позвоните в функцию участника [SetSimple.](../mfc/reference/cstatusbarctrl-class.md#setsimple) После того, как управление панелью состояния находится `SetText` в простом режиме, установите текст, позвонив функции участника, передавая 255 в качестве значения для параметра *nPane.*

Функция IsSimple может быть с помощью функции [IsSimple,](../mfc/reference/cstatusbarctrl-class.md#issimple) чтобы определить, в каком режиме `CStatusBarCtrl` находится объект.

> [!NOTE]
> Если объект панели статуса изменяется с непростого на простой или наоборот, окно немедленно перерисовывается и, если это применимо, любые определенные части автоматически восстанавливаются.

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
