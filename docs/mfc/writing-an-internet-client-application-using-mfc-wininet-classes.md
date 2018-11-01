---
title: Создание клиентских приложений в Интернете с использованием классов MFC WinInet
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 041fa90b030edd9b5324c183b0153a8a062735da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494969"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>Создание клиентских приложений в Интернете с использованием классов MFC WinInet

Интернет-сеанс выполняется на основе каждого клиентских приложений в Интернете. Реализация MFC сеансов Интернета в качестве объектов класса [CInternetSession](../mfc/reference/cinternetsession-class.md). С помощью этого класса, можно создать один сеанс Интернет или несколько одновременных сеансов.

Чтобы подключиться к серверу, вам потребуется [CInternetConnection](../mfc/reference/cinternetconnection-class.md) объекта, а также `CInternetSession`. Можно создать `CInternetConnection` с помощью [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), или [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Каждый из этих вызовов относится только к тип протокола. Эти вызовы следует открывать файл на сервере для чтения или записи. Если вы собираетесь чтения или записи данных, необходимо открыть файл как отдельный шаг.

Для большинства сеансов Интернета `CInternetSession` объект работает Рука в руку с [CInternetFile](../mfc/reference/cinternetfile-class.md) объекта:

- Для Интернет-сеанс, необходимо создать экземпляр [CInternetSession](../mfc/reference/cinternetsession-class.md).

- Если сеанс Internet считывает или записывает данные, необходимо создать экземпляр `CInternetFile` (или его подклассов [CHttpFile](../mfc/reference/chttpfile-class.md) или [CGopherFile](../mfc/reference/cgopherfile-class.md)). Самый простой способ чтения данных является вызов [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Эта функция выполняет синтаксический анализ универсальный указатель ресурса (URL) указанные вами, открывает подключение к серверу, указанному в URL-адрес и возвращает только для чтения `CInternetFile` объекта. `CInternetSession::OpenURL` не относится к типу одного протокола — тот же вызов работает любой FTP, HTTP или gopher URL-адрес. `CInternetSession::OpenURL` даже работает с локальными файлами (возвращая `CStdioFile` вместо `CInternetFile`).

- Если в Интернет, сеанс не чтения или записи данных, но выполняет другие задачи, например при удалении файла в каталоге FTP, не может потребоваться создать экземпляр `CInternetFile`.

Существует два способа создания `CInternetFile` объекта:

- Если вы используете `CInternetSession::OpenURL` для установления подключения к серверу, вызов `OpenURL` возвращает `CStdioFile`.

- Если использовать `CInternetSession::GetFtpConnection`, `GetGopherConnection`, или `GetHttpConnection` для установления подключения к серверу, необходимо вызвать `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, или `CHttpConnection::OpenRequest`, соответственно, чтобы вернуть `CInternetFile`, `CGopherFile`, или `CHttpFile`, соответственно.

Этапы реализации клиентских приложений в Интернете зависит от того, создается ли универсальный Интернет-клиент на основе `OpenURL` или клиент определенных протоколов, с помощью одного из `GetConnection` функции.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Как написать клиентских приложений в Интернете, обычно с FTP, HTTP и gopher](../mfc/steps-in-a-typical-internet-client-application.md)

- [Как написать клиентского приложения FTP, который открывает файл](../mfc/steps-in-a-typical-ftp-client-application.md)

- [Как написать приложение клиента FTP, файл не открыт, но выполняет операции каталога, например при удалении файла](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Как написать клиентского приложения gopher](../mfc/steps-in-a-typical-gopher-client-application.md)

- [Как написать клиентского приложения HTTP](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Классы MFC для создания клиентских приложений в Интернете](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)
