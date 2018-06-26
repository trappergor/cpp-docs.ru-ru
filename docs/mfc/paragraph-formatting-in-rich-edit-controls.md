---
title: Форматирование абзацев в элементы управления Rich Edit | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9417fe9bab9b1fca8ec8292e27efc02afec5511c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929151"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"
Можно использовать функции-члены элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования абзацев и получить сведения о форматировании. Атрибуты форматирования абзаца относятся выравнивание, вкладки, отступы и нумерации.  
  
 Можно применить форматирование абзаца, используя [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) функции-члена. Чтобы определить текущее форматирование для выделенного текста абзаца, используйте [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) функции-члена. [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) использовать структуру с такие функции-члены для задания атрибутов абзаца. Одно из важные члены **PARAFORMAT** — *dwMask*. В `SetParaFormat`, *dwMask* указывает, какие атрибуты абзаца установит этот вызов функции. `GetParaFormat` Выводит атрибуты в первый абзац Выбор; *dwMask* указывает атрибуты, которые они единообразны во всем выделение.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

