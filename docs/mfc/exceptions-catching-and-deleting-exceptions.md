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
ms.openlocfilehash: 74022c8bc6af1d2cdf74fa452d4e0483637e542e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365517"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений

Следующие инструкции и примеры показывают, как поймать и удалить исключения. Для получения более подробной информации о **попытке,** **поймать**, и **бросить** ключевые слова, см [Современные рекомендации По кз с на исключенияи и обработки ошибок.](../cpp/errors-and-exception-handling-modern-cpp.md)

Обработчики исключений должны удалять объекты исключений, которые они обрабатывают, поскольку неспособность удалить исключение приводит к утечке памяти всякий раз, когда этот код ловит исключение.

Блок **catch** должен удалить исключение, когда:

- Блок **улова** бросает новое исключение.

   Конечно, вы не должны удалять исключение, если вы снова выбрасываете одно и то же исключение:

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Выполнение возвращается из блока **catch.**

> [!NOTE]
> При удалении `CException`функции `Delete` участника используйте функцию участника для удаления исключения. Не используйте ключевое слово **удаления,** потому что оно может вывести из строя, если исключение не находится на куче.

#### <a name="to-catch-and-delete-exceptions"></a>Поймать и удалить исключения

1. Используйте ключевое слово **try,** чтобы настроить блок **try.** Выполните любые операторы программы, которые могут выбросить исключение в **блоке try.**

   Используйте ключевое слово **catch,** чтобы настроить блок **catch.** Разместите код обработки исключений в **блоке catch.** Код в блоке **catch** выполняется только в том случае, если код в блоке **try** бросает исключение типа, указанного в заявлении **catch.**

   Следующий скелет показывает, как **попробовать** и **поймать** блоки, как правило, расположены:

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   При броске исключения элемент управления переходит к первому блоку **catch,** декларация исключения которой соответствует типу исключения. Можно выборочно обрабатывать различные типы исключений с последовательными блоками **ловли,** как указано ниже:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Для получения дополнительной [информации см.](../mfc/exceptions-converting-from-mfc-exception-macros.md)

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
