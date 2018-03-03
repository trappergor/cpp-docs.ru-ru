---
title: "Параметры для средства подсказки управления | Документы Microsoft"
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
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 406e35b6ab694ca972d4cd6add0dcca7586e5005
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-tool-tip-control"></a>Параметры для элемента управления всплывающей подсказки
Вы можете задать элемент управления "Всплывающая подсказка" ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) активным или неактивным. При установке его активным он отображается, когда курсор находится над инструментом. При установке его неактивным он не отображается, даже если курсор находится над инструментом. Вызовите [Activate](../mfc/reference/ctooltipctrl-class.md#activate) , чтобы активировать или деактивировать элемент управления "Всплывающая подсказка".  
  
 Вы можете задать активную всплывающую подсказку, чтобы при прохождении курсора над инструментом всплывающая подсказка отображалась независимо от того, активно или нет окно-владелец, с помощью стиля **TTS_ALWAYSTIP** . Если этот стиль не использовать, всплывающая подсказка будет отображаться только в том случае, если окно-владелец активно.  
  
 Большинство приложений содержат панели инструментов с инструментами, которые соответствуют командам меню. Для таких инструментов удобно, когда элемент управления "Всплывающая подсказка" отображает тот же текст, что и соответствующий пункт меню. Система автоматически удаляет символы амперсанда (&) сочетаний клавиш из всех строк, передаваемых для элемента управления всплывающей подсказки, если элемент управления имеет **TTS_NOPREFIX** стиля.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

