---
title: Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления им
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: 37dc7bc5a411ebab3737b87fd6977b26cff68178
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442217"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления им

Ниже приведен пример использования [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) .

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Создание CToolTipCtrl и работа с ними

1. Создайте объект `CToolTipCtrl`.

1. Вызовите [CREATE](../mfc/reference/ctooltipctrl-class.md#create) , чтобы создать общий элемент управления всплывающей подсказки Windows и присоединить его к объекту `CToolTipCtrl`.

1. Вызовите [аддтул](../mfc/reference/ctooltipctrl-class.md#addtool) , чтобы зарегистрировать инструмент с помощью элемента управления "Подсказка", чтобы информация, хранящаяся в подсказке, отображалась, когда курсор находится на инструменте.

1. Вызовите [сеттулинфо](../mfc/reference/ctooltipctrl-class.md#settoolinfo) , чтобы задать сведения, которые поддерживает всплывающая подсказка для средства.

1. Вызовите [сеттулрект](../mfc/reference/ctooltipctrl-class.md#settoolrect) , чтобы задать новый ограничивающий прямоугольник для инструмента.

1. Вызовите [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) , чтобы проверить точку, чтобы определить, находится ли он в ограничивающем прямоугольнике данного инструмента, и, если это так, получить сведения о средстве.

1. Вызовите [жеттулкаунт](../mfc/reference/ctooltipctrl-class.md#gettoolcount) , чтобы получить количество средств, зарегистрированных с помощью элемента управления "Подсказка".

## <a name="see-also"></a>См. также раздел

[Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
