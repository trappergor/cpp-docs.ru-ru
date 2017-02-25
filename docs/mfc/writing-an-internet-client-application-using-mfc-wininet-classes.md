---
title: "Создание клиентских приложений в Интернете с использованием классов MFC WinInet | Microsoft Docs"
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
  - "Интернет-приложения, клиентские приложения"
  - "Интернет-приложения, WinInet"
  - "клиентские интернет-приложения"
  - "клиентские интернет-приложения, написание"
  - "MFC - библиотека, Интернет-приложения"
  - "WinInet - классы, программирование"
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Создание клиентских приложений в Интернете с использованием классов MFC WinInet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Основа каждого приложения Интернет\-клиента сеанс Интернета.  MFC реализует сеансы Интернета как объекты класса [CInternetSession](../Topic/CInternetSession%20Class.md).  С помощью этого класса, можно создать один сеанс Интернета или несколько параллельных сеансов.  
  
 Для связи с сервером нужно создать два объекта: объект [CInternetConnection](../Topic/CInternetConnection%20Class.md), так и `CInternetSession`.  Можно создать `CInternetConnection` с помощью [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) или [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).  Каждый из этих вызовов относится к типу протокола.  Эти вызовы не позволяет открыть файл на сервере для чтения или записи.  Если требуется считывать и записывать данные, необходимо открыть файл как отдельно.  
  
 Для большинства сеансов Интернета объект `CInternetSession` работает рука об руку с объектом [CInternetFile](../mfc/reference/cinternetfile-class.md):  
  
-   Для сеанса в интернете необходимо создать экземпляр [CInternetSession](../Topic/CInternetSession%20Class.md).  
  
-   Если сеанс Интернета считывает или записывает данные, необходимо создать экземпляр `CInternetFile` \(или его подклассов, [CHttpFile](../Topic/CHttpFile%20Class.md) или [CGopherFile](../mfc/reference/cgopherfile-class.md)\).  Самый простой способ чтения данных вызова [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  Эта функция анализирует средство поиска \(URL\) ресурсов как введено текущим пользователем, открывает соединение с сервером, URL\-адрес и возвращает только для чтения объект `CInternetFile`.  `CInternetSession::OpenURL` не только на один тип протокола — тот же вызов работает для любого FTP, HTTP, или URL\-адрес gopher.  `CInternetSession::OpenURL` даже работает с локальные файлы \(возврат `CStdioFile` вместо `CInternetFile`\).  
  
-   Если сеанс не считывает Интернета или не записывает, то данные, но выполняет другие задачи, например удаление файла в каталоге FTP, не может создать экземпляр `CInternetFile`.  
  
 2 Способа создания объекта `CInternetFile`:  
  
-   При использовании `CInternetSession::OpenURL`, чтобы установить подключение сервера, вызов `OpenURL` возвращает `CStdioFile`.  
  
-   Если использовать **CInternetSession::GetFtpConnection**, `GetGopherConnection` или `GetHttpConnection` установить подключение сервера, необходимо вызвать `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, или **CHttpConnection::OpenRequest,**, соответственно, возвращать `CInternetFile`, `CGopherFile` или `CHttpFile` соответственно.  
  
 Этапы реализации приложения Интернет\-клиента различаются в зависимости от того, необходимость создания Интернет\-клиент универсальный шаблон, основанный на **OpenURL**  или клиент протокол\-, используя одну из функций **GetConnection**.  
  
## Дополнительные сведения  
  
-   [Разделы справки Интернет\-клиента пишет приложение, которое работает с родов FTP, HTTP и gopher?](../Topic/Steps%20in%20a%20Typical%20Internet%20Client%20Application.md)  
  
-   [Разделы справки записывает клиентское приложение FTP для открытия файла?](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Разделы справки записывает клиентское приложение FTP, позволяет открыть файл, но не выполняет операцию каталога, например удаление файла?](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Разделы справки записывает клиентское приложение gopher?](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [Разделы справки записывает клиентское приложение HTTP?](../mfc/steps-in-a-typical-http-client-application.md)  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Классы MFC для создания клиентских приложений в Интернете](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)