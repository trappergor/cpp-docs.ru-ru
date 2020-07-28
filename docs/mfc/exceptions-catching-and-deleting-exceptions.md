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
ms.openlocfilehash: 5c1edd4c5d31d9a0e8e5270d074d25b5dd129a0f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184251"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений

В следующих инструкциях и примерах показано, как перехватывать и удалять исключения. Дополнительные сведения о **`try`** **`catch`** **`throw`** ключевых словах, и см. в разделе [современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

Обработчики исключений должны удалять объекты исключений, которые они обрабатывали, так как сбой при удалении исключения приводит к утечке памяти всякий раз, когда этот код перехватывает исключение.

**`catch`** Блок должен удалить исключение, если:

- **`catch`** Блок создает новое исключение.

   Конечно, не следует удалять исключение, если повторно вызвать это исключение:

   [!code-cpp[NVC_MFCExceptions#3](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Выполнение возвращается в **`catch`** блоке.

> [!NOTE]
> При удалении `CException` используется `Delete` функция-член для удаления исключения. Не используйте **`delete`** ключевое слово, так как оно может завершиться ошибкой, если исключение не находится в куче.

#### <a name="to-catch-and-delete-exceptions"></a>Перехват и удаление исключений

1. Используйте **`try`** ключевое слово для настройки **`try`** блока. Выполните все инструкции программы, которые могут вызывать исключение в **`try`** блоке.

   Используйте **`catch`** ключевое слово для настройки **`catch`** блока. Разместите код обработки исключений в **`catch`** блоке. Код в **`catch`** блоке выполняется только в том случае, если код в **`try`** блоке вызывает исключение типа, указанного в **`catch`** инструкции.

   В следующей схеме показано **`try`** , как **`catch`** обычно упорядочиваются блоки:

   [!code-cpp[NVC_MFCExceptions#4](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   При возникновении исключения управление передается первому **`catch`** блоку, объявление исключения которого соответствует типу исключения. Можно выборочно обрабатывайте различные типы исключений с последовательными **`catch`** блоками, как показано ниже:

   [!code-cpp[NVC_MFCExceptions#5](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Дополнительные сведения см. [в разделе исключения: преобразование из макросов исключений MFC](exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
