---
title: Исключения. Изменения макроса исключений в версии 3.0
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 82320b0c7ccd6766e016f0437633339f8f8f61d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365497"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Исключения. Изменения макроса исключений в версии 3.0

Это продвинутая тема.

В версии MFC 3.0 и позже макросы обработки исключений были изменены, чтобы использовать исключения с c.е. В этой статье рассказывается о том, как эти изменения могут повлиять на поведение существующего кода, используюго макросы.

В этой статье рассматриваются следующие темы:

- [Типы исключений и макрос CATCH](#_core_exception_types_and_the_catch_macro)

- [Исключения повторного броска](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>Типы исключений и CATCH Macro

В более ранних версиях MFC макрос **CATCH** использовал информацию о времени выполнения MFC для определения типа исключения; тип исключения определяется, другими словами, на месте улова. Однако, за исключением C, тип исключения всегда определяется на месте броска по типу брошенного объекта исключения. Это приведет к несовместимости в тех редких случаях, когда тип указателя на брошенный объект отличается от типа брошенного объекта.

Следующий пример иллюстрирует последствия этой разницы между версией MFC 3.0 и более ранними версиями:

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Этот код ведет себя по-разному в версии 3.0, потому что элемент управления всегда переходит к первому блоку **catch** с соответствующим исключением-декларацией. Результат выражения броска

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

брошенкак как `CException*`, даже если он `CCustomException`построен как . Макрос **CATCH** в версиях MFC `CObject::IsKindOf` 2.5 и более ранние использует для тестирования типа во время выполнения. Потому что выражение

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

верно, первый блок улова ловит исключение. В версии 3.0, которая использует исключения для реализации многих макросов обработки исключений, второй блок catch соответствует брошенной. `CException`

Код, как это редкость. Обычно появляется, когда объект исключения передается другой функции, которая принимает общий, `CException*`выполняет "предварительный бросок" обработки, и, наконец, бросает исключение.

Чтобы обойти эту проблему, переместите выражение броска из функции в код вызова и бросьте исключение фактического типа, известного компилятору на момент генерирования исключения.

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>Повторное бросивание исключений

Блок улова не может бросить тот же указатель исключения, что он поймал.

Например, этот код был действителен в предыдущих версиях, но будет иметь неожиданные результаты с версией 3.0:

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Использование **THROW** в блоке catch `e` приводит к удалению указателя, так что внешний участок будет получать недействительный указатель. Используйте **THROW_LAST,** `e`чтобы повторно бросить .

Для получения дополнительной [информации см.](../mfc/exceptions-catching-and-deleting-exceptions.md)

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
