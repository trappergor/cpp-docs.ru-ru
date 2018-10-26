---
title: 'Пошаговое руководство: Подключение с использованием задач и HTTP-запросов XML | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 074470d7ba7d9fa67e36587e420f4c67e5750ca6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057079"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML

В этом примере показано, как использовать [IXMLHTTPRequest2](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2) и [IXMLHTTPRequest2Callback](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback) интерфейсы вместе с задачами отправки запросов HTTP GET и POST для веб-службы в универсальной Windows платформы (UWP ) приложения. Путем объединения `IXMLHTTPRequest2` с задачами, можно написать код, который объединяется с другими задачами. Например, можно использовать задачу загрузки в цепочке этих задач. Задача загрузки может также реагировать на отмену работы.

> [!TIP]
>  Можно также использовать C++ REST SDK для выполнения HTTP-запросов из приложения UWP с помощью приложения C++ или на рабочем столе приложения C++. Дополнительные сведения см. в разделе [C++ REST SDK (кодовое название «Casablanca»)](https://github.com/Microsoft/cpprestsdk).

Дополнительные сведения о задачах см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Дополнительные сведения об использовании задач в приложении UWP см. в разделе [асинхронное программирование в C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) и [создание асинхронных операций в C++ для приложений UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

В этом документе сначала показаны способы создания `HttpRequest` и его вспомогательных классов. Затем показано, как использовать этот класс из приложения UWP, которое использует C++ и XAML.

Пример, использующий `IXMLHTTPRequest2` , но не использует задачи, см. в разделе [краткое руководство: подключение с помощью HTTP-запроса (IXMLHTTPRequest2), XML](/previous-versions/windows/apps/hh770550\(v=win.10\)).

> [!TIP]
>  `IXMLHTTPRequest2` и `IXMLHTTPRequest2Callback` являются интерфейсы, которые рекомендуется для использования в приложении универсальной платформы Windows. Можно также адаптировать этот пример для использования в приложении для настольных систем.

## <a name="prerequisites"></a>Предварительные требования

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>Определение классов HttpRequest, HttpRequestBuffersCallback и HttpRequestStringCallback

В случае использования интерфейса `IXMLHTTPRequest2` для создания веб-запросов по протоколу HTTP необходимо реализовать интерфейс `IXMLHTTPRequest2Callback` для получения ответа сервера и реагирования на другие события. В этом примере определяется класс `HttpRequest` для создания веб-запросов и классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` для обработки ответов. Классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` поддерживают класс `HttpRequest`; пользователь работает только с классом `HttpRequest` из кода приложения.

Методы `GetAsync`, `PostAsync` класса `HttpRequest` позволяют запустить операции HTTP GET и POST, соответственно. Эти методы используют класс `HttpRequestStringCallback` для чтения ответа сервера в виде строки. Методы `SendAsync` и `ReadAsync` позволяют выполнять потоковую передачу большого содержимого в виде блоков. Эти методы возвращают [concurrency::task](../../parallel/concrt/reference/task-class.md) для представления операции. Методы `GetAsync` и `PostAsync` создают значение `task<std::wstring>`, где часть `wstring` представляет ответ сервера. Методы `SendAsync` и `ReadAsync` генерируют значения `task<void>`; эти задачи завершаются по завершению операций отправки и чтения.

Так как `IXMLHTTPRequest2` интерфейсы работают асинхронно, в этом примере используется [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) для создания задачи, выполняемой после объект обратного вызова завершает или отменяет операцию загрузки. Класс `HttpRequest` создает основанное на задаче продолжение из этой задачи, чтобы установить конечный результат. Класс `HttpRequest` использует основанное на задаче продолжение, чтобы убедиться, что задача продолжения выполняется, даже если предыдущая задача выдает ошибку или отменяется. Дополнительные сведения о продолжениях на основе задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

Чтобы поддерживать отмену, классы `HttpRequest`, `HttpRequestBuffersCallback` и `HttpRequestStringCallback` используют токены отмены. `HttpRequestBuffersCallback` И `HttpRequestStringCallback` классы используют [Concurrency::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) способ включения события завершения задачи реагировать на отмену. Этот обратный вызов отмены прерывает загрузку. Дополнительные сведения об отмене см. в разделе [отмены](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

#### <a name="to-define-the-httprequest-class"></a>Определение класса HttpRequest

1. С помощью Visual C++ **пустое приложение (XAML)** шаблон, чтобы создать проект пустого XAML-приложения. В этом примере проект называется `UsingIXMLHTTPRequest2`.

1. Добавьте в проект файл заголовка с именем HttpRequest.h и файл исходного кода с именем HttpRequest.cpp.

1. В pch.h добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. В HttpRequest.h добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. В HttpRequest.cpp добавьте следующий код:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>Использование класса HttpRequest в приложении UWP

В этом разделе демонстрируется использование `HttpRequest` класс в приложении UWP. Приложение предоставляет окно ввода, определяющее ресурс URL-адреса, и кнопки команд, которые выполняют операции GET и POST, и команду кнопки, которая отменяет текущую операцию.

#### <a name="to-use-the-httprequest-class"></a>Использование класса HttpRequest

1. В MainPage.xaml определите [StackPanel](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) следующим образом.

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

    >  Если приложение не требует поддержки отмены, передайте [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) для `HttpRequest::GetAsync` и `HttpRequest::PostAsync` методы.

1. В MainPage.xaml.cpp реализуйте метод `MainPage::ProcessHttpRequest`.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. В свойствах проекта в разделе **компоновщика**, **ввода**, укажите `shcore.lib` и `msxml6.lib`.

Здесь приводится работающее приложение:

![Запущенное приложение среды выполнения Windows](../../parallel/concrt/media/concrt_usingixhr2.png "concrt_usingixhr2")

## <a name="next-steps"></a>Следующие шаги

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>См. также

[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Асинхронное программирование в C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[Создание асинхронных операций на C++ для приложений UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Краткое руководство: Подключение с помощью HTTP-запроса (IXMLHTTPRequest2), XML](/previous-versions/windows/apps/hh770550\(v=win.10\))
[класс task (среда выполнения с параллелизмом)](../../parallel/concrt/reference/task-class.md)<br/>
[Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)
