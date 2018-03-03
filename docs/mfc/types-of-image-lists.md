---
title: "Типы списков изображений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84a2118978d5ebd722d4fe56cdeec2aa0f74a94e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-image-lists"></a>Типы списков изображений
Существует два типа списков изображений ([CImageList](../mfc/reference/cimagelist-class.md)): nonmasked и скрытый. «Список nonmasked изображений» состоит из цвета точечного рисунка, который содержит один или несколько образов. «Список скрытого изображения» состоит из двух рисунков одинакового размера. Во-первых, цветовой битовой карты с изображениями и второй — монохромный точечный рисунок, содержащий ряд маски — один для каждого изображения в первом растрового изображения.  
  
 Одной из перегрузок **создать** функции-члена принимает флаг, указывающий, скрыт ли список изображений. (Другие перегрузки создать списки скрытого изображения).  
  
 При рисовании nonmasked изображения, просто он копируется в контексте целевого устройства; то есть он нарисован поверх цвет фона контекста устройства. При рисовании скрытого изображения, биты изображения, объединяются с биты маски, формирующего обычно прозрачные области в битовой карте, где показан цвет фона целевой контекст устройства через. При рисовании скрытого изображения, можно указать несколько стили рисования. Например можно указать, выполняет изображение дизеринг для указания выбранного объекта.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

