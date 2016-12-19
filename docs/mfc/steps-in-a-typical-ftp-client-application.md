---
title: "Шаги для организации типичного клиентского приложения FTP | Microsoft Docs"
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
  - "FTP (протокол передачи данных)"
  - "FTP (протокол передачи данных), клиентские приложения"
  - "Интернет-приложения, клиентские приложения FTP"
  - "клиентские интернет-приложения, таблица FTP"
  - "WinInet - классы, FTP"
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаги для организации типичного клиентского приложения FTP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Типичное FTP клиентское приложение создает объект [CInternetSession](../Topic/CInternetSession%20Class.md) и [CFtpConnection](../mfc/reference/cftpconnection-class.md).  Обратите внимание, что эти классы MFC WinInet не так, элемент управления параметры типа прокси. IIS;  
  
 Также см. в следующих статьях базы знаний Майкрософт:  
  
-   HOWTO: FTP с прокси\-сервером CERN\- с использованием API WinInet \(идентификатор статьи: Q166961\)  
  
-   ПРИМЕР: FTP с прокси\-сервером CERN\-, защищенной паролем \(идентификатор статьи: Q216214\)  
  
-   Диспетчера служб Интернета невозможности отображения установленные службы прокси \(идентификатор статьи: Q216802\)  
  
 В следующей таблице приведены шаги, могут выполняться обычным клиентском приложении FTP.  
  
|Целью является|Действия, предпринимаемые|Произведенный эффект|  
|--------------------|-------------------------------|--------------------------|  
|Начать сеанс FTP.|Создайте объект [CInternetSession](../Topic/CInternetSession%20Class.md).|Инициализирует WinInet и к серверу.|  
|Соединения с ftp\-сервером.|Используйте [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|Возвращает объект [CFtpConnection](../mfc/reference/cftpconnection-class.md).|  
|Перейдите в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Перейдите в данный момент подключен к на сервер.|  
|Найдите первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Находит первый файл.  Возвращает ЛОЖНОЕ, если отсутствуют файлы не найдены.|  
|Найдите следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Находит следующий файл.  Возвращает ЛОЖНОЕ, если файл не найден.|  
|Открытие файла " **FindFile** или `FindNextFile` для чтения или записи.|Используйте [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md), используя имя файла, [FindFile](../Topic/CFtpFileFind::FindFile.md) или [FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Файл будет открыт на сервере для чтения или записи.  Возвращает объект [CInternetFile](../mfc/reference/cinternetfile-class.md).|  
|Чтение и запись в файл.|Используйте [CInternetFile::Read](../Topic/CInternetFile::Read.md) или [CInternetFile::Write](../Topic/CInternetFile::Write.md).|Считывает или записывает указанное число байтов, используя буфер был предоставлен.|  
|Обработка исключений.|Используется класс [CInternetException](../mfc/reference/cinternetexception-class.md).|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса FTP.|Dispose объекта [CInternetSession](../Topic/CInternetSession%20Class.md).|Автоматически очищает handles и открытие подключения файлов.|  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)