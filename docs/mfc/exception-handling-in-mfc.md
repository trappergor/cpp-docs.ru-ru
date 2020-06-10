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
ms.openlocfilehash: ef827af413513d1a1753f84b1cb69a66f41f690c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618853"
---
# <a name="exception-handling-in-mfc"></a>Обработка исключений в MFC

В этой статье объясняются механизмы обработки исключений, доступные в MFC. Доступны два механизма:

- Исключения C++, доступные в MFC версии 3,0 и более поздних

- Макросы исключений MFC, доступные в MFC версий 1,0 и более поздних версиях

При написании нового приложения с помощью MFC следует использовать механизм C++. Можно использовать механизм на основе макросов, если существующее приложение уже использует этот механизм широко.

Можно легко преобразовать существующий код для использования исключений C++ вместо макросов исключений MFC. Преимущества преобразования кода и рекомендаций для этого описаны в статье [исключения: преобразование из макросов исключений MFC](exceptions-converting-from-mfc-exception-macros.md).

Если вы уже разработали приложение с помощью макросов исключений MFC, вы можете продолжать использовать эти макросы в существующем коде, используя исключения C++ в новом коде. В статье [исключения: изменения в макросах исключений в версии 3,0](exceptions-changes-to-exception-macros-in-version-3-0.md) приводятся рекомендации по их выполнению.

> [!NOTE]
> Чтобы включить обработку исключений C++ в коде, выберите включить исключения C++ на странице Создание кода в папке C/C++ диалогового окна [страницы свойств](../build/reference/property-pages-visual-cpp.md) проекта или используйте параметр компилятора [/EHsc](../build/reference/eh-exception-handling-model.md) .

В этой статье рассматриваются следующие темы:

- [Условия использования исключений](#_core_when_to_use_exceptions)

- [Поддержка исключений MFC](#_core_mfc_exception_support)

- [Дополнительные материалы об исключениях](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a>Когда следует использовать исключения

При вызове функции во время выполнения программы могут возникнуть три категории результатов: нормальное выполнение, ошибочное выполнение или аномальное выполнение. Каждая категория описана ниже.

- Нормальное выполнение

   Функция может выполняться в обычном режиме и возвращать. Некоторые функции возвращают код результата вызывающему объекту, который указывает результат функции. Возможные коды результата строго определены для функции и представляют диапазон возможных результатов функции. Код результата может указывать на успех или неудачу или даже указывать на определенный тип сбоя, который находится в пределах обычного диапазона ожиданий. Например, функция "состояние файла" может возвращать код, указывающий, что файл не существует. Обратите внимание, что термин "код ошибки" не используется, так как код результата представляет один из нескольких ожидаемых результатов.

- Ошибочное выполнение

   Вызывающий объект вызывает некоторую ошибку при передаче аргументов функции или вызывает функцию в неприемлемом контексте. Эта ситуация вызывает ошибку и должна обнаруживаться утверждением во время разработки программы. (Дополнительные сведения об утверждениях см. в разделе [утверждения C/C++](/visualstudio/debugger/c-cpp-assertions).)

- Аномальное выполнение

   Аномальное выполнение включает в себя ситуации, когда условия за пределами управления программой, такие как нехватка памяти или ошибки ввода-вывода, задают влияние на результат функции. Аномальные ситуации следует обрабатывать путем перехвата и генерации исключений.

Использование исключений особенно подходит для аварийного выполнения.

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a>Поддержка исключений MFC

Независимо от того, используете ли вы исключения C++ напрямую или используете макросы исключений MFC, вы будете использовать [Класс CException](reference/cexception-class.md) или `CException` производный объект, который может вызываться платформой или приложением.

В следующей таблице показаны стандартные исключения, предоставляемые MFC.

|Exception - класс|Значение|
|---------------------|-------------|
|[Класс CMemoryException](reference/cmemoryexception-class.md)|Недостаточно памяти|
|[Класс CFileException](reference/cfileexception-class.md)|Исключение файла|
|[Класс Карчивиксцептион](reference/carchiveexception-class.md)|Исключение архива или сериализации|
|[Класс Кнотсуппортедексцептион](reference/cnotsupportedexception-class.md)|Ответ на запрос неподдерживаемой службы|
|[Класс Кресаурцеексцептион](reference/cresourceexception-class.md)|Исключение выделения ресурсов Windows|
|[Класс Кдаоексцептион](reference/cdaoexception-class.md)|Исключения базы данных (классы DAO)|
|[Класс CDBException](reference/cdbexception-class.md)|Исключения базы данных (классы ODBC)|
|[Класс COleException](reference/coleexception-class.md)|исключения OLE|
|[Класс COleDispatchException](reference/coledispatchexception-class.md)|Исключения диспетчеризации (Automation)|
|[Класс CUserException](reference/cuserexception-class.md)|Исключение, которое предупреждает пользователя с помощью окна сообщения, а затем создает универсальный [Класс CException](reference/cexception-class.md)|

Начиная с версии 3.0, MFC использует исключения C++, но по-прежнему поддерживает более старые макросы обработки исключений, которые по форме схожи с исключениями C++. Хотя эти макросы не рекомендуется использовать в новом программировании, они по-прежнему поддерживаются для обеспечения обратной совместимости. В программах, в которых уже используются макросы, можно также свободно использовать исключения C++. Во время предварительной обработки макросы оценивают ключевые слова обработки исключений, определенные в реализации КОМПИЛЯТОРОМ MSVC языка C++ Visual C++ версии 2,0. Начиная работать с исключениями C++, разработчик может оставить существующие макросы исключений. Сведения о смешении макросов и обработке исключений C++, а также о преобразовании старого кода для использования нового механизма см. в статьях [исключения: использование макросов MFC и исключений](exceptions-using-mfc-macros-and-cpp-exceptions.md) и [исключений C++: преобразование из макросов исключений MFC](exceptions-converting-from-mfc-exception-macros.md). Более ранние макросы исключений MFC, если вы их еще используете, возвращают ключевые слова исключений C++. См. раздел [исключения: изменения в макросах исключений в версии 3,0](exceptions-changes-to-exception-macros-in-version-3-0.md). MFC не поддерживает непосредственно структурированные обработчики исключений Windows NT (SEH), как описано в разделе [структурированная обработка исключений](/windows/win32/debug/structured-exception-handling).

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a>Дополнительные материалы об исключениях

В следующих статьях объясняется, как использовать библиотеку MFC для обработки исключений.

- [Исключения. Перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md)

- [Исключения. Анализ содержимого исключений](exceptions-examining-exception-contents.md)

- [Исключения. Высвобождение объектов в исключениях](exceptions-freeing-objects-in-exceptions.md)

- [Исключения. Создание исключений из собственных функций](exceptions-throwing-exceptions-from-your-own-functions.md)

- [Исключения. Исключения баз данных](exceptions-database-exceptions.md)

- [Исключения. Исключения OLE](exceptions-ole-exceptions.md)

Следующие статьи сравнивают макросы исключений MFC с ключевыми словами исключений C++ и объясняют, как можно адаптировать код:

- [Исключения. Изменения макроса исключений в версии 3.0](exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Исключения. Преобразование из макроса исключений MFC](exceptions-converting-from-mfc-exception-macros.md)

- [Исключения. Использование макросов MFC и исключений C++](exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>См. также раздел

[Современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Инструкции. Создание собственных классов пользовательских исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
