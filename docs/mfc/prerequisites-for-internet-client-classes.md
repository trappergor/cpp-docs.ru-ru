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
ms.openlocfilehash: aaf5756df69728e8ae89fb278bc0671bfc6840b7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619834"
---
# <a name="prerequisites-for-internet-client-classes"></a>Необходимые компоненты для клиентских классов в Интернете

Некоторые действия, выполняемые Интернет-клиентом (например, чтение файла), имеют необходимые действия (в данном случае установка подключения к Интернету). В следующих таблицах перечислены предварительные требования для некоторых действий клиента.

### <a name="general-internet-url-ftp-gopher-or-http"></a>Общий URL-адрес в Интернете (FTP, Gopher или HTTP)

|Действие|Предварительное требование|
|------------|------------------|
|Установите подключение.|Создайте [Цинтернетсессион](reference/cinternetsession-class.md) , чтобы установить базу клиентского Интернет-приложения.|
|Откройте URL-адрес.|Установите подключение. Вызовите [Цинтернетсессион:: OpenURL](reference/cinternetsession-class.md#openurl). `OpenURL`Функция возвращает объект ресурса, доступного только для чтения.|
|Чтение данных URL-адреса.|Откройте URL-адрес. Вызовите [Цинтернетфиле:: Read](reference/cinternetfile-class.md#read).|
|Задайте параметр Интернета.|Установите подключение. Вызовите [Цинтернетсессион:: SetOption](reference/cinternetsession-class.md#setoption).|
|Задайте функцию, которая будет вызываться со сведениями о состоянии.|Установите подключение. Вызовите [Цинтернетсессион:: енаблестатускаллбакк](reference/cinternetsession-class.md#enablestatuscallback). Переопределите [Цинтернетсессион:: онстатускаллбакк](reference/cinternetsession-class.md#onstatuscallback) , чтобы обращаться к вызовам.|

### <a name="ftp"></a>FTP

|Действие|Предварительное требование|
|------------|------------------|
|Установите соединение по FTP.|Создайте [Цинтернетсессион](reference/cinternetsession-class.md) в качестве основания для этого клиентского Интернет-приложения. Вызовите метод [Цинтернетсессион:: жетфтпконнектион](reference/cinternetsession-class.md#getftpconnection) , чтобы создать объект [кфтпконнектион](reference/cftpconnection-class.md) .|
|Найти первый ресурс.|Установите соединение по FTP. Создайте объект [кфтпфилефинд](reference/cftpfilefind-class.md) . Вызовите [кфтпфилефинд:: финдфиле](reference/cftpfilefind-class.md#findfile).|
|Перечисление всех доступных ресурсов.|Найти первый файл. Вызовите [кфтпфилефинд:: FindNextFile](reference/cftpfilefind-class.md#findnextfile) , пока не вернет значение false.|
|Откройте FTP-файл.|Установите соединение по FTP. Вызовите метод [кфтпконнектион:: OpenFile](reference/cftpconnection-class.md#openfile) , чтобы создать и открыть объект [Цинтернетфиле](reference/cinternetfile-class.md) .|
|Чтение файла FTP.|Откройте FTP-файл с доступом для чтения. Вызовите [Цинтернетфиле:: Read](reference/cinternetfile-class.md#read).|
|Запись в файл FTP.|Откройте FTP-файл с доступом для записи. Вызовите [Цинтернетфиле:: Write](reference/cinternetfile-class.md#write).|
|Измените каталог клиента на сервере.|Установите соединение по FTP. Вызовите [кфтпконнектион:: сеткуррентдиректори](reference/cftpconnection-class.md#setcurrentdirectory).|
|Получение текущего каталога клиента на сервере.|Установите соединение по FTP. Вызовите [кфтпконнектион:: GetCurrentDirectory](reference/cftpconnection-class.md#getcurrentdirectory).|

### <a name="http"></a>HTTP

|Действие|Предварительное требование|
|------------|------------------|
|Установите HTTP-соединение.|Создайте [Цинтернетсессион](reference/cinternetsession-class.md) в качестве основания для этого клиентского Интернет-приложения. Вызовите метод [Цинтернетсессион:: жесттпконнектион](reference/cinternetsession-class.md#gethttpconnection) , чтобы создать объект [чттпконнектион](reference/chttpconnection-class.md) .|
|Откройте HTTP-файл.|Установите HTTP-соединение. Вызовите метод [чттпконнектион:: опенрекуест](reference/chttpconnection-class.md#openrequest) , чтобы создать объект [чттпфиле](reference/chttpfile-class.md) . Вызовите [чттпфиле:: аддрекуессеадерс](reference/chttpfile-class.md#addrequestheaders). Вызовите [чттпфиле:: SendRequest](reference/chttpfile-class.md#sendrequest).|
|Чтение файла HTTP.|Откройте HTTP-файл. Вызовите [Цинтернетфиле:: Read](reference/cinternetfile-class.md#read).|
|Получение сведений о HTTP-запросе.|Установите HTTP-соединение. Вызовите метод [чттпконнектион:: опенрекуест](reference/chttpconnection-class.md#openrequest) , чтобы создать объект [чттпфиле](reference/chttpfile-class.md) . Вызовите [чттпфиле:: куеринфо](reference/chttpfile-class.md#queryinfo).|

### <a name="gopher"></a>Протокол

|Действие|Предварительное требование|
|------------|------------------|
|Установите Gopher-подключение.|Создайте [Цинтернетсессион](reference/cinternetsession-class.md) в качестве основания для этого клиентского Интернет-приложения. Вызовите [Цинтернетсессион:: жетгоферконнектион](reference/cinternetsession-class.md#getgopherconnection) , чтобы создать [кгоферконнектион](reference/cgopherconnection-class.md).|
|Найти первый файл в текущем каталоге.|Установите Gopher-подключение. Создайте объект [кгоферфилефинд](reference/cgopherfilefind-class.md) . Вызовите метод [кгоферконнектион:: CreateLocator](reference/cgopherconnection-class.md#createlocator) , чтобы создать объект [кгоферлокатор](reference/cgopherlocator-class.md) . Передайте указатель в [кгоферфилефинд:: финдфиле](reference/cgopherfilefind-class.md#findfile). Вызовите [кгоферфилефинд::-Locator](reference/cgopherfilefind-class.md#getlocator) , чтобы получить указатель файла, если он понадобится позже.|
|Перечисление всех доступных файлов.|Найти первый файл. Вызовите [кгоферфилефинд:: FindNextFile](reference/cgopherfilefind-class.md#findnextfile) , пока не вернет значение false.|
|Откройте файл gopher.|Установите Gopher-подключение. Создайте локатор gopher с помощью [кгоферконнектион:: CreateLocator](reference/cgopherconnection-class.md#createlocator) или найдите указатель с помощью [кгоферфилефинд::-Locator](reference/cgopherfilefind-class.md#getlocator). Вызовите [кгоферконнектион:: OpenFile](reference/cgopherconnection-class.md#openfile).|
|Чтение файла gopher.|Откройте файл gopher. Используйте [CGopherFile](reference/cgopherfile-class.md).|

## <a name="see-also"></a>См. также раздел

[Расширения Интернета Win32 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[Классы MFC для создания клиентских приложений в Интернете](mfc-classes-for-creating-internet-client-applications.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](writing-an-internet-client-application-using-mfc-wininet-classes.md)
