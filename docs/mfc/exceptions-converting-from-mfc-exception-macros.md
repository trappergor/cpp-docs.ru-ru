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
ms.openlocfilehash: 330f66b1f46542082637645ad53da016b434d4a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372018"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Исключения. Преобразование из макроса исключений MFC

Это продвинутая тема.

В этой статье объясняется, как преобразовать существующий код, написанный с макросами Microsoft Foundation Class - **TRY**, **CATCH**, **THROW**, и так далее - использовать ключевые слова, обрабатываемые исключениями, **попробуйте,** **поймают**и **бросят**. Будут рассмотрены следующие задачи:

- [Преимущества конверсии](#_core_advantages_of_converting)

- [Преобразование кода с макросами исключений для использования исключений C](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>Преимущества преобразования

Вероятно, вам не нужно конвертировать существующий код, хотя вы должны знать о различиях между макрореализациями в версии MFC 3.0 и реализациями в более ранних версиях. Эти различия и последующие изменения в поведении кода обсуждаются в [исключении: Изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

Основными преимуществами преобразования являются:

- Код, который использует ключевые слова обработки исключений, компилируется до немного меньшего размера. EXE или . Dll.

- Ключевые слова для обработки исключений являются более универсальными: они могут обрабатывать исключения любого типа данных, которые могут быть скопированы **(int,** **float,** **char**и так далее), в то время как макросы обрабатывают исключения только класса `CException` и классов, полученных из них.

Основное различие между макросами и ключевыми словами заключается в том, что код с использованием макросов "автоматически" удаляет пойманное исключение, когда исключение выходит за рамки. Код, использующий ключевые слова, не используется, поэтому необходимо явно удалить пойманное исключение. Для получения дополнительной информации см. [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md)

Другим отличием является синтаксис. Синтаксис для макросов и ключевых слов отличается в трех отношениях:

1. Макро аргументы и исключения декларации:

   Макровызов **CATCH** имеет следующий синтаксис:

   **CATCH (exception_class** *exception_class*, *exception_object_pointer_name* **)**

   Обратите внимание на запятую между именем класса и именем указателя объекта.

   Декларация исключений для ключевого слова **catch** использует этот синтаксис:

   **улов (exception_name** *exception_name* **exception_type)** *exception_type*

   В этом заявлении о декларации об исключении указывается тип исключения, обрабатывающего блоком catch.

2. Делимитация блоков улова:

   С макросов, **catch** макрос (с его аргументами) начинает первый блок улова; **AND_CATCH** макрос начинает последующие блоки ловли, а **END_CATCH** макрос завершает последовательность блоков улова.

   С ключевыми словами, **поймать** ключевое слово (с его исключением декларации) начинается каждый блок улова. Нет аналога **END_CATCH** макросу; блок улова заканчивается его заключительной скобкой.

3. Выражение броска:

   Макросы используют **THROW_LAST** для повторного броска текущего исключения. Ключевое слово **броска,** без аргумента, имеет тот же эффект.

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>Ведение преобразования

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>Для преобразования кода с помощью макросов для использования ключевых слов обработки исключений

1. Найдите все случаи макросов MFC **TRY**, **CATCH**, **AND_CATCH,** **END_CATCH,** **THROW**и **THROW_LAST.**

2. Заменить или удалить все случаи следующих макросов:

   **TRY** (Заменить его **попробовать**)

   **CATCH** (Заменить его **уловом)**

   **AND_CATCH** (Заменить его **уловом)**

   **END_CATCH** (Удалить его)

   **THROW** (Заменить его **броском)**

   **THROW_LAST** (Заменить его **броском)**

3. Изменяйте макроаргументы таким образом, чтобы они составляли действительные декларации об исключениях.

   Например, измените

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   значение

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Изменяйте код в блоках catch таким образом, чтобы он удалял объекты исключения по мере необходимости. Для получения дополнительной информации см. [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md)

Вот пример кода обработки исключений с использованием макросов исключений MFC. Обратите внимание, что, поскольку код в следующем `e` примере использует макросы, исключение удаляется автоматически:

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

В коде в следующем примере используются ключевые слова исключения C, поэтому исключение должно быть явно удалено:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Для получения дополнительной [информации см.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../mfc/exception-handling-in-mfc.md)<br/>
