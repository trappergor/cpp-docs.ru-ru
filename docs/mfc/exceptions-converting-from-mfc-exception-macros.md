---
title: 'Исключения: Преобразование из макроса исключений MFC'
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
ms.openlocfilehash: 59b83438d5341fd6a139af64a2f365a739438741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394511"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Исключения: Преобразование из макроса исключений MFC

Это довольно сложная тема.

В этой статье объясняется, как преобразовать существующий код, написанный с макросами Microsoft Foundation Class — **попробуйте**, **CATCH**, **THROW**, и так далее — чтобы использовать обработку исключений C++ ключевые слова **попробуйте**, **catch**, и **throw**. Ниже приведен список разделов.

- [Преимущества преобразования](#_core_advantages_of_converting)

- [Преобразование кода с помощью макросов исключений, чтобы использовать исключения C++](#_core_doing_the_conversion)

##  <a name="_core_advantages_of_converting"></a> Преимущества преобразования

Вы, вероятно, не обязательно для преобразования существующего кода, несмотря на то, что следует учитывать различия между реализациями макрос с MFC версии 3.0 и реализации в более ранних версиях. Эти различия и последующие изменения в поведении кода рассматриваются в [исключения: Изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

Основные преимущества преобразования являются:

- Код, использующий ключевые слова обработки исключений C++ компилируется немного меньше. EXE-файла или. БИБЛИОТЕКА DLL.

- C++ Являются более гибкими ключевые слова обработки исключений: Они могут обрабатывать исключения любого типа данных, который может быть скопирован (**int**, **float**, **char**, и так далее), тогда как макросы обрабатывать исключения только класс `CException` и классы, производные от него.

Основное отличие между макросы и ключевые слова — это, код, используя макросы «автоматически» удаляет перехваченного исключения, когда исключение выходит из области. Код, используя ключевые слова — нет, поэтому необходимо явно удалить перехваченного исключения. Дополнительные сведения см. в статье [исключения: Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md).

Еще одно различие — это синтаксис. Синтаксис для макросов и ключевые слова отличается в трех аспектах:

1. Макрос аргументов и объявления исключения:

   Объект **CATCH** вызов макроса имеет следующий синтаксис:

   **CATCH (** *exception_class*, *exception_object_pointer_name* **)**

   Обратите внимание на запятую между именем класса и имя указателя объекта.

   Объявления исключения для **catch** ключевое слово используется следующий синтаксис:

   **catch(** *exception_type* *exception_name* **)**

   Этот оператор объявления исключения указывает тип исключения catch block дескрипторов.

2. Разграничение блоки catch:

   С макросами **CATCH** макрос (с ее аргументами) начинает первого блока catch; **AND_CATCH** макрос начинается блоках catch последующих и **END_CATCH** макрос останавливает последовательность из блоков catch.

   Ключевые слова **catch** ключевое слово (с его объявления исключения) начинается каждый блок catch. Отсутствует эквивалент для **END_CATCH** макрос; catch block заканчивается его закрывающей фигурной скобки.

3. Выражение throw:

   Используйте макросы **THROW_LAST** для повторного создания текущего исключения. **Throw** ключевое слово, без аргументов, имеет тот же эффект.

##  <a name="_core_doing_the_conversion"></a> Это преобразование

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>Преобразование кода, использование макросов использовать ключевые слова обработки исключений C++

1. Найдите все вхождения макросы MFC **попробуйте**, **CATCH**, **AND_CATCH**, **END_CATCH**, **THROW**, и **THROW_LAST**.

2. Замените или удалите все вхождения следующих макросов.

   **Попробуйте** (замените ее строкой **попробуйте**)

   **CATCH** (замените ее строкой **catch**)

   **AND_CATCH** (замените ее строкой **catch**)

   **END_CATCH** (Удалить)

   **ИСКЛЮЧЕНИЕ** (замените ее строкой **throw**)

   **THROW_LAST** (замените ее строкой **throw**)

3. Измените аргументов макроса, таким образом, чтобы они образуют допустимое исключение объявления.

   Например изменение

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   в

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Таким образом, чтобы он удаляет объекты исключений при необходимости, измените код в блоках catch. Дополнительные сведения см. в статье [исключения: Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md).

Ниже приведен пример кода обработки исключений, с помощью макроса исключений MFC. Обратите внимание, что поскольку код в следующем примере использует макросы, исключение `e` будет автоматически удалена:

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

В коде, в следующем примере используются ключевые слова исключений C++, поэтому исключения должны быть явно удалены:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Дополнительные сведения см. в разделе [исключения: Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)<br/>
