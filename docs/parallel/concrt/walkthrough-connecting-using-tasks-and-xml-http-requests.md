---
title: "Пошаговое руководство: Подключение с использованием задач и HTTP-запросов XML | Документы Microsoft"
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
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e778c03368a634c349ec7c3ef241a29314cac4ea
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML
В этом примере показано, как использовать [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) и [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) интерфейсы вместе с задачами отправки запросов HTTP GET и POST к веб-службе в универсальной платформы Windows (UWP ) приложения. Путем объединения `IXMLHTTPRequest2` с задачами, можно написать код, который объединяется с другими задачами. Например, можно использовать задачу загрузки в цепочке этих задач. Задача загрузки может также реагировать на отмену работы.  
  
> [!TIP]
>  Можно также использовать C++ REST SDK для выполнения HTTP-запросов из приложения UWP, с помощью приложения C++ или на настольных приложений C++. Дополнительные сведения см. в разделе [C++ REST SDK (кодовое имя «Casablanca»)](https://github.com/Microsoft/cpprestsdk).  
  
 Дополнительные сведения о задачах см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Дополнительные сведения о том, как использовать задачи в приложении UWP в разделе [асинхронное программирование в C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) и [создание асинхронных операций в C++ для приложений UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
 В этом документе сначала показаны способы создания `HttpRequest` и его вспомогательных классов. Затем показано, как использовать этот класс из приложения UWP, использующего C++ и XAML.  
  
 Более полный пример, использующий `HttpReader` классов, описанных в этом документе в разделе [разработка Bing Maps Trip Optimizer, приложение магазина Windows на JavaScript и C++](http://msdn.microsoft.com/library/974cf025-de1a-4299-b7dd-c6c7bf0e5d30). Другой пример, использующий `IXMLHTTPRequest2` , но не использует задачи, в разделе [краткое руководство: подключение с помощью HTTP-запроса (IXMLHTTPRequest2), XML](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35).  
  
> [!TIP]
>  `IXMLHTTPRequest2` и `IXMLHTTPRequest2Callback` являются интерфейсами, которые рекомендуется для использования в приложении UWP. Можно также адаптировать этот пример для использования в приложении для настольных систем.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>Определение классов HttpRequest, HttpRequestBuffersCallback и HttpRequestStringCallback  
 В случае использования интерфейса `IXMLHTTPRequest2` для создания веб-запросов по протоколу HTTP необходимо реализовать интерфейс `IXMLHTTPRequest2Callback` для получения ответа сервера и реагирования на другие события. В этом примере определяется класс `HttpRequest` для создания веб-запросов и классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` для обработки ответов. Классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` поддерживают класс `HttpRequest`; пользователь работает только с классом `HttpRequest` из кода приложения.  
  
 Методы `GetAsync`, `PostAsync` класса `HttpRequest` позволяют запустить операции HTTP GET и POST, соответственно. Эти методы используют класс `HttpRequestStringCallback` для чтения ответа сервера в виде строки. Методы `SendAsync` и `ReadAsync` позволяют выполнять потоковую передачу большого содержимого в виде блоков. Эти методы возвращают [concurrency::task](../../parallel/concrt/reference/task-class.md) для представления операции. Методы `GetAsync` и `PostAsync` создают значение `task<std::wstring>`, где часть `wstring` представляет ответ сервера. Методы `SendAsync` и `ReadAsync` генерируют значения `task<void>`; эти задачи завершаются по завершению операций отправки и чтения.  
  
 Поскольку `IXMLHTTPRequest2` интерфейсы работают асинхронно, в этом примере используется [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) для создания задачи, выполняемой после объект обратного вызова завершает или отменяет операцию загрузки. Класс `HttpRequest` создает основанное на задаче продолжение из этой задачи, чтобы установить конечный результат. Класс `HttpRequest` использует основанное на задаче продолжение, чтобы убедиться, что задача продолжения выполняется, даже если предыдущая задача выдает ошибку или отменяется. Дополнительные сведения о продолжения на основе задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
 Чтобы поддерживать отмену, классы `HttpRequest`, `HttpRequestBuffersCallback` и `HttpRequestStringCallback` используют токены отмены. `HttpRequestBuffersCallback` И `HttpRequestStringCallback` классы используют [Concurrency::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) метод, чтобы позволить событию завершения задачи реагировать на отмену. Этот обратный вызов отмены прерывает загрузку. Дополнительные сведения об отмене см. в разделе [отмены](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
#### <a name="to-define-the-httprequest-class"></a>Определение класса HttpRequest  
  
1.  Используйте Visual C++ **пустое приложение (XAML)** шаблона для создания пустой проект приложения XAML. В этом примере проект называется `UsingIXMLHTTPRequest2`.  
  
2.  Добавьте в проект файл заголовка с именем HttpRequest.h и файл исходного кода с именем HttpRequest.cpp.  
  
3.  В pch.h добавьте следующий код:  
  
     [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]  
  
4.  В HttpRequest.h добавьте следующий код:  
  
     [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]  
  
5.  В HttpRequest.cpp добавьте следующий код:  
  
     [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]  
  
## <a name="using-the-httprequest-class-in-a-uwp-app"></a>Использование класса HttpRequest в приложении UWP  
 В этом разделе демонстрируется использование `HttpRequest` класс в приложении UWP. Приложение предоставляет окно ввода, определяющее ресурс URL-адреса, и кнопки команд, которые выполняют операции GET и POST, и команду кнопки, которая отменяет текущую операцию.  
  
#### <a name="to-use-the-httprequest-class"></a>Использование класса HttpRequest  
  
1.  В MainPage.xaml определить [StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) следующим образом.  
  
     [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]  
  
2.  В MainPage.xaml.h добавьте эту директиву `#include`:  
  
     [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]  
  
3.  В MainPage.xaml.h добавьте следующие переменные-члены `private` в класс `MainPage`:  
  
     [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]  
  
4.  В MainPage.xaml.h объявите `private` метод `ProcessHttpRequest`:  
  
     [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]  
  
5.  В MainPage.xaml.cpp добавьте эти операторы `using`:  
  
     [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]  
  
6.  В MainPage.xaml.cpp реализуйте методы `GetButton_Click`, `PostButton_Click` и `CancelButton_Click` класса `MainPage`.  
  
     [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]  
  
    > [!TIP]


    >  Если приложение не требует поддержки отмены, передайте [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) для `HttpRequest::GetAsync` и `HttpRequest::PostAsync` методы.  


  
7.  В MainPage.xaml.cpp реализуйте метод `MainPage::ProcessHttpRequest`.  
  
     [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]  
  
8.  В свойствах проекта в разделе **компоновщика**, **ввода**, укажите `shcore.lib` и `msxml6.lib`.  
  
 Здесь приводится работающее приложение:  
  
 ![Выполнение приложения среды выполнения Windows](../../parallel/concrt/media/concrt_usingixhr2.png "concrt_usingixhr2")  
  
## <a name="next-steps"></a>Следующие шаги  
 [Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)  
  
## <a name="see-also"></a>См. также  
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Асинхронное программирование в C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)   
 [Создание асинхронных операций в C++ для приложений UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [Краткое руководство: Подключение с помощью HTTP-запроса (IXMLHTTPRequest2), XML](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [Класс Task (среда выполнения параллелизма)](../../parallel/concrt/reference/task-class.md)   
 [Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)
