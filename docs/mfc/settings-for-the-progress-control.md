---
title: Параметры элемента управления "Индикатор выполнения"
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 444dc45c816e0dfc2fd45bad999ad90c2acacc01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481787"
---
# <a name="settings-for-the-progress-control"></a>Параметры элемента управления "Индикатор выполнения"

Основные параметры для элемента управления хода выполнения ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) — это диапазон и текущей позиции. Диапазон представляет всю продолжительность операции. Текущая позиция представляет объем работ выполнила приложения работ по завершению операции. Любые изменения диапазона или положение для перевода элемента управления хода выполнения получает команду перерисовать себя.

По умолчанию имеет значение диапазона 0 - 100 и исходное положение имеет значение 0. Чтобы получить текущие параметры диапазона для индикатора хода выполнения, используйте [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) функция-член. Чтобы изменить диапазон, используйте [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) функция-член.

Чтобы установить позицию, используйте [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Чтобы получить текущую позицию без указания нового значения, используйте [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Например можно просто запросить состояние текущей операции.

Чтобы выполнить шаг текущую позицию индикатора хода выполнения, используйте [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Чтобы задать объем каждого шага, используйте [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>См. также

[Использование CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

