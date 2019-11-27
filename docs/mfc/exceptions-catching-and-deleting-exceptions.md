---
title: Исключения. Перехват и удаление исключений
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 0142ffddfb391ae8da878d9e5fe34629cf16cb52
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246689"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений

В следующих инструкциях и примерах показано, как перехватывать и удалять исключения. Дополнительные сведения о ключевых словах **try**, **catch**и **throw** см. в [разделе C++ современные рекомендации по исключениям и обработке ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

Обработчики исключений должны удалять объекты исключений, которые они обрабатывали, так как сбой при удалении исключения приводит к утечке памяти всякий раз, когда этот код перехватывает исключение.

Блок **catch** должен удалить исключение, если:

- Блок **catch** создает новое исключение.

   Конечно, не следует удалять исключение, если повторно вызвать это исключение:

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Выполнение возвращается в блоке **catch** .

> [!NOTE]
>  При удалении `CException`используйте функцию-член `Delete` для удаления исключения. Не используйте ключевое слово **Delete** , так как оно может завершиться ошибкой, если исключение не находится в куче.

#### <a name="to-catch-and-delete-exceptions"></a>Перехват и удаление исключений

1. Для настройки блока **try** используется ключевое слово **try** . Выполните все инструкции программы, которые могут вызывать исключение в блоке **try** .

   Используйте ключевое слово **catch** для настройки блока **catch** . Разместите код обработки исключений в блоке **catch** . Код в блоке **catch** выполняется только в том случае, если код в блоке **try** создает исключение типа, указанного в операторе **catch** .

   На следующем рисунке показано, как обычно размещаются блоки **try** и **catch** :

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   При возникновении исключения управление передается в первый блок **catch** , объявление Exception которого соответствует типу исключения. Можно выборочно обрабатывайте различные типы исключений с последовательными блоками **catch** , как показано ниже:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Дополнительные сведения см. [в разделе исключения: преобразование из макросов исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>См. также:

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
