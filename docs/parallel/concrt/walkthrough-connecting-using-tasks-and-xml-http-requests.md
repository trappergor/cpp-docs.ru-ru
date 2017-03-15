---
title: "Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "подключение к веб-службам, приложения для Магазина Windows [C++]"
  - "IXMLHTTPRequest2 и задачи, пример"
  - "IXHR2 и задачи, пример"
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот пример показывает, как использовать интерфейсы [IXMLHTTPRequest2](http://msdn.microsoft.com/ru-ru/bbc11c4a-aecf-4d6d-8275-3e852e309908) и [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/ru-ru/aa4b3f4c-6e28-458b-be25-6cce8865fc71) вместе с задачами отправки HTTP\-запросов GET и POST к веб\-службе в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Путем объединения `IXMLHTTPRequest2` с задачами, можно написать код, который объединяется с другими задачами.  Например, можно использовать задачу загрузки в составе этих задач.  Задача загрузки может также реагировать на отмену работы.  
  
> [!TIP]
>  Можно также использовать C\+\+ REST SDK для выполнения HTTP\-запросов из приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], используя приложение С\+\+, или из настольного приложения С\+\+.  Дополнительные сведения см. в разделе [C\+\+ REST SDK \(Codename "Casablanca"\)](../../top/cpp-rest-sdk-codename-casablanca.md).  
  
 Дополнительные сведения о задачах см. в разделе [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Дополнительные сведения об использовании задач в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] см. в разделах [Asynchronous programming in C\+\+](http://msdn.microsoft.com/ru-ru/512700b7-7863-44cc-93a2-366938052f31) и [Создание асинхронных операций в C\+\+ для приложений для Магазина Windows](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
 В этом документе сначала показано, как создать `HttpRequest` и его вспомогательные классы.  Затем показано, как использовать этот класс из приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], использующего C\+\+ и XAML.  
  
 Более полный пример, в котором используется класс `HttpReader`, описанный в этом документе, см. в разделе [Разработка Bing Maps Trip Optimizer — приложения для Магазина Windows — с помощью JavaScript и C\+\+](../Topic/Developing%20Bing%20Maps%20Trip%20Optimizer,%20a%20Windows%20Store%20app%20in%20JavaScript%20and%20C++.md).  Другой пример, который использует `IXMLHTTPRequest2`, но не использует задач, см. в разделе [Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](http://msdn.microsoft.com/ru-ru/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35).  
  
> [!TIP]
>  `IXMLHTTPRequest2` и `IXMLHTTPRequest2Callback` \- интерфейсы, которые рекомендуется использовать в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Можно также адаптировать этот пример для использования в настольном приложении.  
  
## Обязательные компоненты  
  
## Определение классов HttpRequest, HttpRequestBuffersCallback и HttpRequestStringCallback  
 В случае использования интерфейса `IXMLHTTPRequest2` для создания веб\-запросов по протоколу HTTP необходимо реализовать интерфейс `IXMLHTTPRequest2Callback` для получения ответа сервера и реагирования на другие события.  В этом примере определяется класс `HttpRequest` для создания веб\-запросов и классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` для обработки ответов.  Классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` поддерживают класс `HttpRequest`; пользователь работает только с классом `HttpRequest` из кода приложения.  
  
 Методы `GetAsync`, `PostAsync` класса `HttpRequest` позволяет запустить операции HTTP GET и POST соответственно.  Эти методы используют класс `HttpRequestStringCallback` для чтения ответ сервера в виде строки.  Методы `SendAsync` и `ReadAsync` позволяют отправлять большое содержимое в блоках.  Эти методы возвращают значение [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) для представления операции.  Методы `GetAsync` и `PostAsync` создают значение `task<std::wstring>`, где часть `wstring` представляет ответ сервера.  Методы `SendAsync` и `ReadAsync` генерируют значения `task<void>`; эти задачи завершаются по завершению операций отправки и чтения.  
  
 Поскольку интерфейсы `IXMLHTTPRequest2` работают асинхронно, в этом примере используется [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md) для создания задачи, которая завершается после того, как объект обратного вызова завершает или отменяет операцию загрузки.  Класс `HttpRequest` создает основанное на задачах продолжение из этой задачи, чтобы установить конечный результат.  Класс `HttpRequest` использует основанное на задачах продолжение, чтобы убедиться, что задача продолжения выполняется, даже если предыдущая задача выдает ошибку или отменена.  Дополнительные сведения об основанных на задачах продолжениях см. в разделе [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Чтобы поддерживать отмену, классы `HttpRequest`, `HttpRequestBuffersCallback` и `HttpRequestStringCallback` используют токены отмены.  Классы `HttpRequestBuffersCallback` и `HttpRequestStringCallback` используют метод [concurrency::cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md), чтобы позволить событию завершения задачи реагировать на отмену.  Этот обратный вызов отмены прерывает загрузку.  Дополнительные сведения об отмене см. в разделе [Отмена](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
#### Определение класса HttpRequest  
  
1.  Используйте шаблон **Пустое приложение \(XAML\)** Visual C\+\+, чтобы создать пустой проект приложения XAML.  В этом примере проект назван `UsingIXMLHTTPRequest2`.  
  
2.  Добавьте в проект файл заголовка с именем HttpRequest.h и файл исходного кода с именем HttpRequest.cpp.  
  
3.  В pch.h добавьте следующий код:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#1](concrt-using-IXMLHTTPRequest2#1)]  
  
4.  В HttpRequest.h добавьте следующий код:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#2](concrt-using-IXMLHTTPRequest2#2)]  
  
5.  В HttpRequest.cpp добавьте следующий код:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#3](concrt-using-IXMLHTTPRequest2#3)]  
  
## Использование класса HttpRequest в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]  
 В этом разделе показано, как использовать класс `HttpRequest` в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Приложение предоставляет окно ввода, определяющее ресурс url\-адреса, и кнопки команд, которые выполняют операции GET и POST, и команду кнопки, которая отменяет текущую операцию.  
  
#### Использование класса HttpRequest  
  
1.  В MainPage.xaml, следует указать элемент [StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) следующим образом.  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A1](concrt-using-IXMLHTTPRequest2#A1)]  
  
2.  В MainPage.xaml.h добавьте эту директиву `#include`:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A2](concrt-using-IXMLHTTPRequest2#A2)]  
  
3.  В MainPage.xaml.h добавьте следующие переменные\-члены `private` в класс `MainPage`:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A3](concrt-using-IXMLHTTPRequest2#A3)]  
  
4.  В MainPage.xaml.h объявите `private` метод `ProcessHttpRequest`:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A4](concrt-using-IXMLHTTPRequest2#A4)]  
  
5.  В MainPage.xaml.cpp добавьте эти операторы `using`:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A5](concrt-using-IXMLHTTPRequest2#A5)]  
  
6.  В MainPage.xaml.cpp реализуйте методы `GetButton_Click`, `PostButton_Click` и `CancelButton_Click` класса `MainPage`.  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A6](concrt-using-IXMLHTTPRequest2#A6)]  
  
    > [!TIP]
    >  Если приложение не требует поддержки отмены, передайте [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md) к методам `HttpRequest::GetAsync` и `HttpRequest::PostAsync`.  
  
7.  В MainPage.xaml.cpp реализуйте метод `MainPage::ProcessHttpRequest`.  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A7](concrt-using-IXMLHTTPRequest2#A7)]  
  
8.  В свойствах проекта выберите **Компоновщик**, **Ввод**, укажите `shcore.lib` и `msxml6.lib`.  
  
 Здесь работающее приложение:  
  
 ![Запущенное приложение для Магазина Windows](../../parallel/concrt/media/concrt_usingixhr2.png "ConcRT\_UsingIXHR2")  
  
## Следующие действия  
 [Пошаговые руководства по среде выполнения с параллелизмом](../Topic/Concurrency%20Runtime%20Walkthroughs.md)  
  
## См. также  
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Отмена](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Asynchronous programming in C\+\+](http://msdn.microsoft.com/ru-ru/512700b7-7863-44cc-93a2-366938052f31)   
 [Создание асинхронных операций в C\+\+ для приложений для Магазина Windows](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](http://msdn.microsoft.com/ru-ru/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [Класс task \(среда выполнения с параллелизмом\)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)   
 [Класс task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md)   
 [IXMLHTTPRequest2](http://msdn.microsoft.com/ru-ru/bbc11c4a-aecf-4d6d-8275-3e852e309908)   
 [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/ru-ru/aa4b3f4c-6e28-458b-be25-6cce8865fc71)