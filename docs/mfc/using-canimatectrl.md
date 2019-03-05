---
title: Использование CAnimateCtrl
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
ms.openlocfilehash: b967cc6dde6b4f639ef081b3821f6a7e5a2fe295
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287444"
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
