---
title: Использование CStatusBarCtrl для создания объекта CStatusBarCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c68603eff0393d76af4e0617548e5bf1dd4aa63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413696"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>Использование CStatusBarCtrl для создания объекта CStatusBarCtrl

Ниже приведен пример типичное использование [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):

### <a name="to-use-a-status-bar-control-with-parts"></a>Чтобы использовать элемент управления строка состояния с частями

1. Создать `CStatusBarCtrl` объекта.

1. Вызовите [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) Если вы хотите задать минимальную высоту строки состояния области рисования.

1. Вызовите [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) задать цвет фона строки состояния.

1. Вызовите [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) задать число частей в строке элемента управления и координата правого края каждая часть состояния.

1. Вызовите [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) для задания текста в указанной части элемента управления строкой состояния. Сообщение объявляет недействительной часть элемента управления, который был изменен, поэтому она отображается новый текст, когда элемент управления затем получит сообщение WM_PAINT.

В некоторых случаях в строке состояния достаточно для отображения строки текста. В этом случае сделать вызов к [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Этот запрос помещает строки состояния в значение simple, режим, в котором отображается одна строка текста.

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

