---
title: Форматирование абзацев в элементы управления Rich Edit | Документация Майкрософт
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
ms.openlocfilehash: 8258ff95fc91f6f29d424e77be95ce1b44f621ac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215825"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"
Можно использовать функции-члены элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования абзацев и получить сведения о форматировании. Атрибуты форматирования абзаца включают выравнивание, вкладки, отступы и нумерации.  
  
 Можно применить форматирование абзаца, с помощью [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) функция-член. Чтобы определить текущий абзац, форматирование для выделенного текста, используйте [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) функция-член. [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) структура будет использована в эти функции-члены для задания атрибутов абзаца. Один из важные члены **PARAFORMAT** — *dwMask*. В `SetParaFormat`, *dwMask* указывает, какие атрибуты абзаца установит этим вызовом функции. `GetParaFormat` Выводит атрибуты в первый абзац Выбор; *dwMask* указывает атрибуты, которые они единообразны во всем выделения.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

