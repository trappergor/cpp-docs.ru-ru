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
ms.openlocfilehash: e8c0f1feba566ef9b961edcfacb9124830f9851d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508619"
---
# <a name="exception-handling-in-mfc"></a>Обработка исключений в MFC

В этой статье объясняются механизмы обработки исключений, доступные в MFC. Доступны два механизма:

- C++исключения, доступные в MFC версии 3,0 и более поздних

- Макросы исключений MFC, доступные в MFC версий 1,0 и более поздних версиях

При написании нового приложения с помощью MFC следует использовать C++ механизм. Можно использовать механизм на основе макросов, если существующее приложение уже использует этот механизм широко.

Можно легко преобразовать существующий код для использования C++ исключений вместо макросов исключений MFC. Преимущества преобразования кода и рекомендаций см. в статье [исключения: Преобразование из макросов](../mfc/exceptions-converting-from-mfc-exception-macros.md)исключений MFC.

Если вы уже разработали приложение с помощью макросов исключений MFC, вы можете продолжать использовать эти макросы в существующем коде, используя C++ исключения в новом коде. Исключения статьи [: Изменения в макросах исключений в версии](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) 3,0 приводят к поправилам.

> [!NOTE]
>  Чтобы включить C++ обработку исключений в коде, выберите C++ включить исключения на странице Создание кода в папке CC++ /в диалоговом окне [страницы свойств](../build/reference/property-pages-visual-cpp.md) проекта или используйте параметр компилятора [/EHsc](../build/reference/eh-exception-handling-model.md) .

В этой статье рассматриваются следующие темы:

- [Когда следует использовать исключения](#_core_when_to_use_exceptions)

- [Поддержка исключений MFC](#_core_mfc_exception_support)

- [Дополнительные материалы об исключениях](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a>Когда следует использовать исключения

При вызове функции во время выполнения программы могут возникнуть три категории результатов: нормальное выполнение, ошибочное выполнение или аномальное выполнение. Каждая категория описана ниже.

- Нормальное выполнение

   Функция может выполняться в обычном режиме и возвращать. Некоторые функции возвращают код результата вызывающему объекту, который указывает результат функции. Возможные коды результата строго определены для функции и представляют диапазон возможных результатов функции. Код результата может указывать на успех или неудачу или даже указывать на определенный тип сбоя, который находится в пределах обычного диапазона ожиданий. Например, функция "состояние файла" может возвращать код, указывающий, что файл не существует. Обратите внимание, что термин "код ошибки" не используется, так как код результата представляет один из нескольких ожидаемых результатов.

- Ошибочное выполнение

   Вызывающий объект вызывает некоторую ошибку при передаче аргументов функции или вызывает функцию в неприемлемом контексте. Эта ситуация вызывает ошибку и должна обнаруживаться утверждением во время разработки программы. (Дополнительные сведения об утверждениях см. в разделе [CC++ /Assert](/visualstudio/debugger/c-cpp-assertions).)

- Аномальное выполнение

   Аномальное выполнение включает в себя ситуации, когда условия за пределами управления программой, такие как нехватка памяти или ошибки ввода-вывода, задают влияние на результат функции. Аномальные ситуации следует обрабатывать путем перехвата и генерации исключений.

Использование исключений особенно подходит для аварийного выполнения.

##  <a name="_core_mfc_exception_support"></a>Поддержка исключений MFC

Независимо от C++ того, используются ли исключения непосредственно или с помощью макросов исключений MFC, вы будете использовать `CException` [Класс CException](../mfc/reference/cexception-class.md) или производный объект, который может вызываться платформой или приложением.

В следующей таблице показаны стандартные исключения, предоставляемые MFC.

|Exception - класс|Значение|
|---------------------|-------------|
|[Класс CMemoryException](../mfc/reference/cmemoryexception-class.md)|Недостаточно памяти|
|[Класс CFileException](../mfc/reference/cfileexception-class.md)|Исключение файла|
|[Класс CArchiveException](../mfc/reference/carchiveexception-class.md)|Исключение архива или сериализации|
|[Класс CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)|Ответ на запрос неподдерживаемой службы|
|[Класс CResourceException](../mfc/reference/cresourceexception-class.md)|Исключение выделения ресурсов Windows|
|[Класс CDaoException](../mfc/reference/cdaoexception-class.md)|Исключения базы данных (классы DAO)|
|[Класс CDBException](../mfc/reference/cdbexception-class.md)|Исключения базы данных (классы ODBC)|
|[Класс COleException](../mfc/reference/coleexception-class.md)|исключения OLE|
|[Класс COleDispatchException](../mfc/reference/coledispatchexception-class.md)|Исключения диспетчеризации (Automation)|
|[Класс CUserException](../mfc/reference/cuserexception-class.md)|Исключение, которое предупреждает пользователя с помощью окна сообщения, а затем создает универсальный [Класс CException](../mfc/reference/cexception-class.md)|

> [!NOTE]
>  MFC поддерживает как C++ исключения, так и макросы исключений MFC. MFC не поддерживает непосредственно структурированные обработчики исключений Windows NT (SEH), как описано в разделе [структурированная обработка исключений](/windows/win32/debug/structured-exception-handling).

##  <a name="_core_further_reading_about_exceptions"></a>Дополнительные материалы об исключениях

В следующих статьях объясняется, как использовать библиотеку MFC для обработки исключений.

- [Исключения. Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Исключения. Анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md)

- [Исключения. Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Исключения. Создание исключений из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Исключения. Исключения базы данных](../mfc/exceptions-database-exceptions.md)

- [Исключения. Исключения OLE](../mfc/exceptions-ole-exceptions.md)

Следующие статьи сравнивают макросы исключений MFC с ключевыми C++ словами исключений и объясняют, как можно адаптировать код:

- [Исключения. Изменения макроса исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Исключения. Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Исключения. Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>См. также

[Обработка исключений С++](../cpp/cpp-exception-handling.md)<br/>
[Инструкции: Создание собственных классов пользовательских исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
