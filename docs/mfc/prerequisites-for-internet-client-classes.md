---
title: Необходимые компоненты для клиентских классов в Интернете
ms.date: 11/04/2016
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
ms.openlocfilehash: 6246db7dfb2837f5d94fa51f8433b46722c43663
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218810"
---
# <a name="prerequisites-for-internet-client-classes"></a>Необходимые компоненты для клиентских классов в Интернете

Некоторые действия, предпринимаемые Интернет-клиентом (чтение файла, например) имеют ряд предварительных действий (в данном случае, подключении к Интернету). В следующих таблицах перечислены необходимые компоненты для некоторых действий клиента.

### <a name="general-internet-url-ftp-gopher-or-http"></a>Общие URL-адрес (FTP, Gopher или HTTP)

|Действие|Предварительные требования|
|------------|------------------|
|Установите подключение.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) для установления основы для клиентских приложений в Интернете.|
|Откройте URL-адрес.|Установите подключение. Вызовите [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). `OpenURL` Функция возвращает объект ресурсов только для чтения.|
|URL-адрес чтения данных.|Откройте URL-адрес. Вызовите [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Настроить параметр Internet.|Установите подключение. Вызовите [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|
|Установка функции может вызываться с использованием сведений о состоянии.|Установите подключение. Вызовите [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Переопределить [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) для обработки вызовов.|

### <a name="ftp"></a>FTP

|Действие|Предварительные требования|
|------------|------------------|
|Установите подключение к FTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) основой этого клиентских приложений в Интернете. Вызовите [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) для создания [CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта.|
|Найти первый ресурс.|Установите подключение к FTP. Создание [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) объекта. Вызовите [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|
|Перечислить все доступные ресурсы.|Найдите первый файл. Вызовите [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) пока не будет возвращено значение FALSE.|
|Откройте файл FTP.|Установите подключение к FTP. Вызовите [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile) для создания и открытия [CInternetFile](../mfc/reference/cinternetfile-class.md) объекта.|
|Чтение файла FTP.|Откройте файл FTP с доступом на чтение. Вызовите [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Запись в файл FTP.|Откройте файл FTP с доступом на запись. Вызовите [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|
|Измените каталог клиента на сервере.|Установите подключение к FTP. Вызовите [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|
|Получите текущий каталог клиента на сервере.|Установите подключение к FTP. Вызовите [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|

### <a name="http"></a>HTTP

|Действие|Предварительные требования|
|------------|------------------|
|Установите подключение к HTTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) основой этого клиентских приложений в Интернете. Вызовите [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) для создания [CHttpConnection](../mfc/reference/chttpconnection-class.md) объекта.|
|Откройте файл HTTP.|Установите подключение к HTTP. Вызовите [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) для создания [CHttpFile](../mfc/reference/chttpfile-class.md) объекта. Вызовите [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Вызовите [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|
|Файл для чтения HTTP.|Откройте файл HTTP. Вызовите [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Получение сведений о HTTP-запроса.|Установите подключение к HTTP. Вызовите [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) для создания [CHttpFile](../mfc/reference/chttpfile-class.md) объекта. Вызовите [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo).|

### <a name="gopher"></a>Gopher

|Действие|Предварительные требования|
|------------|------------------|
|Установите подключение gopher.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) основой этого клиентских приложений в Интернете. Вызовите [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) для создания [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|
|Найдите первый файл в текущем каталоге.|Установите подключение gopher. Создание [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) объекта. Вызовите [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) для создания [CGopherLocator](../mfc/reference/cgopherlocator-class.md) объекта. Передайте указатель для [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Вызовите [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) для получения указателя файла, если оно понадобится позже.|
|Перечислить все доступные файлы.|Найдите первый файл. Вызовите [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) пока не будет возвращено значение FALSE.|
|Откройте файл gopher.|Установите подключение gopher. Создание указателя gopher с [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) или найти указатель с [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Вызовите [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|
|Чтение файла gopher.|Откройте файл gopher. Используйте [CGopherFile](../mfc/reference/cgopherfile-class.md).|

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Классы MFC для создания клиентских приложений в Интернете](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
