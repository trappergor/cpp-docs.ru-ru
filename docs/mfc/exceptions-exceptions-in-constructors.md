---
title: Исключения. Исключения в конструкторах
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 4089f4d44f03c7de3432f137b5d28f74189e1cb9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624618"
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения. Исключения в конструкторах

При возникновении исключения в конструкторе очистите все объекты и выделения памяти, сделанные до создания исключения, как описано в [исключениях: создание исключений из собственных функций](exceptions-throwing-exceptions-from-your-own-functions.md).

При возникновении исключения в конструкторе память для самого объекта уже была выделена на момент вызова конструктора. Таким образом, компилятор автоматически освобождает память, занятую объектом, после возникновения исключения.

Дополнительные сведения см. [в разделе исключения: освобождение объектов в исключениях](exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
