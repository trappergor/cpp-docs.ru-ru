---
title: Основы программирования для Интернет MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6896daddc0eb900f9e2a29497eb2dd8a1dc78446
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="mfc-internet-programming-basics"></a>Основы программирования для интернет-решений MFC
Корпорация Майкрософт предоставляет множество API-интерфейсы для программирования клиентских и серверных приложений. Для использования в Интернете, записываются много новых приложений и технологии, возможности браузера и изменение параметров безопасности, будут записаны новые типы приложений. Браузеры запуска на клиентских компьютерах, предоставление доступа к Интернет и отображения HTML-страницы, содержащие текст, графики, элементы управления ActiveX и документы. Серверы предоставляют FTP, HTTP и gopher службы и запустите серверные расширения приложения с помощью CGI. Пользовательские приложения можно получить сведения и предоставления данных в Интернете.  
  
 ![Клиентские и серверные приложения](../mfc/media/vc38bq1.gif "vc38bq1")  
  
 MFC предоставляет классы, поддерживающие Интернет-программирование. Можно использовать [COleControl](../mfc/reference/colecontrol-class.md) и [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) и связанных классов MFC для создания элементов управления ActiveX и активные документы. Можно использовать классы MFC, такие как [CInternetSession](../mfc/reference/cinternetsession-class.md), [классе CFtpConnection](../mfc/reference/cftpconnection-class.md), и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) для получения файлов и данных, используя протоколы Интернета, таких как FTP, HTTP и gopher.  
  
## <a name="in-this-section"></a>В этом разделе  
  
-   [Классы MFC, связанные с Интернетом](../mfc/internet-related-mfc-classes.md)  
  
-   [Сведения о работе с Интернетом по разделам](../mfc/internet-information-by-topic.md)  
  
-   [Сведения о работе с Интернетом по задачам](../mfc/internet-information-by-task.md)  
  
-   [Технология Active в Интернете](../mfc/active-technology-on-the-internet.md)  
  
-   [Основные сведения о WinInet](../mfc/wininet-basics.md)  
  
-   [Основы HTML](../mfc/html-basics.md)  
  
## <a name="related-sections"></a>Связанные разделы  
  
-   [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)  
  
-   [Активные документы в Интернете](../mfc/active-documents-on-the-internet.md)  
  
-   [Асинхронные моникеры в Интернете](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [Задачи программирования для интернет-решений MFC](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Решения, которые необходимо принять при разработке приложения](../mfc/application-design-choices.md)  
  
-   [Создание приложений MFC](../mfc/writing-mfc-applications.md)  
  
-   [Тестирование интернет-приложений](../mfc/testing-internet-applications.md)  
  
-   [Интернет-безопасность](../mfc/internet-security-cpp.md)  
  
-   [Поддержка элементов управления DHTML в ATL](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> Веб-сайтов для получения дополнительной информации  
 Дополнительные сведения о технологии Microsoft Internet см. в разделе [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) веб-сайта. (Ссылки могут изменяться без предварительного уведомления).  
  
 Этот веб-сайт для разработчиков, содержит сведения об использовании средства разработки Майкрософт и технологий и главные темы о прошедших или предстоящих конференций. На этой странице можно перейти на многие узлы связанные разработчика, включая .NET и центры разработчиков XML. Можно также загрузить бета-версии SDK и образцы.  
  
 [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) публикует спецификации для HTML, HTTP, CGI и других веб-технологий.  
  
##  <a name="_core_more_internet_help"></a> Дополнительную информацию для Интернета  
 Раздел OLE пакета Windows SDK содержит дополнительные сведения о программировании OLE. Эти сведения предоставляют подробные сведения об использовании функций Win32 WinInet напрямую, а не через классы MFC. Он также содержит общие сведения о технологии Интернета.  
  
## <a name="see-also"></a>См. также  



