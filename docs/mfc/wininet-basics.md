---
title: Основные сведения о WinInet
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: b989e5c3df63ee7b5129d01468a0f869772ed286
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367325"
---
# <a name="wininet-basics"></a>Основные сведения о WinInet

Вы можете использовать WinInet для добавления поддержки FTP для загрузки и загрузки файлов из приложения. Вы можете переопределить [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) и использовать параметр *dwContext* для предоставления пользователям информации о ходе работы при поиске и загрузке файлов.

Эта статья содержит следующие темы:

- [Создайте очень простой браузер](#_core_create_a_very_simple_browser)

- [Скачать веб-страницу](#_core_download_a_web_page)

- [FTP файл](#_core_ftp_a_file)

- [Получить Гофер Каталог](#_core_retrieve_a_gopher_directory)

- [Отображение информации о прогрессе при передаче файлов](#_core_display_progress_information_while_transferring_files)

Выдержки из кода ниже демонстрируют, как создать простой браузер, скачать веб-страницу, FTP файл, и поиск файла суслик. Они не предназначены в качестве полных примеров и не все содержат обработку исключений.

Для получения дополнительной информации о WinInet, [см. Win32 Интернет расширения (WinInet)](../mfc/win32-internet-extensions-wininet.md).

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a>Создайте очень простой браузер

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a>Скачать веб-страницу

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a>FTP файл

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a>Получить Гофер Каталог

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>Использование OnStatusCallback

При использовании классов WinInet можно использовать для получения информации о статусе участника [объекта](../mfc/reference/cinternetsession-class.md#onstatuscallback) CInternetSession вашего приложения [CInternetSession.](../mfc/reference/cinternetsession-class.md) Если вы получаете свой `CInternetSession` `OnStatusCallback`собственный объект, переопределить и включить `OnStatusCallback` обратные вызовы статуса, MFC вызовет вашу функцию с информацией о ходе работы в этой сессии Интернета.

Поскольку один сеанс может поддерживать несколько соединений (которые в `OnStatusCallback` течение срока их службы могут выполнять множество различных операций), необходим механизм для идентификации каждого изменения статуса с определенным соединением или транзакцией. Этот механизм обеспечивается параметром идентификатора контекста, присваиваемым многим функциям членов в классах поддержки WinInet. Этот параметр всегда типа **DWORD** и всегда называется *dwContext*.

Контекст, присвоенный определенному объекту Интернета, используется только для `OnStatusCallback` определения действия `CInternetSession` объекта, вызываемого в элементе объекта. Вызов получает `OnStatusCallback` несколько параметров; эти параметры работают вместе, чтобы сообщить приложению, какой прогресс был достигнут для транзакции и соединения.

При создании `CInternetSession` объекта можно указать параметр *dwContext* для конструктора. `CInternetSession`сам по себе не использует идентификатор контекста; вместо этого он передает идентификатор контекста на любые объекты, полученные из **InternetConnection,** которые явно не получают свой собственный идентификатор контекста. В свою `CInternetConnection` очередь, эти объекты `CInternetFile` будут передавать идентификатор контекста вместе с объектами, которые они создают, если не указано идентификатор агнеталя другого контекста. Если, с другой стороны, вы укажете свой идентификатор контекста, объект и любая работа, которую он выполняет, будут связаны с этим идентификатором контекста. Ипотилирами контекста можно определить, какой статус `OnStatusCallback` предоставляется вам в вашей функции.

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a>Отображение информации о прогрессе при передаче файлов

Например, если вы пишете приложение, которое создает соединение с сервером FTP для чтения файла, а также `CInternetSession` подключается к серверу HTTP, чтобы получить веб-страницу, у вас будет объект, `CInternetConnection` два объекта (один будет) `CFtpSession` `CHttpSession`и два `CInternetFile` объекта (по одному для каждого соединения). Если вы использовали значения по умолчанию для параметров *dwContext,* `OnStatusCallback` вы не сможете различать вызовы, указывающие на прогресс для соединения FTP, и вызовы, указывающие на прогресс для соединения HTTP. Если вы укажете *dwContext* ID, который `OnStatusCallback`вы можете позже проверить в, вы будете знать, какая операция генерируется обратный вызов.

## <a name="see-also"></a>См. также раздел

[Основы программирования ВРЦ в Интернете](../mfc/mfc-internet-programming-basics.md)<br/>
[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)
