---
title: Шаги для организации типичного клиентского приложения HTTP
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 59b585d3e6b8c9f13c585f5a712d33abd6123f67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306968"
---
# <a name="steps-in-a-typical-http-client-application"></a>Шаги для организации типичного клиентского приложения HTTP

В следующей таблице представлены действия, можно выполнять в типичном приложении клиента HTTP:

|Ваша цель|Выполняемые действия|Произведенный эффект|
|---------------|----------------------|-------------|
|Начните сеанс HTTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|
|Подключение к HTTP-сервера.|Используйте [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Возвращает [CHttpConnection](../mfc/reference/chttpconnection-class.md) объекта.|
|Отправьте запрос HTTP.|Используйте [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Возвращает [CHttpFile](../mfc/reference/chttpfile-class.md) объекта.|
|Отправьте запрос HTTP.|Используйте [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) и [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Поиск файла. Возвращает значение FALSE, если файл не найден.|
|Чтение из файла.|Используйте [CHttpFile](../mfc/reference/chttpfile-class.md).|Считывает указанное число байтов, с помощью буфера указанные вами.|
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернет.|
|Завершите сеанс HTTP.|Избавиться от [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
