---
title: "Шаги в типичном клиентском приложении FTP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d707d2b4903394b6b3b70367184767cce28ea1d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Шаги для организации типичного клиентского приложения FTP
Создает обычном клиентском приложении FTP [CInternetSession](../mfc/reference/cinternetsession-class.md) и [классе CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта. Обратите внимание, что эти классы MFC WinInet не контролируют, фактически параметры типа прокси-сервера; Выполняет IIS.  
  
 Кроме того см. статьи базы знаний:  
  
-   Практическое руководство: Протокол FTP с CERN прокси-с помощью WinInet API (идентификатор статьи: Q166961)  
  
-   Пример: FTP паролем CERN защищенных прокси-сервера (идентификатор статьи: Q216214)  
  
-   Internet Services Manager не удается показать службы установленных прокси-сервера (идентификатор статьи: Q216802)  
  
 Ниже приведены шаги, которые необходимо выполнять в обычном клиентском приложении FTP.  
  
|Ваша цель|Выполняемые действия|Произведенный эффект|  
|---------------|----------------------|-------------|  
|Начните сеанс FTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|  
|Подключиться к FTP-серверу.|Используйте [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Возвращает [классе CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта.|  
|Изменения в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Изменяет каталог, который в настоящий момент подключены к на сервере.|  
|Найти первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Находит первый файл. Возвращает значение FALSE, если файлы не найдены.|  
|Найти следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Находит следующий файл. Возвращает значение FALSE, если файл не найден.|  
|Откройте файл, обнаруженные **FindFile** или `FindNextFile` для чтения или записи.|Используйте [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile), возвращенные с помощью имени файла [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) или [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Открывает файл для чтения или записи на сервере. Возвращает [классе CInternetFile](../mfc/reference/cinternetfile-class.md) объекта.|  
|Чтения или записи в файл.|Используйте [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read) или [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|Считывает или записывает указанное число байтов, с помощью буфера указанные вами.|  
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса FTP.|Удалить [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Предварительные требования для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
