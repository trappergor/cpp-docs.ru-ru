---
title: Исключения. Использование макросов MFC и исключений C++
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: afad5335bedf001329ecb401a8a16c663afb5571
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371589"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Исключения. Использование макросов MFC и исключений C++

В этой статье рассматриваются соображения для написания кода, в который используются как макросы обработки исключений MFC, так и ключевые слова обработки исключений.

В этой статье рассматриваются следующие темы:

- [Смешивание ключевых слов и макросов исключений](#_core_mixing_exception_keywords_and_macros)

- [Попробуйте блоки внутри блоков ловли](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>Смешивание ключевых слов исключений и макросов

В одной и той же программе можно смешивать макросы исключений MFC и ключевые слова исключения СЗ. Но нельзя смешивать макросы MFC с ключевыми словами исключения с КЗ в том же блоке, потому что макросы автоматически удаляют объекты исключений, когда они выходят за рамки, в то время как код, использующий ключевые слова обработки исключений, не выполняется. Для получения дополнительной информации см. [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md)

Основное различие между макросами и ключевыми словами заключается в том, что макросы "автоматически" удаляют пойманное исключение, когда исключение выходит за рамки. Код с использованием ключевых слов не делает; исключения, попавшие в блок улова, должны быть явно удалены. Смешивание макросов и ключевых слов исключения СЗ может привести к утечке памяти, когда объект исключения не удаляется, или к порче кучи, когда исключение удавливается дважды.

Следующий код, например, аннулирует указатель исключений:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Проблема возникает `e` из-за удаления, когда выполнение выходит из "внутреннего" блока **CATCH.** Использование **THROW_LAST** макроса вместо оператора **THROW** приведет к тому, что «внешний» блок **CATCH** получит действительный указатель:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>Попробуйте блоки внутри блоков catch

Вы не можете повторно выбросить текущее исключение из блока **try,** который находится внутри блока **CATCH.** Следующий пример является недействительным:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Для получения дополнительной [информации см.](../mfc/exceptions-examining-exception-contents.md)

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
