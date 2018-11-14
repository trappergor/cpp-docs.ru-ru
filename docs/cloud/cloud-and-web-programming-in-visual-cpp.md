---
title: Облачное и веб-программирование в Visual C++
ms.date: 11/04/2016
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.openlocfilehash: 197d3d344d4be809c81f52f30e2462d35ebefbbe
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519637"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Облачное и веб-программирование в Visual C++

В C++ имеются несколько параметров для соединения с веб-узлом и облаком.

## <a name="cloud-programming-options"></a>Облачные возможности программирования

- [Мобильные службы Microsoft Azure](http://www.windowsazure.com/develop/mobile/)

  Предоставляет собственный API, которые можно использовать в приложениях универсальной платформы Windows (UWP) или классических приложениях Windows для подключения к мобильным службам Windows Azure. Хотя большинство примеров на веб-сайте написаны на C#, также можно использовать и C++. Дополнительные сведения см. в разделе [Краткое руководство. Добавление мобильной службы с помощью C++](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx).

- [Клиентская библиотека хранилища Microsoft Azure для C++](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

  Клиентская библиотека хранилища Azure для C++ предоставляет универсальный интерфейс API для работы со службой хранилища Azure, включая, но не ограничиваясь следующие возможности:

  - Создание, чтение, удаление и список контейнеров больших двоичных объектов, таблиц и очередей.
  - Создание, чтение, удаление, список и копирования больших двоичных объектов и чтение и запись диапазонов больших двоичных объектов.
  - INSERT, delete, replace, слияния и запрос сущностей в таблице Azure.
  - Поставить в очередь и вывода из очереди сообщений в очереди Azure.
  - Неактивно список контейнеров, больших двоичных объектов, таблиц и очередей и отложенного запрос сущностей

- [API OneDrive](https://dev.onedrive.com/README.htm)

  OneDrive API предоставляет набор служб HTTP для подключения приложения к файлам и папкам в Office 365 и SharePoint Server 2016.

- [Пакет C++ REST SDK (кодовое имя "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  Предоставляет современных, кросс платформенных, асинхронные API для взаимодействия со службами REST.

  - Выполнять вызовы REST для любого указанного сервера HTTP, со встроенной поддержкой для синтаксического анализа документов JSON и сериализация
  - Поддерживает OAuth 1 и 2, в том числе локальным перенаправлением прослушивателя
  - Устанавливают соединения Websockets от удаленной службы
  - Полностью асинхронная задача API, основанный на библиотеке параллельных Шаблонов, включая встроенные threadpool

  Поддерживает Windows Desktop (7 +), Windows Server (2012 или более поздней), универсальной платформы Windows, Linux, OSX, Android и iOS.

- [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/library/windows/apps/windows.web.http.httpclient.aspx)

  Клиентский класс HTTP среды выполнения Windows, основанный на классе .NET Framework с тем же именем в пространстве имен System.Web. `HttpClient` полностью поддерживает асинхронной отправку и загрузку по протоколу HTTP, а также фильтры конвейера, позволяющие вставлять пользовательские обработчики HTTP в конвейер. Пакет Windows SDK содержит примеры фильтров для лимитных сетей, проверки подлинности OAuth и т. д. Для приложений, предназначенных для универсальной платформы Windows, мы рекомендуем использовать `Windows::Web:HttpClient` класса.

- [Интерфейс IXMLHTTPRequest2](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

  Предоставляет собственный интерфейс COM, что можно использовать в приложениях среды выполнения Windows или классических приложениях Windows для подключения к Интернету по протоколу HTTP, и вызывать команду GET, PUT и других команд HTTP. Дополнительные сведения см. в разделе [Пошаговое руководство: подключение с использованием задач и HTTP-запросов XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinInet)](/windows/desktop/WinInet/portal)

  Windows API, который можно использовать в классических приложениях Windows для подключения к Интернету.

## <a name="see-also"></a>См. также

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[Сети и веб-служб](/windows/uwp/networking/)
