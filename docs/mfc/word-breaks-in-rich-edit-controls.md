---
title: Разбиение слов с элементами управления Rich Edit | Документация Майкрософт
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
ms.openlocfilehash: f012897d968d108cb366126fc38992ff1dd11d0a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424616"
---
# <a name="word-breaks-in-rich-edit-controls"></a>Разбиение слов с использованием элементов управления "Rich Edit"

Элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) вызывает функцию с именем «procedure слово break» для поиска разрывов между словами и определить, где его можно переносить строку. Элемент управления использует эти сведения при выполнении операций переноса слов и при обработке сочетания клавиш CTRL + стрелка влево и CTRL + стрелка вправо. Приложение может отправлять сообщения в элементе управления rich edit для замены процедуру разбиения слов по умолчанию, для получения сведений разбиение текста на слова и определить, какие строки определенный символ ложится на.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

