---
title: Основы программирования для интернет-решений MFC
ms.date: 11/19/2018
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
ms.openlocfilehash: 814e63272058200850424e9d5355637111527e1c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750289"
---
# <a name="mfc-internet-programming-basics"></a>Основы программирования для интернет-решений MFC

Корпорация Майкрософт предоставляет множество интерфейсов API для программирования клиентских и серверных приложений. Многие новые приложения написаны для Интернета и технологии, возможностей браузера и изменение параметров безопасности, будут записаны новые типы приложений. Браузеры запуска на клиентских компьютерах, предоставление доступа к Интернет и отображении HTML-страниц, содержащих текст, графики, элементы управления ActiveX и документы. Серверы FTP, HTTP и gopher служб и запуску приложений расширения сервера, с помощью CGI. Пользовательское приложение может получить сведения и предоставления данных в Интернете.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения см. в разделе [элементы управления ActiveX](activex-controls.md).

![Клиентские и серверные приложения](../mfc/media/vc38bq1.gif "клиентские и серверные приложения")

MFC предоставляет классы, поддерживающие программирование для Интернета. Можно использовать [COleControl](../mfc/reference/colecontrol-class.md) и [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) и связанных классов MFC для создания элементов управления ActiveX и активные документы. Можно использовать классы MFC, такие как [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) для извлечения файлов и данных с помощью протоколов Интернета, таких как FTP, HTTP и gopher.

## <a name="in-this-section"></a>В этом разделе

- [Классы MFC, связанные с Интернетом](../mfc/internet-related-mfc-classes.md)

- [Сведения о работе с Интернетом по разделам](../mfc/internet-information-by-topic.md)

- [Сведения о работе с Интернетом по задачам](../mfc/internet-information-by-task.md)

- [Технология Active в Интернете](../mfc/active-technology-on-the-internet.md)

- [Основные сведения о WinInet](../mfc/wininet-basics.md)

- [Основы HTML](../mfc/html-basics.md)

## <a name="related-sections"></a>Связанные разделы

- [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)

- [Асинхронные моникеры в Интернете](../mfc/asynchronous-monikers-on-the-internet.md)

- [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [Задачи программирования для интернет-решений MFC](../mfc/mfc-internet-programming-tasks.md)

- [Решения, которые необходимо принять при разработке приложения](../mfc/application-design-choices.md)

- [Создание приложений MFC](../mfc/writing-mfc-applications.md)

- [Тестирование интернет-приложений](../mfc/testing-internet-applications.md)

- [Internet Security](../mfc/internet-security-cpp.md)

- [Поддержка элементов управления DHTML в ATL](../atl/atl-support-for-dhtml-controls.md)

##  <a name="_core_web_sites_for_more_information"></a> Веб-сайтов Дополнительные сведения

Дополнительные сведения о технологии Microsoft Internet см. в разделе [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) веб-сайта. (Ссылки могут изменяться без уведомления).

Этот веб-сайт для разработчиков, содержит сведения об использовании средства разработки Майкрософт и технологий и Важнейшие материалы о недавно прошедшие и предстоящие конференциях. На этой странице можно перейти к многие дополнительные сайты для разработчиков, включая .NET, а также центры разработчиков XML. Можно также загрузить бета-версии SDK и примеры.

[World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) публикует спецификации для HTML, HTTP, CGI и других веб-технологий.

##  <a name="_core_more_internet_help"></a> Дополнительная помощь по Интернету

В разделе "OLE" пакета SDK для Windows содержит дополнительные сведения о программировании OLE. Эти сведения содержат сведения об использовании функций Win32 WinInet, напрямую, а не через классы MFC. Он также содержит общие сведения о технологии Интернета.
