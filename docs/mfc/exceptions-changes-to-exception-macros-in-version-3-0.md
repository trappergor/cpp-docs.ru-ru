---
title: Исключения. Изменения макроса исключений в версии 3.0
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 25095257096efd869e237383c5cd202ae4e602c2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620171"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Исключения. Изменения макроса исключений в версии 3.0

Это дополнительная тема.

В MFC версии 3,0 и более поздних макросы обработки исключений были изменены для использования исключений C++. В этой статье рассказывается, как эти изменения могут повлиять на поведение существующего кода, использующего макросы.

В этой статье рассматриваются следующие темы:

- [Типы исключений и макрос CATCH](#_core_exception_types_and_the_catch_macro)

- [Повторная генерация исключений](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>Типы исключений и макрос CATCH

В более ранних версиях MFC макрос **catch** использовал сведения о типе среды выполнения MFC для определения типа исключения. тип исключения определяется другими словами на сайте перехвата. Однако с исключениями C++ тип исключения всегда определяется на вызываемом сайте типом создаваемого объекта исключения. Это приведет к несовместимости в редких случаях, когда тип указателя на создаваемый объект отличается от типа создаваемого объекта.

В следующем примере показан результат этой разницы между MFC версии 3,0 и более ранними версиями:

[!code-cpp[NVC_MFCExceptions#1](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Этот код ведет себя по-разному в версии 3,0, поскольку Управление всегда передается первому блоку **catch** с соответствующим объявлением исключения. Результат выражения Throw

[!code-cpp[NVC_MFCExceptions#19](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

вызывается как `CException*` , даже если он создан как `CCustomException` . Макрос **catch** в MFC версии 2,5 и более ранних версий использует `CObject::IsKindOf` для проверки типа во время выполнения. Так как выражение

[!code-cpp[NVC_MFCExceptions#20](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

имеет значение true, первый блок catch перехватывает исключение. В версии 3,0, которая использует исключения C++ для реализации многих макросов обработки исключений, второй блок catch соответствует созданному `CException` .

Такой код выглядит редко. Обычно он появляется, когда объект исключения передается в другую функцию, которая принимает универсальный метод `CException*` , выполняет предварительную обработку и, наконец, вызывает исключение.

Чтобы обойти эту проблему, переместите выражение Throw из функции в вызывающий код и вызовите исключение фактического типа, известного компилятору во время создания исключения.

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>Повторная генерация исключений

Блок catch не может вызывать тот же указатель исключения, который он вызвал.

Например, этот код был действителен в предыдущих версиях, но будет иметь непредвиденные результаты с версией 3,0:

[!code-cpp[NVC_MFCExceptions#2](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Использование инструкции **throw** в блоке catch приводит к `e` удалению указателя, чтобы внешний узел catch получил недопустимый указатель. Чтобы повторно создать исключение, используйте **THROW_LAST** `e` .

Дополнительные сведения см. в разделе [исключения: перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
