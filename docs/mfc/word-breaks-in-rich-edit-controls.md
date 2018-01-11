---
title: "Разрывы слов в элементы управления Rich Edit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12ae5d682515a6f266b7e41a2ff89148ea98c0b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="word-breaks-in-rich-edit-controls"></a>Разбиение слов с использованием элементов управления "Rich Edit"
Элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) вызывает функцию с именем «процедуры слово break» для поиска разрывов между словами и определить, где это может нарушить работу строк. Элемент управления использует эти сведения при выполнении операций переноса слов и при обработке сочетания клавиш CTRL + стрелка влево и CTRL + стрелка вправо. Приложение может отправлять сообщения в элементе управления rich edit для замены процедуры разбиения по умолчанию, для получения сведений о разбиения, а также для определения, какие строки определенный символ приходится на.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

