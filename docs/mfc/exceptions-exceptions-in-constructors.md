---
title: 'Исключения: Исключения в конструкторах'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 0b11f5be18879d5ad4b9e204bb02e18b4617c6b7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271018"
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения: Исключения в конструкторах

При возникновении исключения в конструкторе, очистить все объекты и выделения памяти были внесены до возникновения исключения, как описано в [исключения: Создание исключений из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

При возникновении исключения в конструкторе, память для самого объекта уже выделен, к моменту вызова конструктора. Таким образом компилятор автоматически освободит память, занимаемая объектом, после исключения.

Дополнительные сведения см. в разделе [исключения: Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
