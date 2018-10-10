---
title: Шаги в типичном клиентском приложении FTP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ac1eef12a3f782f3ad9ba8a9bb526989876251e
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890222"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Шаги для организации типичного клиентского приложения FTP

Типичное приложение клиента FTP создает [CInternetSession](../mfc/reference/cinternetsession-class.md) и [CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта. Обратите внимание, что эти классы MFC WinInet фактически управляет параметры типа прокси-сервера; Делает IIS.

Ниже приведены шаги, которые необходимо выполнять в обычном клиентском приложении FTP.

|Ваша цель|Выполняемые действия|Произведенный эффект|
|---------------|----------------------|-------------|
|Начните сеанс FTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|
|Подключитесь к серверу FTP.|Используйте [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Возвращает [CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта.|
|Перейдите в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Изменение каталога, которые в настоящее время вы подключены к на сервере.|
|Найдите первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Находит первый файл. Возвращает значение FALSE, если файлы не найдены.|
|Найти следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Находит следующий файл. Возвращает значение FALSE, если файл не найден.|
|Откройте файл обнаруженных `FindFile` или `FindNextFile` для чтения или записи.|Используйте [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile), возвращенные с помощью имени файла [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) или [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Открывает файл для чтения или записи на сервере. Возвращает [CInternetFile](../mfc/reference/cinternetfile-class.md) объекта.|
|Считывание или запись в файл.|Используйте [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read) или [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|Считывает или записывает указанное число байтов, с помощью буфера указанные вами.|
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернет.|
|Завершите сеанс FTP.|Избавиться от [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
