---
title: 'Исключения: Использование макросов MFC и исключений C++'
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
ms.openlocfilehash: 00e88ddabf3a8e8b591bebae7ebc8ced0e1dc637
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297714"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Исключения: Использование макросов MFC и исключений C++

В этой статье рассматриваются особенности написания кода, использующего обработку исключений макросов MFC и ключевые слова обработки исключений C++.

В этой статье рассматриваются следующие темы:

- [Совместное использование ключевых слов исключение и макросы](#_core_mixing_exception_keywords_and_macros)

- [Блоки внутри блоков catch "try"](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> Совместное использование ключевых слов исключение и макросы

Можно смешивать макроса исключений MFC и ключевые слова исключений C++ в одной программе. Но нельзя смешивать макросы MFC с ключевые слова исключений C++ в одном блоке, поскольку макросы удаление объектов исключения автоматически при выходе из области, не поддерживает код, используя ключевые слова обработки исключений. Дополнительные сведения см. в статье [исключения: Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md).

Основное различие между макросы и ключевых слов является то, что макросы «автоматическое» удаление перехваченного исключения в случае исключения выходит за пределы области. Код с помощью ключевых слов не; исключения, перехватываемые в блоке catch должен быть явно удалены. Смешение макросов и ключевые слова исключений C++ может вызвать утечку памяти, когда объект исключения не удаляется или повреждения кучи, когда исключение удаляется дважды.

Следующий код, например, делает недействительным указатель исключение:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Проблема возникает, так как `e` удаляется после выхода из «внутренний» **CATCH** блока. С помощью **THROW_LAST** макрос вместо **THROW** оператор будет приводить к «внешний» **CATCH** блока для получения допустимого указателя:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Блоки внутри блоков Catch "try"

Невозможно повторно вызвать текущее исключение изнутри **попробуйте** блок, который находится внутри **CATCH** блока. Следующий пример является недопустимым:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Дополнительные сведения см. в разделе [исключения: Анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
