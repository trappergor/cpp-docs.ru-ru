---
title: "Шаги для удаления файла в типичном клиентском приложении FTP | Microsoft Docs"
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
  - "FTP (протокол передачи данных), клиентские приложения"
  - "Интернет-приложения, клиентские приложения FTP"
  - "клиентские интернет-приложения, удаление FTP"
  - "WinInet - классы, FTP"
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаги для удаления файла в типичном клиентском приложении FTP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице приведены шаги, могут выполняться обычным клиентском приложении FTP, удаляет файл.  
  
|Целью является|Действия, предпринимаемые|Произведенный эффект|  
|--------------------|-------------------------------|--------------------------|  
|Начать сеанс FTP.|Создайте объект [CInternetSession](../Topic/CInternetSession%20Class.md).|Инициализирует WinInet и к серверу.|  
|Соединения с ftp\-сервером.|Используйте [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|Возвращает объект [CFtpConnection](../mfc/reference/cftpconnection-class.md).|  
|Убедитесь в том, что в правом каталог на FTP\-сервере.|Используйте [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md) или [CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md).|Возвращает имя или URL\-адрес каталога в данный момент подключен к на сервер, в зависимости от выбранного функции\-члена.|  
|Перейдите в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Перейдите в данный момент подключен к на сервер.|  
|Найдите первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Находит первый файл.  Возвращает ЛОЖНОЕ, если отсутствуют файлы не найдены.|  
|Найдите следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Находит следующий файл.  Возвращает ЛОЖНОЕ, если файл не найден.|  
|Удалите файл " **FindFile** или `FindNextFile`.|Используйте [CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md), используя имя файла, **FindFile** или `FindNextFile`.|Удаляет файл на сервере для чтения или записи.|  
|Обработка исключений.|Используется класс [CInternetException](../mfc/reference/cinternetexception-class.md).|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса FTP.|Dispose объекта [CInternetSession](../Topic/CInternetSession%20Class.md).|Автоматически очищает handles и открытие подключения файлов.|  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)