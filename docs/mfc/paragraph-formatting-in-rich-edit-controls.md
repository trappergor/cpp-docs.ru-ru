---
title: "Форматирование абзацев в элементы управления Rich Edit | Документы Microsoft"
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
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f0dc12d923f6f424fe84768b0d934d8dd7ff20b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"
Можно использовать функции-члены элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования абзацев и получить сведения о форматировании. Атрибуты форматирования абзаца относятся выравнивание, вкладки, отступы и нумерации.  
  
 Можно применить форматирование абзаца, используя [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) функции-члена. Чтобы определить текущее форматирование для выделенного текста абзаца, используйте [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) функции-члена. [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) использовать структуру с такие функции-члены для задания атрибутов абзаца. Одно из важные члены **PARAFORMAT** — **dwMask**. В `SetParaFormat`, **dwMask** указывает, какие атрибуты абзаца установит этот вызов функции. `GetParaFormat`Выводит атрибуты в первый абзац Выбор; **dwMask** указывает атрибуты, которые они единообразны во всем выделение.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

