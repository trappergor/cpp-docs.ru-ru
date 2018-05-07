---
title: Использование CAnimateCtrl | Документы Microsoft
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
ms.openlocfilehash: 5685d6aed00cd57f4329b3865f96fa75226d7cf6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-canimatectrl"></a>Использование CAnimateCtrl
Элемент управления анимации, представленный классом [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), — окно, которое отображает картинку в формате звука видео с чередованием (AVI) — стандартный формат видео и аудио Windows. AVI-clip представляет собой ряд кадров растрового изображения, такие как фильма.  
  
 Так как поток продолжает выполнение во время отображения AVI-clip, часто используются для управления "анимация" — для указания активности системы во время продолжительной операции. Например диалоговое окно Поиск Windows отображает скользящего увеличительное стекло как система выполняет поиск файла.  
  
 Элементы управления анимацией можно воспроизводить только простые ролики AVI и звук не поддерживаются. (Полный список ограничений см. в разделе [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Поскольку возможности управления "анимация" серьезно ограничены и подлежит изменению альтернативы, такие как управление MCIWnd следует использовать, если необходим элемент управления, чтобы предоставить воспроизведение мультимедиа и/или средства записи. Дополнительные сведения об элементе управления MCIWnd мультимедиа см.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Использование элемента управления "Анимация"](../mfc/using-an-animation-control.md)  
  
-   [Уведомления, отправленные элементами управления "Анимация"](../mfc/notifications-sent-by-animation-controls.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../mfc/controls-mfc.md)

