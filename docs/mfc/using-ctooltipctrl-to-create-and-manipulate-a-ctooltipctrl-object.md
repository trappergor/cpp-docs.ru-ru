---
title: Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2143ea37cfe9448e43aacfa75622beab93d2fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления им
Ниже приведен пример [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) использования:  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Для создания и управления CToolTipCtrl  
  
1.  Создать `CToolTipCtrl` объекта.  
  
2.  Вызовите [создать](../mfc/reference/ctooltipctrl-class.md#create) для создания общих управления всплывающей подсказки Windows и присоединить его к `CToolTipCtrl` объекта.  
  
3.  Вызовите [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) для регистрации средство для отображения сведений, хранящихся в подсказке, когда курсор находится в средстве управления всплывающей подсказки.  
  
4.  Вызовите [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) для задания данных, поддерживающий во всплывающей подсказке инструмента.  
  
5.  Вызовите [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) для установки нового ограничивающего прямоугольника для средства.  
  
6.  Вызовите [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) для тестирования точки, чтобы определить, является ли она внутри ограничивающего прямоугольника данное средство и если да, получить информацию об этом инструменте.  
  
7.  Вызовите [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) Чтобы получить число средств зарегистрирован с элементом управления всплывающей подсказки.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

