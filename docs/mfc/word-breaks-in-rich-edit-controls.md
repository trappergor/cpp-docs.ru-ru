---
title: Разрывы слов в элементы управления Rich Edit | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 373a30ed4a327cff99cb3cfce873707314608b57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="word-breaks-in-rich-edit-controls"></a>Разбиение слов с использованием элементов управления "Rich Edit"
Элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) вызывает функцию с именем «процедуры слово break» для поиска разрывов между словами и определить, где это может нарушить работу строк. Элемент управления использует эти сведения при выполнении операций переноса слов и при обработке сочетания клавиш CTRL + стрелка влево и CTRL + стрелка вправо. Приложение может отправлять сообщения в элементе управления rich edit для замены процедуры разбиения по умолчанию, для получения сведений о разбиения, а также для определения, какие строки определенный символ приходится на.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

