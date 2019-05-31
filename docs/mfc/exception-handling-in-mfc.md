---
title: Обработка исключений в MFC
ms.date: 11/04/2016
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
ms.openlocfilehash: 69bb5a9478120db322b5727af491be7943f44cbe
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449732"
---
# <a name="exception-handling-in-mfc"></a>Обработка исключений в MFC

Эта статья объясняет способы обработки исключений, доступные в MFC. Доступны два механизма:

- Исключения C++, доступные в MFC версии 3.0 и более поздние версии

- Макросы исключений MFC, доступные в MFC версии 1.0 и более поздние версии

Если вы создаете новое приложение с помощью MFC, следует использовать механизм C++. Если существующее приложение уже активно использует этот механизм можно использовать механизм на основе макрос.

Можно легко преобразовать существующий код, чтобы использовать исключения C++ вместо макроса исключений MFC. В этой статье описаны преимущества преобразования кода и рекомендации по таким образом [исключения: Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).

Если вы уже разработали приложения с помощью макроса исключений MFC, можно продолжить использование этих макросов в существующем коде, при использовании исключений C++ в новом коде. Статья [исключения: Изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) дает инструкции по таким образом.

> [!NOTE]
>  Чтобы включить обработку исключений C++ в коде, выберите Включить C++ исключения на странице "Создание кода" в папке проекта C/C++ [страницы свойств](../build/reference/property-pages-visual-cpp.md) диалогового окна, или используйте [/EHsc](../build/reference/eh-exception-handling-model.md) параметр компилятора.

В этой статье рассматриваются следующие темы:

- [Когда следует использовать исключения](#_core_when_to_use_exceptions)

- [Поддержка исключений MFC](#_core_mfc_exception_support)

- [Дополнительные сведения об исключениях](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a> Когда следует использовать исключения

Три категории результатов может возникнуть при вызове функции во время выполнения программы: обычное выполнение, ошибочные или аварийное выполнение. Каждая категория описан ниже.

- Обычное выполнение

   Функция может выполнения обычно и возвращения. Некоторые функции возвращают код результата, вызвавшему объекту, который указывает результат функции. Коды возможных результатов строго определенные функции и представляет диапазон возможных значений функции. Код результата, можно указать, успешно ли выполнен или даже можно указать определенный тип сбоя, который в обычном спектр ожиданий. Например состояние файла функция может возвращать код, указывающий, что файл не существует. Обратите внимание на то, что термин «код ошибки» не используется, поскольку код результата представляет собой одну из многих ожидаемые результаты.

- Ошибочные выполнения

   Вызывающий объект делает некоторые ошибки при передаче аргументов в функцию или вызывает функцию в недопустимом контексте. Это приводит к ошибке, и он должен определяться с помощью утверждения во время разработки программ. (Дополнительные сведения об утверждениях, см. в разделе [утверждения C/C++](/visualstudio/debugger/c-cpp-assertions).)

- Аномальное выполнение

   Аномальное выполнение также подразумевает ситуациях, где условия за пределами элемента управления программы, например нехватка памяти или ошибок ввода-вывода, влияют на результат функции. Аномальных ситуациях должна обрабатываться перехват и создание исключений.

С помощью исключений особенно хорошо подходят для Аномальное выполнение.

##  <a name="_core_mfc_exception_support"></a> Поддержка исключений MFC

Понадобится ли вы использовать исключения C++, напрямую или макроса исключений MFC, [класса CException](../mfc/reference/cexception-class.md) или `CException`-производных объектов, которые могут произойти платформой или приложением.

В следующей таблице показаны стандартных исключений, предоставляемых MFC.

|Exception - класс|Значение|
|---------------------|-------------|
|[Класс CMemoryException](../mfc/reference/cmemoryexception-class.md)|Памяти|
|[Класс CFileException](../mfc/reference/cfileexception-class.md)|Исключение файлов|
|[Класс CArchiveException](../mfc/reference/carchiveexception-class.md)|Архив/сериализации исключения|
|[Класс CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)|Ответ на запрос службы не поддерживается|
|[Класс CResourceException](../mfc/reference/cresourceexception-class.md)|Исключение выделения ресурсов Windows|
|[Класс CDaoException](../mfc/reference/cdaoexception-class.md)|Исключения базы данных (классы DAO)|
|[Класс CDBException](../mfc/reference/cdbexception-class.md)|Исключения базы данных (классы ODBC)|
|[Класс COleException](../mfc/reference/coleexception-class.md)|исключения OLE|
|[Класс COleDispatchException](../mfc/reference/coledispatchexception-class.md)|Исключения диспетчеризации (автоматизация)|
|[Класс CUserException](../mfc/reference/cuserexception-class.md)|Исключение, которое предупреждает пользователя в окне сообщения, то создается универсальный [CException-класс](../mfc/reference/cexception-class.md)|

> [!NOTE]
>  MFC поддерживает макросы исключений MFC и исключений C++. MFC не поддерживает непосредственно обработчики Windows NT структурированных исключений (SEH), как описано в [структурированную обработку исключений](/windows/desktop/debug/structured-exception-handling).

##  <a name="_core_further_reading_about_exceptions"></a> Дополнительные сведения об исключениях

В следующих статьях описывается с помощью библиотеки MFC для обработки исключений:

- [Исключения. Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Исключения. Анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md)

- [Исключения. Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Исключения. Создание исключений из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Исключения. Исключения базы данных](../mfc/exceptions-database-exceptions.md)

- [Исключения. Исключения OLE](../mfc/exceptions-ole-exceptions.md)

Со следующими статьями сравнения макроса исключений MFC с ключевые слова исключений C++ и объясняется, как можно адаптировать код:

- [Исключения. Изменения макроса исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Исключения. Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Исключения. Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>См. также

[Обработка исключений С++](../cpp/cpp-exception-handling.md)<br/>
[Инструкции: Создать собственные пользовательские классы исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
