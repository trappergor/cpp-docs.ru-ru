---
title: "Обработка исключений в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 544130f27fb01d0d29652087351c8a5bbc5bd5c7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="exception-handling-in-mfc"></a>Обработка исключений в MFC
В этой статье описываются способы обработки исключений, доступные в MFC. Доступны два механизма.  
  
-   Исключения C++, доступные в MFC версии 3.0 и более поздние версии  
  
-   Макросы исключений MFC, доступные в MFC версии 1.0 и более поздние версии  
  
 При написании нового приложения с помощью MFC, следует использовать механизм C++. Если существующее приложение уже широко использует этот механизм можно использовать механизм на основе макрос.  
  
 Можно легко преобразовать существующий код, чтобы использовать исключения C++ вместо макроса исключений MFC. Преимущества преобразования кода и рекомендации по таким образом описанное в статье [исключения: преобразование из макросов исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
 Если вы уже разработали приложения с помощью макроса исключений MFC, можно продолжить использование этих макросов в существующий код, при использовании исключения C++ в новом коде. Статья [исключения: изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) дает инструкции по таким образом.  
  
> [!NOTE]
>  Чтобы включить обработку исключений C++ в коде, выберите Включить C++ исключения на странице Создание кода в папке проекта C/C++ [страницы свойств](../ide/property-pages-visual-cpp.md) диалогового окна, или используйте /GX параметр компилятора. Значение по умолчанию — /GX-, который отключает обработку исключений.  
  
 В этой статье рассматриваются следующие темы:  
  
-   [Условия использования исключений](#_core_when_to_use_exceptions)  
  
-   [Поддержка исключений MFC](#_core_mfc_exception_support)  
  
-   [Дополнительные сведения об исключениях](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a>Условия использования исключений  
 Три категории результатов может возникнуть при вызове функции во время выполнения программы: нормальное выполнение, ошибочного выполнения или аварийное выполнение. Каждой категории описаны ниже.  
  
-   Обычное выполнение  
  
     Функция может выполнить обычно и возврата. Некоторые функции возвращают код результата вызывающему объекту, который указывает результат функции. Коды возможных результатов строго определенные функции и представляет диапазон возможных значений функции. Код результата можно указывает успешность или сбой или даже можно указать определенный тип сбоя, который находится в обычном диапазоне ожиданиям. Например состояние файла функция может возвращать код, указывающий, что файл не существует. Обратите внимание, не используется термин «код ошибки», так как код результата представляет один из многих исходов ожидаемого.  
  
-   Ошибочные выполнения  
  
     Вызывающий объект делает некоторые ошибки при передаче аргументов в функцию или вызывает функцию в недопустимом контексте. Такой ситуации приведет к ошибке, и он должен определяться с помощью утверждения во время разработки программ. (Дополнительные сведения об утверждениях см. в разделе [утверждения C/C++](/visualstudio/debugger/c-cpp-assertions).)  
  
-   Аномальное выполнение  
  
     Аномальное выполнение включает в себя ситуациях, где условия вне элемента управления программы, например нехватка памяти или ошибок ввода-вывода влияние на результат функции. Перехват и создание исключений должны обрабатываться нестандартной ситуации.  
  
 Использование исключений особенно хорошо подходят для выполнения нестандартных.  
  
##  <a name="_core_mfc_exception_support"></a>Поддержка исключений MFC  
 Использовать исключения C++ напрямую или использовать макросы исключений MFC, будет использовать [класса CException](../mfc/reference/cexception-class.md) или `CException`-производных объектов, которые могут быть созданы платформой или приложением.  
  
 В следующей таблице показаны стандартные исключения, предоставляемая MFC.  
  
|Exception - класс|Значение|  
|---------------------|-------------|  
|[Класс CMemoryException](../mfc/reference/cmemoryexception-class.md)|Нехватки памяти|  
|[Класс CFileException](../mfc/reference/cfileexception-class.md)|Исключение файлов|  
|[Класс CArchiveException](../mfc/reference/carchiveexception-class.md)|Исключение архива и сериализации|  
|[Класс CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)|Ответ на запрос службы не поддерживается|  
|[Класс CResourceException](../mfc/reference/cresourceexception-class.md)|Исключение выделения ресурсов Windows|  
|[Класс CDaoException](../mfc/reference/cdaoexception-class.md)|Исключения баз данных (классов DAO)|  
|[Класс CDBException](../mfc/reference/cdbexception-class.md)|Исключения баз данных (классов ODBC)|  
|[Класс COleException](../mfc/reference/coleexception-class.md)|исключения OLE|  
|[Класс COleDispatchException](../mfc/reference/coledispatchexception-class.md)|Исключения диспетчеризации (автоматизация)|  
|[Класс CUserException](../mfc/reference/cuserexception-class.md)|Исключение, которое предупреждает пользователя в окне сообщения, затем вызывает универсальный [CException-класс](../mfc/reference/cexception-class.md)|  
  
> [!NOTE]
>  MFC поддерживает исключения C++ и макросов исключений MFC. MFC непосредственно не поддерживает Windows NT структурированные обработчики исключений (SEH), как описано в [структурированную обработку исключений](http://msdn.microsoft.com/library/windows/desktop/ms680657).  
  
##  <a name="_core_further_reading_about_exceptions"></a>Дополнительные сведения об исключениях  
 Следующие статьи описывается с помощью библиотеки MFC для обработки исключений:  
  
-   [Исключения. Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [Исключения. Анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md)  
  
-   [Исключения. Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [Исключения. Создание исключений из собственных функций](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [Исключения. Исключения баз данных](../mfc/exceptions-database-exceptions.md)  
  
-   [Исключения. Исключения OLE](../mfc/exceptions-ole-exceptions.md)  
  
 Следующие статьи сравнения макросы исключений MFC с ключевые слова исключений C++ и объясняется, каким образом можно адаптировать код:  
  
-   [Исключения. Изменения макросов исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [Исключения. Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [Исключения. Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений с ++](../cpp/cpp-exception-handling.md)   
 [Практические советы. Создание собственных классах пользовательское исключение](http://go.microsoft.com/fwlink/p/?linkid=128045)

