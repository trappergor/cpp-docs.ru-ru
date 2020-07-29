---
title: Очистка исключений CString
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 48c8f1c0040236a4f7bf27a2d5ad985ae343c03a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222060"
---
# <a name="cstring-exception-cleanup"></a>Очистка исключений CString

В предыдущих версиях MFC было важно очищать объекты [CString](../atl-mfc-shared/reference/cstringt-class.md) после использования. В MFC версии 3,0 и более поздней явная очистка больше не требуется.

В механизме обработки исключений C++, который теперь используется библиотекой MFC, не нужно беспокоиться об очистке после возникновения исключения. Сведения о том, как перехватывается стек, порожденный с помощью C++ "Unwind" после исключения, см. [в инструкциях try, catch и Throw](../cpp/try-throw-and-catch-statements-cpp.md). Даже если вы используете макрос **try** / **catch** вместо ключевых слов C++ **`try`** и **`catch`** , MFC использует механизм исключений c++ под, поэтому вам по-прежнему не нужно явно очищать.

## <a name="see-also"></a>См. также раздел

[Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Обработка исключений](../mfc/exception-handling-in-mfc.md)
