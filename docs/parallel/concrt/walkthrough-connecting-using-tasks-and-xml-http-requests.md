---
title: Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: 2c627a543ec18702bf5358ff0170bec177fd7497
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032269"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML

Этот пример показывает, как использовать интерфейсы [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) и [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) вместе с задачами для отправки запросов HTTP GET и POST в веб-службу в приложении Universal Windows Platform (UWP). Путем объединения `IXMLHTTPRequest2` с задачами, можно написать код, который объединяется с другими задачами. Например, можно использовать задачу загрузки в цепочке этих задач. Задача загрузки может также реагировать на отмену работы.

> [!TIP]
> Вы также можете использовать SDK с ПОМОЩЬю HTTP-запросов от приложения UWP с помощью приложения «СИ» или из настольного приложения « C». Для получения более [C++ REST SDK (Codename "Casablanca")](https://github.com/Microsoft/cpprestsdk)подробной информации см.

Для получения дополнительной информации о задачах [см.](../../parallel/concrt/task-parallelism-concurrency-runtime.md) Для получения дополнительной информации о том, как использовать задачи в приложении [Creating Asynchronous Operations in C++ for UWP Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)UWP, [см.](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)

В этом документе сначала показаны способы создания `HttpRequest` и его вспомогательных классов. Затем он показывает, как использовать этот класс из приложения UWP, которое использует C и XAML.

Например, в `IXMLHTTPRequest2` использовании задач, но не использующих задачи, [см.](/previous-versions/windows/apps/hh770550\(v=win.10\))

> [!TIP]
> `IXMLHTTPRequest2`и `IXMLHTTPRequest2Callback` являются интерфейсами, которые мы рекомендуем для использования в приложении UWP. Можно также адаптировать этот пример для использования в приложении для настольных систем.

## <a name="prerequisites"></a>Предварительные требования

Поддержка UWP необязательна в Visual Studio 2017 и позже. Чтобы установить его, откройте Visual Studio Installer из меню Windows Start и выберите версию Visual Studio, который вы используете. Нажмите кнопку **«Изменить»** и убедитесь, что плитка **разработки UWP** проверена. В **рамках дополнительных компонентов** убедитесь, что **инструменты C'UWP** проверяются. Используйте v141 для Visual Studio 2017 или v142 для Visual Studio 2019.

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>Определение классов HttpRequest, HttpRequestBuffersCallback и HttpRequestStringCallback

В случае использования интерфейса `IXMLHTTPRequest2` для создания веб-запросов по протоколу HTTP необходимо реализовать интерфейс `IXMLHTTPRequest2Callback` для получения ответа сервера и реагирования на другие события. В этом примере определяется класс `HttpRequest` для создания веб-запросов и классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` для обработки ответов. Классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` поддерживают класс `HttpRequest`; пользователь работает только с классом `HttpRequest` из кода приложения.

Методы `GetAsync`, `PostAsync` класса `HttpRequest` позволяют запустить операции HTTP GET и POST, соответственно. Эти методы используют класс `HttpRequestStringCallback` для чтения ответа сервера в виде строки. Методы `SendAsync` и `ReadAsync` позволяют выполнять потоковую передачу большого содержимого в виде блоков. Эти методы каждый возврат [параллелизма::задача](../../parallel/concrt/reference/task-class.md) представлять операцию. Методы `GetAsync` и `PostAsync` создают значение `task<std::wstring>`, где часть `wstring` представляет ответ сервера. Методы `SendAsync` и `ReadAsync` генерируют значения `task<void>`; эти задачи завершаются по завершению операций отправки и чтения.

Поскольку `IXMLHTTPRequest2` интерфейсы действуют асинхронно, в этом примере используется [параллель::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) для создания задачи, которая завершается после завершения или отмены операции загрузки. Класс `HttpRequest` создает основанное на задаче продолжение из этой задачи, чтобы установить конечный результат. Класс `HttpRequest` использует основанное на задаче продолжение, чтобы убедиться, что задача продолжения выполняется, даже если предыдущая задача выдает ошибку или отменяется. Для получения дополнительной информации о [Task Parallelism](../../parallel/concrt/task-parallelism-concurrency-runtime.md) продолжениях задач см.

Чтобы поддерживать отмену, классы `HttpRequest`, `HttpRequestBuffersCallback` и `HttpRequestStringCallback` используют токены отмены. И `HttpRequestBuffersCallback` `HttpRequestStringCallback` классы используют [параллелизм::cancellation_token:::register_callback](reference/cancellation-token-class.md#register_callback) метод, позволяющий событию завершения задачи реагировать на отмену. Этот обратный вызов отмены прерывает загрузку. Для получения дополнительной информации об отмене, см [Отмена](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

### <a name="to-define-the-httprequest-class"></a>Определение класса HttpRequest

1. Из основного меню выберите **Файл** > **Новый** > **проект**.

1. Для создания пустого проекта приложения XAML используйте шаблон **«Бланк-приложение» (Universal Windows).** В этом примере проект называется `UsingIXMLHTTPRequest2`.

1. Добавьте в проект файл заголовка с именем HttpRequest.h и файл исходного кода с именем HttpRequest.cpp.

1. В pch.h добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. В HttpRequest.h добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. В HttpRequest.cpp добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>Использование класса HttpRequest в приложении UWP

В этом разделе показано, `HttpRequest` как использовать класс в приложении UWP. Приложение предоставляет окно ввода, определяющее ресурс URL-адреса, и кнопки команд, которые выполняют операции GET и POST, и команду кнопки, которая отменяет текущую операцию.

### <a name="to-use-the-httprequest-class"></a>Использование класса HttpRequest

1. В MainPage.xaml определите элемент [StackPanel](/uwp/api/windows.ui.xaml.controls.stackpanel) следующим образом.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

1. В MainPage.xaml.h добавьте эту директиву `#include`:

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

1. В MainPage.xaml.h добавьте следующие переменные-члены `private` в класс `MainPage`:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

1. В MainPage.xaml.h объявите `private` метод `ProcessHttpRequest`:

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

1. В MainPage.xaml.cpp добавьте эти операторы `using`:

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

1. В MainPage.xaml.cpp реализуйте методы `GetButton_Click`, `PostButton_Click` и `CancelButton_Click` класса `MainPage`.

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > Если ваше приложение не требует поддержки `HttpRequest::GetAsync` для отмены, пройдите `HttpRequest::PostAsync` [параллел: :cancellation_token::Нет](reference/cancellation-token-class.md#none) и методам.

1. В MainPage.xaml.cpp реализуйте метод `MainPage::ProcessHttpRequest`.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. В свойствах проекта, под **Linker,** `msxml6.lib` **Вход**, указать `shcore.lib` и .

Здесь приводится работающее приложение:

![Запущенное приложение Windows Runtime](../../parallel/concrt/media/concrt_usingixhr2.png "Запущенное приложение Windows Runtime")

## <a name="next-steps"></a>Next Steps

[Параллелизм Runtime Прохождение](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>См. также раздел

[Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Асинхронное программирование в СЗЗ](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[Создание асинхронных операций в СЗ для приложений UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Быстрый запуск: Подключение с помощью XML HTTP Запрос (IXMLHTTPRequest2)](/previous-versions/windows/apps/hh770550\(v=win.10\))
[класс задач (Время выполнения параллелизма)](../../parallel/concrt/reference/task-class.md)<br/>
[Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)
