---
title: Использование CAnimateCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a07b1f5a433ffa9525da8e8a7f942c9034d54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398460"
---
# <a name="using-canimatectrl"></a>Использование CAnimateCtrl

Элемент управления анимацией, представленный классом [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), — это окно, которое выводит клипа в формате звука видео с чередованием (AVI) — стандартный формат видео и аудио Windows. AVI-файла представляет собой ряд кадры растрового изображения, например фильм.

Так как ваш поток продолжает выполнение, пока отображается AVI-файла, часто применяются для элемента управления анимации — указывает действие системы во время длительной операции. Например диалоговое окно поиска Windows отображает скользящего увеличительное стекло как система выполняет поиск файла.

Элементы управления анимацией можно только воспроизведение простой AVI, и они не поддерживают звук. (Полный список ограничений, см. в разделе [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Так как возможности элемента управления анимации серьезно ограничены и может измениться, следует использовать альтернативы, например элемент управления MCIWnd, если необходим элемент управления для обеспечения воспроизведения мультимедиа и/или средства записи. Дополнительные сведения об элементе управления MCIWnd мультимедиа см.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Использование элемента управления "Анимация"](../mfc/using-an-animation-control.md)

- [Уведомления, отправленные элементами управления "Анимация"](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)

