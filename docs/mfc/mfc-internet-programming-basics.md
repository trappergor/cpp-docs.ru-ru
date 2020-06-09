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
ms.openlocfilehash: 3265bffb393eeff1d8a04a41357e2b138aa0ebf7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615564"
---
# <a name="mfc-internet-programming-basics"></a>Основы программирования для интернет-решений MFC

Корпорация Майкрософт предоставляет множество интерфейсов API для программирования клиентских и серверных приложений. Многие новые приложения записываются для Интернета, а в качестве технологий, возможностей работы с браузерами и параметров безопасности изменяются новые типы приложений. Браузеры работают на клиентских компьютерах, предоставляя доступ к Интернету и отображая HTML-страницы, содержащие текст, графику, элементы управления ActiveX и документы. Серверы предоставляют службы FTP, HTTP и Gopher, а затем запускают приложения серверных расширений с помощью CGI. Пользовательское приложение может получать информацию и предоставлять данные через Интернет.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения см. в разделе [элементы управления ActiveX](activex-controls.md).

![Клиентские и серверные приложения](../mfc/media/vc38bq1.gif "Клиентские и серверные приложения")

MFC предоставляет классы, поддерживающие Интернет. Для записи элементов ActiveX и активных документов можно использовать [COleControl](reference/colecontrol-class.md) и [кдокобжектсервер](reference/cdocobjectserver-class.md) , а также связанные классы MFC. Классы MFC, такие как [Цинтернетсессион](reference/cinternetsession-class.md), [кфтпконнектион](reference/cftpconnection-class.md)и [касинкмоникерфиле](reference/casyncmonikerfile-class.md) , можно использовать для получения файлов и информации с помощью Интернет-протоколов, таких как FTP, HTTP и gopher.

## <a name="in-this-section"></a>В этом разделе

- [Классы MFC, связанные с Интернетом](internet-related-mfc-classes.md)

- [Сведения о Интернете по разделам](internet-information-by-topic.md)

- [Сведения о работе с Интернетом по задачам](internet-information-by-task.md)

- [Активная технология в Интернете](active-technology-on-the-internet.md)

- [Основы WinInet](wininet-basics.md)

- [Основы HTML](html-basics.md)

## <a name="related-sections"></a>Связанные разделы

- [Элементы управления ActiveX в Интернете](activex-controls-on-the-internet.md)

- [Асинхронные моникеры в Интернете](asynchronous-monikers-on-the-internet.md)

- [Расширения Интернета Win32 (WinInet)](win32-internet-extensions-wininet.md)

- [Задачи программирования для интернет-решений MFC](mfc-internet-programming-tasks.md)

- [Решения, которые необходимо принять при разработке приложения](application-design-choices.md)

- [Создание приложений MFC](writing-mfc-applications.md)

- [Тестирование интернет-приложений](testing-internet-applications.md)

- [Интернет — безопасность](internet-security-cpp.md)

- [Поддержка ATL для элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>Веб-сайты для получения дополнительных сведений

Дополнительные сведения о Microsoft Internet Technology см. на веб-сайте [Microsoft Developer Network (MSDN)](https://go.microsoft.com/fwlink/p/?linkid=56322) . (Ссылки могут измениться без предварительного уведомления.)

Этот веб-сайт для разработчиков содержит сведения об использовании средств и технологий разработки Майкрософт, а главные статьи о последних и предстоящих конференциях. На этой странице можно перейти ко многим связанным сайтам разработчиков, включая .NET и центры разработчиков XML. Вы также можете загрузить бета-версии пакетов SDK и примеры.

[Консорциум W3C (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125) публикует спецификации для HTML, HTTP, CGI и других Интернет-технологий.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>Дополнительная справка в Интернете

В разделе OLE Windows SDK содержатся дополнительные сведения о программировании OLE. Эта информация содержит сведения об использовании функций Win32 WinInet напрямую, а не через классы MFC. В нем также содержатся общие сведения о технологиях Интернета.
