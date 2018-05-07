---
title: Использование CStatusBarCtrl для создания объекта CStatusBarCtrl | Документы Microsoft
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
ms.openlocfilehash: 3b7f322003a36d89927930c0a57fd060078755f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>Использование CStatusBarCtrl для создания объекта CStatusBarCtrl
Вот пример типичного использования [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### <a name="to-use-a-status-bar-control-with-parts"></a>Чтобы использовать элемент управления строка состояния с частями  
  
1.  Создать `CStatusBarCtrl` объекта.  
  
2.  Вызовите [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) Чтобы задать минимальную высоту строки состояния область рисования.  
  
3.  Вызовите [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) Чтобы задать цвет фона строки состояния.  
  
4.  Вызовите [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) для задания количества разделов в состояние элемента управления и координаты правой границы каждой части панели.  
  
5.  Вызовите [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) для задания текста в данной части строки состояния. Сообщение объявляет недействительной измененную часть элемента управления, и, когда он в следующий раз получает сообщение `WM_PAINT`, отображается новый текст.  
  
 В некоторых случаях в строке состояния достаточно для отображения текста в строке. В этом случае вызвать [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Этот запрос помещает строки состояния в «простой» режим, в котором отображается одна строка текста.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

