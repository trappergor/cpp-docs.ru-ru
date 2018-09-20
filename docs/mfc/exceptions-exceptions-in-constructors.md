---
title: 'Исключения: Исключения в конструкторах | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cab21255698c19046cfca185a0d8d7e7c530112
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421938"
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения. Исключения в конструкторах

При возникновении исключения в конструкторе, очистить все объекты и выделения памяти были внесены до возникновения исключения, как описано в [исключения: создание исключений из вашей собственной функции](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

При возникновении исключения в конструкторе, память для самого объекта уже выделен, к моменту вызова конструктора. Таким образом компилятор автоматически освободит память, занимаемая объектом, после исключения.

Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

