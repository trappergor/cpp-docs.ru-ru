---
title: Разбиение слов с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
ms.openlocfilehash: efe4a0a2c06c14d913d43c51d1f0100f27c6a537
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632600"
---
# <a name="word-breaks-in-rich-edit-controls"></a>Разбиение слов с использованием элементов управления "Rich Edit"

Элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) вызывает функцию с именем «procedure слово break» для поиска разрывов между словами и определить, где его можно переносить строку. Элемент управления использует эти сведения при выполнении операций переноса слов и при обработке сочетания клавиш CTRL + стрелка влево и CTRL + стрелка вправо. Приложение может отправлять сообщения в элементе управления rich edit для замены процедуру разбиения слов по умолчанию, для получения сведений разбиение текста на слова и определить, какие строки определенный символ ложится на.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

