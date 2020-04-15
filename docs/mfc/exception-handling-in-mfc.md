---
title: Обработка исключений в MFC
ms.date: 11/19/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
ms.openlocfilehash: d339ec98dabc6cb24fc7106c4c7238cd6a14a71b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365538"
---
# <a name="exception-handling-in-mfc"></a>Обработка исключений в MFC

В этой статье разъясняется механизмы обработки исключений, доступные в МФЦ. Доступны два механизма:

- Исключения сК, доступные в версии MFC 3.0 и более поздние

- Макросы исключения MFC, доступные в версиях MFC 1.0 и более поздние

Если вы пишете новое приложение с помощью MFC, вы должны использовать механизм СЗ. Механизм макроиспользования можно использовать, если существующее приложение уже широко использует этот механизм.

Можно легко преобразовать существующий код для использования исключений c'е вместо макросов исключения MFC. Преимущества преобразования кода и руководящих принципов для этого описаны в статье [Исключения: Преобразование из MFC Исключения Макрос](../mfc/exceptions-converting-from-mfc-exception-macros.md).

Если вы уже разработали приложение с использованием макросов исключения MFC, вы можете продолжить использование этих макросов в существующем коде, используя исключения C в новом коде. Статья [Исключения: Изменения в исключения Макрос в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) дает руководящие принципы для этого.

> [!NOTE]
> Для включения в код обработки исключений СЗ, выберите исключения включить C'на странице Generation кода в папке C/C' [страницы](../build/reference/property-pages-visual-cpp.md) диалогового окна страниц проекта или используйте опцию компилятора [/EHsc.](../build/reference/eh-exception-handling-model.md)

В этой статье рассматриваются следующие темы:

- [Условия использования исключений](#_core_when_to_use_exceptions)

- [Поддержка исключений MFC](#_core_mfc_exception_support)

- [Дальнейшее прочтение об исключениях](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a>Когда использовать исключения

Три категории исходов могут возникать, когда функция называется во время выполнения программы: нормальное выполнение, ошибочное выполнение или ненормальное выполнение. Каждая категория описана ниже.

- Нормальное исполнение

   Функция может выполняться нормально и возвращаться. Некоторые функции возвращают вызывающему код результата, который указывает на результат функции. Возможные коды результатов строго определены для функции и представляют диапазон возможных результатов функции. Код результата может указывать на успех или сбой или даже может указывать на определенный тип сбоя, который находится в пределах нормального диапазона ожиданий. Например, функция статуса файла может вернуть код, указывающий на то, что файл не существует. Обратите внимание, что термин "код ошибки" не используется, поскольку код результата представляет собой один из многих ожидаемых результатов.

- Ошибочное исполнение

   Звонящее совершает некоторую ошибку при передаче аргументов функции или вызывает функцию в неподходящем контексте. Эта ситуация вызывает ошибку, и она должна быть обнаружена утверждением во время разработки программы. (Для получения более подробной информации об утверждениях [см.](/visualstudio/debugger/c-cpp-assertions)

- Аномальное исполнение

   Аномальное выполнение включает ситуации, когда условия, не поддающиеся контролю программы, такие как низкая память или ошибки ввилистов, влияют на результат функции. Аномальные ситуации должны быть решены путем ловли и бросали исключения.

Использование исключений особенно подходит для аномального исполнения.

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a>Поддержка исключений MFC

Независимо от того, используете ли вы исключения c's напрямую или `CException`используете макросы исключения MFC, вы будете использовать [CException Class](../mfc/reference/cexception-class.md) или -производные объекты, которые могут быть брошены рамкой или вашим приложением.

В следующей таблице показаны предопределенные исключения, предоставляемые МФЦ.

|Exception - класс|Значение|
|---------------------|-------------|
|[Класс CMemoryException](../mfc/reference/cmemoryexception-class.md)|Непопамяти|
|[Класс CFileException](../mfc/reference/cfileexception-class.md)|Исключение файла|
|[Класс CArchiveException](../mfc/reference/carchiveexception-class.md)|Исключение архива/серизации|
|[Класс CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)|Ответ на запрос неподдерживаемой службы|
|[Класс CResourceException](../mfc/reference/cresourceexception-class.md)|Исключение выделения ресурсов Windows|
|[Класс CDaoException](../mfc/reference/cdaoexception-class.md)|Исключения из базы данных (классы DAO)|
|[Класс CDBException](../mfc/reference/cdbexception-class.md)|Исключения из базы данных (классы ODBC)|
|[Класс COleException](../mfc/reference/coleexception-class.md)|исключения OLE|
|[Класс COleDispatchException](../mfc/reference/coledispatchexception-class.md)|Исключения диспетчерской (автоматизации)|
|[Класс CUserException](../mfc/reference/cuserexception-class.md)|Исключение, которое предупреждает пользователя с полем сообщений, а затем бросает общий [класс CException](../mfc/reference/cexception-class.md)|

Начиная с версии 3.0, MFC использует исключения C++, но по-прежнему поддерживает более старые макросы обработки исключений, которые по форме схожи с исключениями C++. Хотя эти макросы не рекомендуется использовать в новом программировании, они по-прежнему поддерживаются для обеспечения обратной совместимости. В программах, в которых уже используются макросы, можно также свободно использовать исключения C++. Во время предварительной обработки макросы оценивают ключевые слова обработки исключений, определенные в реализации MSVC языка СЗ» в версии Visual C's 2.0. Начиная работать с исключениями C++, разработчик может оставить существующие макросы исключений. Для получения информации о смешивании макросов и обработке исключений с C и о преобразовании старого кода для [Exceptions: Converting from MFC Exception Macros](../mfc/exceptions-converting-from-mfc-exception-macros.md)использования нового механизма [см.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) Более ранние макросы исключений MFC, если вы их еще используете, возвращают ключевые слова исключений C++. См [Исключения: Изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md). MFC напрямую не поддерживает обработчики исключений windows NT структурированных исключений (SEH), о чем говорится в [структурированной обработке исключений.](/windows/win32/debug/structured-exception-handling)

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a>Далее читайте об исключениях

Следующие статьи объясняют использование библиотеки MFC для передачи исключений:

- [Исключения. Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Исключения. Анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md)

- [Исключения. Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Исключения. Создание исключений из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Исключения. Исключения баз данных](../mfc/exceptions-database-exceptions.md)

- [Исключения. Исключения OLE](../mfc/exceptions-ole-exceptions.md)

Следующие статьи сравнивают макросы исключения MFC с ключевыми словами исключения СЗ и объясняют, как можно адаптировать код:

- [Исключения. Изменения макроса исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Исключения. Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Исключения. Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>См. также раздел

[Современные рекомендации по се-практикам для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Как я: Создайте свои собственные индивидуальные классы исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
