---
title: Шаги для удаления файла в типичном клиентском приложении FTP
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 6d2a920d3053a920638dd20a23e1c2334745bbc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326508"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Шаги для удаления файла в типичном клиентском приложении FTP

В следующей таблице показаны шаги, которые необходимо выполнять в обычном клиентском приложении FTP, который удаляет файл.

|Ваша цель|Выполняемые действия|Эффекты|
|---------------|----------------------|-------------|
|Начните сеанс FTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|
|Подключитесь к серверу FTP.|Используйте [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Возвращает [CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта.|
|Установите этот флажок, чтобы убедиться, что вы находитесь в каталоге вправо на FTP-сервере.|Используйте [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) или [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Возвращает имя или URL-адрес каталога, который в данный момент вы подключены к на сервере, в зависимости от выбранной функции-члена.|
|Перейдите в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Изменение каталога, которые в настоящее время вы подключены к на сервере.|
|Найдите первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Находит первый файл. Возвращает значение FALSE, если файлы не найдены.|
|Найти следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Находит следующий файл. Возвращает значение FALSE, если файл не найден.|
|Удаление файла, найденного с `FindFile` или `FindNextFile`.|Используйте [CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove), возвращенные с помощью имени файла `FindFile` или `FindNextFile`.|Удаляет файл на сервере для чтения или записи.|
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернет.|
|Завершите сеанс FTP.|Избавиться от [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
