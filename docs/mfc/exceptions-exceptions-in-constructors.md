---
title: Исключения. Исключения в конструкторах
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 23d1f6a9a3c76cc9c0c1d4aebd5c0b0ea45c3154
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472277"
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения. Исключения в конструкторах

При возникновении исключения в конструкторе, очистить все объекты и выделения памяти были внесены до возникновения исключения, как описано в [исключения: создание исключений из вашей собственной функции](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

При возникновении исключения в конструкторе, память для самого объекта уже выделен, к моменту вызова конструктора. Таким образом компилятор автоматически освободит память, занимаемая объектом, после исключения.

Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

