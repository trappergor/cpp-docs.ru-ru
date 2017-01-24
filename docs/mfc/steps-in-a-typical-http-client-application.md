---
title: "Шаги для организации типичного клиентского приложения HTTP | Microsoft Docs"
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
  - "приложения [MFC], HTTP-клиент"
  - "клиентские приложения [C++], HTTP"
  - "клиентские приложения HTTP"
  - "Интернет-приложения [C++], клиентские приложения HTTP"
  - "клиентские интернет-приложения [C++], HTTP-таблица"
  - "WinInet - классы, HTTP"
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаги для организации типичного клиентского приложения HTTP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице приведены шаги, могут выполняться обычным клиентском приложении HTTP:  
  
|Целью является|Действия, предпринимаемые|Произведенный эффект|  
|--------------------|-------------------------------|--------------------------|  
|Начать сеанс HTTP.|Создайте объект [CInternetSession](../Topic/CInternetSession%20Class.md).|Инициализирует WinInet и к серверу.|  
|Подключитесь к HTTP\-серверу.|Используйте [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md).|Возвращает объект [CHttpConnection](../mfc/reference/chttpconnection-class.md).|  
|Открытие HTTP\-запроса.|Используйте [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).|Возвращает объект [CHttpFile](../Topic/CHttpFile%20Class.md).|  
|Отправить HTTP\-запрос.|Используйте [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md) и [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|Находит файл.  Возвращает ЛОЖНОЕ, если файл не найден.|  
|Чтение из файла.|Используйте [CHttpFile](../Topic/CHttpFile%20Class.md).|Считывает указанное число байтов в буфер был предоставлен.|  
|Обработка исключений.|Используется класс [CInternetException](../mfc/reference/cinternetexception-class.md).|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса HTTP.|Dispose объекта [CInternetSession](../Topic/CInternetSession%20Class.md).|Автоматически очищает handles и открытие подключения файлов.|  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)