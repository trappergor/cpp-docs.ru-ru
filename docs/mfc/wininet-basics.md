---
title: "Основные сведения о WinInet | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnStatusCallback - метод"
  - "WinInet - классы, WinInet - о классах"
  - "WinInet - классы, отображение хода выполнения"
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Основные сведения о WinInet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать WinInet добавление поддержки FTP, чтобы загрузить и передавать файлы из приложения.  Можно переопределить [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) и используйте параметр `dwContext` для реализации информацию о ходе выполнения пользователи как для поиска и загрузите файлы.  
  
 Этот раздел содержит следующие подразделы:  
  
-   [Создайте очень простой браузер](#_core_create_a_very_simple_browser)  
  
-   [Загрузите страницу](#_core_download_a_web_page)  
  
-   [Файл FTP](#_core_ftp_a_file)  
  
-   [Извлечение каталог gopher](#_core_retrieve_a_gopher_directory)  
  
-   [Отображает сведения о ходе выполнения во время перемещающ файлы](#_core_display_progress_information_while_transferring_files)  
  
 Извлечь кода демонстрируют, как создать простой браузер, загрузят страницы, FTP файл и поиск файла gopher.  Они не предназначены для как полные примеры и не содержат все обработку исключений.  
  
 Дополнительные сведения о WinInet см. в разделе [Расширения Win32 Интернета \(WinInet\)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Создайте очень простой браузер  
 [!CODE [NVC_MFCWinInet#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#1)]  
  
##  <a name="_core_download_a_web_page"></a> Загрузите страницу  
 [!CODE [NVC_MFCWinInet#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#2)]  
  
##  <a name="_core_ftp_a_file"></a> Файл FTP  
 [!CODE [NVC_MFCWinInet#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#3)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Извлечение каталог gopher  
 [!CODE [NVC_MFCWinInet#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#4)]  
  
## Используйте OnStatusCallback  
 При использовании классов WinInet, можно использовать элемент [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) объекта [CInternetSession](../Topic/CInternetSession%20Class.md) приложения извлечь сведения о состоянии.  Если производный объект `CInternetSession`, переопределите `OnStatusCallback` и включить обратные вызовы состояния, MFC вызывает пользовательскую функцию `OnStatusCallback` со сведениями о ходе выполнения о работе полностью в этом сеансе Интернета.  
  
 Поскольку один сеанс может поддерживать несколько подключений \(, по своим времени существования, можно выполнять различные определенных операций\), `OnStatusCallback` требуется механизм определения каждое изменение состояния с указанными подключение или транзакцией.  Механизм, предоставляется параметром контекстного идентификатора, присвоенное многие функции\-члены в классах поддержки WinInet.  Этот параметр всегда типа `DWORD` и всегда имеет имя `dwContext`.  
  
 Контекст, в частности объект Интернета используется только для определения причины работы объекта в элементе `OnStatusCallback` объекта `CInternetSession`.  Вызов `OnStatusCallback` получит несколько параметров; эти параметры работают вместе, чтобы сообщить приложению о ходе выполнения, выполненной для которого транзакции и подключение.  
  
 При создании объекта `CInternetSession` можно указать параметр `dwContext` в конструктор.  `CInternetSession` сам не использует контекстный идентификатор; вместо этого он передает контекстный идентификатор и перейти к любому **InternetConnection**\- производным объектам, которые явно не задает контекстный идентификатор их.  В свою очередь, эти объекты `CInternetConnection` загружают контекстный идентификатор вперед к объектам `CInternetFile` они создают, если явно не указан идентификатор другого контекста  Если, с другой стороны, нужно задать конкретный контекстный идентификатор, объект, и любой рабочий она позволяет связать с этим идентификатором контекста  Можно использовать идентификатор контекста указать сведения о состоянии указан в функции `OnStatusCallback`.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Отображает сведения о ходе выполнения во время перемещающ файлы  
 Например, если нужно создать приложение, которое создает соединение с FTP\-сервером для считывания файла, а также подключиться к HTTP\-серверу для доступа к странице будет создан объект `CInternetSession`, 2 объекта `CInternetConnection` \(один будет **CFtpSession** и другой будет **CHttpSession**\) и 2 объекта `CInternetFile` \(по одному для каждого соединения\).  При использовании значения по умолчанию для параметров `dwContext`, то, возможно, будет различать вызовами `OnStatusCallback`, отражающих прогресс для подключения FTP и вызовы, отражающих прогресс для подключения HTTP.  Если указан идентификатор `dwContext`, которое можно более новый тест в `OnStatusCallback` необходимо узнать, какая операция генерировала обратный вызов.  
  
## См. также  
 [Основы программирования для интернет\-решений MFC](../mfc/mfc-internet-programming-basics.md)   
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)