---
title: Печать в элементах управления Rich Edit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 882ed020b37ec60c072c8983c61bbe564bb74b04
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217692"
---
# <a name="printing-in-rich-edit-controls"></a>Печать в элементах управления "Rich Edit"
Чтобы узнать, элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для подготовки к просмотру выходные данные для заданного устройства, такие как принтер. Можно также указать, что устройство вывода, для которого элемент управления rich edit форматирует его текст.  
  
 Чтобы форматировать часть содержимого элемента управления "rich edit" для конкретного устройства, можно использовать [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) функция-член. [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) структура, используемая с этой функцией указывает диапазон текста для форматирования, а также контекст устройства (DC) для целевого устройства.  
  
 После форматирования текста для вывода устройства, можно отправлять выходные данные на устройстве с помощью [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) функция-член. С помощью многократно `FormatRange` и `DisplayBand`, приложение, которое выводит содержимое элемента управления форматированным редактированием можно реализовать чередование. (Чередования — деление на более мелкие части выходных данных для печати).  
  
 Можно использовать [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) функции-члена для указания целевого устройства, для которого элемент управления rich edit форматирует его текст. Эта функция полезна для WYSIWYG (очевидно, что вы получаете) форматирование, в котором приложение размещает текст с помощью метрик шрифтов принтер по умолчанию вместо экрана.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

