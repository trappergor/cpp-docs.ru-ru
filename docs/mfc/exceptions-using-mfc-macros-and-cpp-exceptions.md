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
ms.openlocfilehash: 9e97eb545dedd3ac38dd93471f82aecc382717ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223178"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Исключения. Использование макросов MFC и исключений C++

В этой статье рассматриваются вопросы написания кода, использующего как макросы обработки исключений MFC, так и ключевые слова обработки исключений C++.

В этой статье рассматриваются следующие темы:

- [Сочетание ключевых слов и макросов исключений](#_core_mixing_exception_keywords_and_macros)

- [Блоки try внутри блоков catch](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>Сочетание ключевых слов и макросов исключений

В одной программе можно смешивать макросы исключений MFC и ключевые слова исключений C++. Однако нельзя смешивать макросы MFC с ключевыми словами исключений C++ в одном блоке, так как макросы удаляют объекты исключений автоматически при выходе из области, а код, использующий ключевые слова для обработки исключений, — нет. Дополнительные сведения см. в статье [исключения: перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md).

Основное различие между макросами и ключевыми словами заключается в том, что макросы автоматически удаляют Перехваченное исключение, когда исключение выходит из области действия. Код, использующий ключевые слова, не имеет; исключения, перехваченные в блоке catch, должны быть явно удалены. Смешивание макросов и ключевых слов исключений C++ может вызвать утечку памяти, если объект исключения не удален, или повреждение кучи, когда исключение будет удалено дважды.

Следующий код, например, делает недействительным указатель исключения:

[!code-cpp[NVC_MFCExceptions#10](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Проблема возникает потому, что `e` удаляется, когда выполнение передается из внутреннего блока **catch** . Использование макроса **THROW_LAST** вместо инструкции **throw** вызовет получение допустимого указателя для внешнего блока **catch** :

[!code-cpp[NVC_MFCExceptions#11](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>Блоки try внутри блоков catch

Невозможно повторно создать текущее исключение из **`try`** блока внутри блока **catch** . Следующий пример является недопустимым:

[!code-cpp[NVC_MFCExceptions#12](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Дополнительные сведения см. в разделе [исключения: Проверка содержимого исключений](exceptions-examining-exception-contents.md).

## <a name="see-also"></a>См. также статью

[Обработка исключений](exception-handling-in-mfc.md)
