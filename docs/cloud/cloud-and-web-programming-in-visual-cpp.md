---
title: "Облачные и веб-программирование в Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-azure
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: "13"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aaf02f645ae61c75fb4ede3f5bc8e820039d1cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Облачное и веб-программирование в Visual C++
В C++ имеются несколько параметров для соединения с веб-узлом и облаком.  
  
 [Мобильные службы Microsoft Azure](http://www.windowsazure.com/develop/mobile/)  
 Предоставляет API-интерфейсы неуправляемого кода, которые можно использовать в приложениях для Магазина Windows или классических приложениях Windows для подключения к мобильным службам Microsoft Azure. Хотя большинство примеров на веб-сайте написаны на C#, также можно использовать и C++. Дополнительные сведения см. в разделе [Краткое руководство. Добавление мобильной службы с помощью C++](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).  

 [Клиентская библиотека хранилища Microsoft Azure для C++](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)  
 Клиентская библиотека хранилища Azure для C++ предоставляет универсальный интерфейс API для работы с хранилищем Azure, включая, но не ограничиваясь следующие возможности:

- Создание, чтение, удаление и список контейнеров больших двоичных объектов, таблиц и очередей.
- Создание, чтение, удалить список копирования больших двоичных объектов и плюс чтения и записи диапазонов больших двоичных объектов.
- INSERT, delete, replace, слияния и запросы к сущностям в таблице Azure.
- Поставить в очередь и вывода из очереди сообщений в очереди Azure.
- Неактивно список контейнеров, больших двоичных объектов, таблиц и очередей и задержкой запрос сущностей

[OneDrive API](https://dev.onedrive.com/README.htm)  
 OneDrive API предоставляет набор служб HTTP для подключения приложения к файлам и папкам в Office 365 и SharePoint Server 2016.

[Пакет C++ REST SDK (кодовое имя "Casablanca")](https://github.com/Microsoft/cpprestsdk)  
Предоставляет современный, между различными платформами, асинхронный API для взаимодействия со службами REST.

-   Выполнять вызовы REST к любой HTTP-сервера со встроенной поддержкой для синтаксического анализа документа JSON и сериализации
-   Поддерживает OAuth 1 и 2, включая перенаправление локального прослушивателя
-   Соединения Websockets от удаленной службы
-   Полностью асинхронных задач API в зависимости от PPL, включая встроенные threadpool

Поддерживает Windows Desktop (7 +), Windows Server (2012 +), универсальной платформы Windows, Linux, OSX, Android и iOS. 
  
[Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 Клиентский класс HTTP среды выполнения Windows, основанный на классе .NET Framework с тем же именем в пространстве имен System.Web. `HttpClient` полностью поддерживает асинхронной отправку и загрузку по протоколу HTTP, а также фильтры конвейера, позволяющие вставлять пользовательские обработчики HTTP в конвейер. Пакет Windows SDK содержит примеры фильтров для лимитных сетей, проверки подлинности OAuth и т. д. Для приложений, предназначенных для универсальной платформы Windows, мы рекомендуем использовать `Windows::Web:HttpClient` класса. 
  
[Интерфейс IXMLHTTPRequest2](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 Предоставляет COM-интерфейс неуправляемого кода, который можно использовать в приложениях для Магазина Windows или классических приложениях Windows для подключения к Интернету по протоколу HTTP и отправки вызовов GET, PUT и других команд HTTP. Дополнительные сведения см. в разделе [Пошаговое руководство: подключение с использованием задач и HTTP-запросов XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).  
  
[Windows Internet (WinInet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 Windows API, который можно использовать в классических приложениях Windows для подключения к Интернету.  
  
## <a name="see-also"></a>См. также  
 [Visual C++](../visual-cpp-in-visual-studio.md)   
 [Подключение к сети и веб-служб (приложения магазина Windows с помощью C#, VB, C++ и XAML)](http://msdn.microsoft.com/library/windows/apps/br229573.aspx)