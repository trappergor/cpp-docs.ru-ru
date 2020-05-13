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
ms.openlocfilehash: 5a8fb7bf07ec631869075c5977dcec468143ad56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366289"
---
# <a name="mfc-internet-programming-basics"></a>Основы программирования для интернет-решений MFC

Корпорация Майкрософт предоставляет множество AI для программирования как клиентских, так и серверных приложений. Многие новые приложения пишутся для Интернета, и по мере изменения технологий, возможностей браузера и параметров безопасности будут писаться новые типы приложений. Браузеры работают на клиентских компьютерах, предоставляя доступ к Всемирной паутине и отображая HTML-страницы, содержащие текст, графику, элементы управления ActiveX и документы. Серверы предоставляют услуги FTP, HTTP и gopher, а также заходят приложения для расширения серверов с помощью CGI. Пользовательское приложение может получать информацию и предоставлять данные в Интернете.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации [см.](activex-controls.md)

![Клиентские и серверные приложения](../mfc/media/vc38bq1.gif "Клиентские и серверные приложения")

MFC предоставляет классы, поддерживающие интернет-программирование. Для записи элементов управления ActiveX и активных документов можно использовать [COleControl](../mfc/reference/colecontrol-class.md) и [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) и связанные с ними классы MFC. Вы можете использовать классы MFC, такие как [CInternetSession,](../mfc/reference/cinternetsession-class.md) [CFtpConnection](../mfc/reference/cftpconnection-class.md)и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) для получения файлов и информации с помощью интернет-протоколов, таких как FTP, HTTP и суслик.

## <a name="in-this-section"></a>в этом разделе

- [Занятия МФЦ, связанные с Интернетом](../mfc/internet-related-mfc-classes.md)

- [Информация в Интернете по темам](../mfc/internet-information-by-topic.md)

- [Сведения о работе с Интернетом по задачам](../mfc/internet-information-by-task.md)

- [Активные технологии в Интернете](../mfc/active-technology-on-the-internet.md)

- [Основы WinInet](../mfc/wininet-basics.md)

- [Основы HTML](../mfc/html-basics.md)

## <a name="related-sections"></a>Связанные разделы

- [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)

- [Асинхронные моникеры в Интернете](../mfc/asynchronous-monikers-on-the-internet.md)

- [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [Задачи программирования для интернет-решений MFC](../mfc/mfc-internet-programming-tasks.md)

- [Решения, которые необходимо принять при разработке приложения](../mfc/application-design-choices.md)

- [Создание приложений MFC](../mfc/writing-mfc-applications.md)

- [Тестирование интернет-приложений](../mfc/testing-internet-applications.md)

- [Интернет-безопасность](../mfc/internet-security-cpp.md)

- [Поддержка ATL для управления DHTML](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>Веб-сайты для получения дополнительной информации

Для получения дополнительной информации об Интернет-технологиях Майкрософт можно ознакомиться на веб-сайте [Microsoft Developer Network (MSDN).](https://go.microsoft.com/fwlink/p/?linkid=56322) (Ссылки могут меняться без предварительного уведомления.)

Этот веб-сайт для разработчиков содержит информацию об использовании инструментов и технологий разработки Майкрософт, а также топ-истории о последних и предстоящих конференциях. С этой страницы вы можете перейти на многие связанные сайты разработчиков, включая .NET, и XML Центры разработчиков. Вы также можете скачать бета-версии SDKs и образцы.

[Консорциум World Wide Web Consortium (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125) публикует спецификации для HTML, HTTP, CGI и других технологий World Wide Web.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>Больше справки для интернета

Раздел OLE SDK Windows содержит дополнительную информацию о программировании OLE. Эта информация содержит подробную информацию об использовании функций Win32 WinInet напрямую, а не через классы MFC. Он также содержит обзорную информацию об интернет-технологиях.
