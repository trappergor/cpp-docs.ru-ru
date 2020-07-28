---
title: Исключения. Преобразование из макроса исключений MFC
ms.date: 08/27/2018
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
ms.openlocfilehash: e8e7f47b66f4263ed55d73c0aac1fda73d72393c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87183816"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Исключения. Преобразование из макроса исключений MFC

Это дополнительная тема.

В этой статье объясняется, как преобразовать существующий код, написанный с помощью макросов Microsoft Foundation Class ( **try**, **catch**, **throw**и т. д.), для использования ключевых слов обработки исключений C++ **`try`** , **`catch`** и **`throw`** . Будут рассмотрены следующие задачи:

- [Преимущества преобразования](#_core_advantages_of_converting)

- [Преобразование кода с помощью макросов исключений для использования исключений C++](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>Преимущества преобразования

Вам, возможно, не придется преобразовывать существующий код, хотя следует помнить о различиях между реализациями макросов в MFC версии 3,0 и реализациях в более ранних версиях. Эти различия и последующие изменения в поведении кода обсуждаются в [исключениях: изменения в макросах исключений в версии 3,0](exceptions-changes-to-exception-macros-in-version-3-0.md).

Основные преимущества преобразования:

- Код, использующий ключевые слова обработки исключений C++, компилируется немного меньше. EXE или. Компоновки.

- Ключевые слова обработки исключений C++ являются более универсальными: они могут обрабатывать исключения любого типа данных, который может быть скопирован ( **`int`** , **`float`** , **`char`** и т. д.), в то время как макросы обрабатывают исключения только класса `CException` и классов, производных от него.

Основное различие между макросами и ключевыми словами состоит в том, что код, использующий макросы, автоматически удаляет Перехваченное исключение, когда исключение выходит из области действия. Код, использующий ключевые слова, не имеет, поэтому необходимо явно удалить Перехваченное исключение. Дополнительные сведения см. в статье [исключения: перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md).

Еще одно отличие — синтаксис. Синтаксис макросов и ключевых слов отличается в трех отношениях:

1. Аргументы макроса и объявления исключений:

   При вызове **catch** макрос имеет следующий синтаксис:

   **Catch (** *exception_class*, *exception_object_pointer_name* **)**

   Обратите внимание на запятую между именем класса и именем указателя объекта.

   В объявлении исключения для **`catch`** ключевого слова используется следующий синтаксис:

   **catch (** *exception_type* *exception_name* **)**

   Этот оператор объявления исключения указывает тип исключения, обрабатываемого блоком catch.

2. Разделители блоков catch:

   С помощью макросов макрос **catch** (с аргументами) начинает первый блок catch. макрос **AND_CATCH** начинает последующие блоки catch, а **END_CATCH** макрос завершает последовательность блоков catch.

   С помощью ключевых слов **`catch`** ключевое слово (вместе с его объявлением исключения) начинает каждый блок catch. Не существует аналога с **END_CATCH** макросом. блок catch заканчивается закрывающей фигурной скобкой.

3. Выражение Throw:

   Макросы используют **THROW_LAST** для повторного создания текущего исключения. **`throw`** Ключевое слово без аргумента имеет тот же результат.

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>Преобразование

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>Преобразование кода с помощью макросов для использования ключевых слов обработки исключений C++

1. Нахождение всех вхождений макросов MFC: **try**, **catch**, **AND_CATCH**, **END_CATCH**, **throw**и **THROW_LAST**.

2. Замените или удалите все вхождения следующих макросов:

   **Попробовать** (заменить **`try`** )

   **Перехватить** (заменить на **`catch`** )

   **AND_CATCH** (заменить на **`catch`** )

   **END_CATCH** (удалить)

   **Создать** (заменить на **`throw`** )

   **THROW_LAST** (заменить на **`throw`** )

3. Измените аргументы макроса таким образом, чтобы они формируют допустимые объявления исключений.

   Например, измените

   [!code-cpp[NVC_MFCExceptions#6](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   в

   [!code-cpp[NVC_MFCExceptions#7](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Измените код в блоках catch таким образом, чтобы при необходимости удалялись объекты исключений. Дополнительные сведения см. в статье [исключения: перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md).

Ниже приведен пример кода обработки исключений с помощью макросов исключений MFC. Обратите внимание, что поскольку код в следующем примере использует макросы, исключение `e` автоматически удаляется:

[!code-cpp[NVC_MFCExceptions#8](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

Код в следующем примере использует ключевые слова исключения C++, поэтому исключение должно быть явно удалено:

[!code-cpp[NVC_MFCExceptions#9](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Дополнительные сведения см. в разделе [исключения: использование макросов MFC и исключений C++](exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)<br/>
