---
title: Основные сведения о WinInet | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98ca2eab519cdfa3140d40adfd83070976dcc965
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435653"
---
# <a name="wininet-basics"></a>Основные сведения о WinInet

WinInet можно использовать для добавления поддержки FTP для загрузки и отправки файлов из приложения. Можно переопределить [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) и использовать *dwContext* параметр для предоставления сведений о ходе выполнения пользователям, так как поиск и загрузка файлов.

Эта статья содержит следующие разделы:

- [Создать очень простой браузер](#_core_create_a_very_simple_browser)

- [Скачайте веб-страницы](#_core_download_a_web_page)

- [Файл FTP](#_core_ftp_a_file)

- [Получить каталог Gopher](#_core_retrieve_a_gopher_directory)

- [Отображение сведений о ходе выполнения во время передачи файлов](#_core_display_progress_information_while_transferring_files)

Отрывки кода ниже показано, как создать простой браузера, скачать веб-страницы, FTP файл и найдите файл gopher. Они не предназначены как полные примеры и не содержат обработки исключений.

Дополнительные сведения о WinInet, см. в разделе [расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md).

##  <a name="_core_create_a_very_simple_browser"></a> Создать очень простой браузер

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

##  <a name="_core_download_a_web_page"></a> Скачайте веб-страницы

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

##  <a name="_core_ftp_a_file"></a> Файл FTP

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

##  <a name="_core_retrieve_a_gopher_directory"></a> Получить каталог Gopher

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>Использовать OnStatusCallback

При использовании классов WinInet, можно использовать [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) членом приложения [CInternetSession](../mfc/reference/cinternetsession-class.md) объект для получения информации о состоянии. Если вы наследуете собственные `CInternetSession` объекта, переопределить `OnStatusCallback`и включить состояние обратные вызовы, вызовет MFC вашей `OnStatusCallback` функция сведения о ходе выполнения обо всей деятельности в этом сеансе Internet.

Так как за один сеанс может поддерживать несколько подключений (которые, во время своего существования может выполнения различных операций distinct), `OnStatusCallback` необходим механизм для идентификации каждого изменения состояния определенного подключения или транзакции. Этот механизм обеспечивает параметр контекста идентификатор, присвоенный многие из функций-членов в классы с поддержкой WinInet. Этот параметр всегда имеет тип **DWORD** и всегда имеет имя *dwContext*.

Контекст, назначенный к определенному объекту Интернет используется только для идентификации объекта приводит в действие `OnStatusCallback` членом `CInternetSession` объекта. Вызов `OnStatusCallback` принимает несколько параметров; эти параметры работают вместе, чтобы указать приложению, что было сделано для какой транзакции и соединения.

При создании `CInternetSession` объекта, можно указать *dwContext* параметра конструктора. `CInternetSession` сам не использует идентификатор контекста; Вместо этого он передает идентификатор контекста, к любому **Интернет-соединение**-производных объектов, которые не получают собственные контекстный идентификатор явным образом. В свою очередь, их `CInternetConnection` объектов передаст ИД контекста вдоль `CInternetFile` объекты, они создают, если вы явно не указано с идентификатором другого контекста. Если, с другой стороны, вы укажете идентификатор конкретного контекста собственные, объект и какой-либо работы он будет связан с этим идентификатором контекста. Идентификаторов контекста можно использовать для определения, какие сведения о состоянии предоставляется вам в вашей `OnStatusCallback` функции.

##  <a name="_core_display_progress_information_while_transferring_files"></a> Отображение сведений о ходе выполнения во время передачи файлов

Например, при написании приложения, которое создает соединение с FTP-сервера для считывания файла и подключается к серверу HTTP, чтобы получить веб-страницы, вы получите `CInternetSession` объекта, двух `CInternetConnection` объектов (один `CFtpSession` и другой `CHttpSession`) и два `CInternetFile` объектов (по одному для каждого подключения). Если вы использовали значения по умолчанию для *dwContext* параметры, вы не смогли бы различать `OnStatusCallback` вызовы, на которые указывают ход выполнения, для FTP-соединения и вызовы методов, которые указывают ход выполнения для HTTP-соединение. Если указать *dwContext* идентификатор, который позже можно проверить в `OnStatusCallback`, вы будете знать, какая операция создан обратный вызов.

## <a name="see-also"></a>См. также

[Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)<br/>
[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

