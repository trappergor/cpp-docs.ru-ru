---
title: "Шаги для организации типичного клиентского приложения Gopher | Microsoft Docs"
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
  - "Gopher - клиентские приложения"
  - "Интернет-приложения, gopher - клиентские приложения"
  - "клиентские интернет-приложения, gopher - таблица"
  - "WinInet - классы, gopher"
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Шаги для организации типичного клиентского приложения Gopher
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице приведены шаги, могут выполняться обычным клиентском приложении gopher.  
  
|Целью является|Действия, предпринимаемые|Произведенный эффект|  
|--------------------|-------------------------------|--------------------------|  
|Начать сеанс gopher.|Создайте объект [CInternetSession](../Topic/CInternetSession%20Class.md).|Инициализирует WinInet и к серверу.|  
|Подключитесь к gopher сервер.|Используйте [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).|Возвращает объект [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Найдите первый ресурс в gopher.|Используйте [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).|Находит первый файл.  Возвращает ЛОЖНОЕ, если отсутствуют файлы не найдены.|  
|Найдите следующий ресурс в gopher.|Используйте [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md).|Находит следующий файл.  Возвращает ЛОЖНОЕ, если файл не найден.|  
|Открытие файла " **FindFile** или `FindNextFile` для чтения.|Получает средство поиска gopher с помощью [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Используйте [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Файл будет открыт определенный URL\-адрес.  `OpenFile` возвращает объект [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
|Откройте файл, используя средство поиска gopher указываются.|Создайте gopher средство поиска с помощью [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md).  Используйте [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Файл будет открыт определенный URL\-адрес.  `OpenFile` возвращает объект [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
|Чтение из файла.|Используйте [CGopherFile](../mfc/reference/cgopherfile-class.md).|Считывает указанное количество байтов, используя буфер был предоставлен.|  
|Обработка исключений.|Используется класс [CInternetException](../mfc/reference/cinternetexception-class.md).|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса gopher.|Dispose объекта [CInternetSession](../Topic/CInternetSession%20Class.md).|Автоматически очищает handles и открытие подключения файлов.|  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)