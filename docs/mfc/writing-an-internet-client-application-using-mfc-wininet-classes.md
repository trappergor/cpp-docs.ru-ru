---
title: "Создание клиентских приложений в Интернете с использованием классов MFC WinInet | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07b97d4af18ff560a48aadb3ba71b61609f82a85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>Создание клиентских приложений в Интернете с использованием классов MFC WinInet
Основой каждой клиентских веб-приложений является Интернет-сеанс. Реализация MFC сеансов Интернета как объекты класса [CInternetSession](../mfc/reference/cinternetsession-class.md). С помощью этого класса, можно создать один сеанс Интернета или несколько параллельных сеансов.  
  
 Для обеспечения связи с сервером, необходимо [CInternetConnection](../mfc/reference/cinternetconnection-class.md) объекта, а также `CInternetSession`. Можно создать `CInternetConnection` с помощью [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), или [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Каждый из этих вызовов определяется тип протокола. Эти вызовы не открывайте файл на сервере для чтения или записи. Если вы собираетесь чтения или записи данных, необходимо открыть файл как отдельный шаг.  
  
 Для большинства сеансов Интернета `CInternetSession` объект работает вручную в наличии с [классе CInternetFile](../mfc/reference/cinternetfile-class.md) объекта:  
  
-   Для Интернет-сеанс, необходимо создать экземпляр [CInternetSession](../mfc/reference/cinternetsession-class.md).  
  
-   Если Интернет-сеанс считывает или записывает данные, необходимо создать экземпляр `CInternetFile` (или его подклассов [CHttpFile](../mfc/reference/chttpfile-class.md) или [CGopherFile](../mfc/reference/cgopherfile-class.md)). Самый простой способ чтения данных является вызов [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Эта функция выполняет синтаксический анализ универсальных ресурсов URL-адрес предоставленные вами, открывает подключение к серверу, указанному в URL-адрес и возвращает только для чтения `CInternetFile` объекта. `CInternetSession::OpenURL`не относится к типу одного протокола, и тем же вызовом работает для любого gopher, HTTP или FTP URL-адреса. `CInternetSession::OpenURL`даже работает с локальными файлами (возврат `CStdioFile` вместо `CInternetFile`).  
  
-   Если к Интернету сеанса не чтение и запись данных, но выполняет другие задачи, например при удалении файла в каталоге FTP, не может потребоваться создать экземпляр `CInternetFile`.  
  
 Существует два способа создания `CInternetFile` объекта:  
  
-   Если вы используете `CInternetSession::OpenURL` для установления подключения к серверу, вызов `OpenURL` возвращает `CStdioFile`.  
  
-   Если использовать **CInternetSession::GetFtpConnection**, `GetGopherConnection`, или `GetHttpConnection` для установления подключения к серверу, необходимо вызвать `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, или **CHttpConnection::OpenRequest,**  соответственно, чтобы вернуть `CInternetFile`, `CGopherFile`, или `CHttpFile`соответственно.  
  
 Шаги по реализации клиентских веб-приложений зависит от того, необходимо создать универсальный клиент через Интернет, на основе **OpenURL** или протоколом клиента, с помощью одного из **GetConnection** функции.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Как создавать клиентских веб-приложений, обычно работает с FTP, HTTP и gopher](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [Как создавать клиентского приложения FTP, который открывает файл](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Как создавать клиентского приложения FTP не открывайте файл, но выполняет операцию каталога, например при удалении файла](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Как написать клиентского приложения gopher](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [Как создавать клиентского приложения HTTP](../mfc/steps-in-a-typical-http-client-application.md)  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Классы MFC для создания клиентских приложений в Интернете](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)
