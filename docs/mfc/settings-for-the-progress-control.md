---
title: Параметры для управления ходом выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b11189e3e0a8381ade372841e6c7b25a5a9fa0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434639"
---
# <a name="settings-for-the-progress-control"></a>Параметры элемента управления "Индикатор выполнения"

Основные параметры для элемента управления хода выполнения ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) — это диапазон и текущей позиции. Диапазон представляет всю продолжительность операции. Текущая позиция представляет объем работ выполнила приложения работ по завершению операции. Любые изменения диапазона или положение для перевода элемента управления хода выполнения получает команду перерисовать себя.

По умолчанию имеет значение диапазона 0 - 100 и исходное положение имеет значение 0. Чтобы получить текущие параметры диапазона для индикатора хода выполнения, используйте [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) функция-член. Чтобы изменить диапазон, используйте [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) функция-член.

Чтобы установить позицию, используйте [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Чтобы получить текущую позицию без указания нового значения, используйте [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Например можно просто запросить состояние текущей операции.

Чтобы выполнить шаг текущую позицию индикатора хода выполнения, используйте [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Чтобы задать объем каждого шага, используйте [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>См. также

[Использование CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

