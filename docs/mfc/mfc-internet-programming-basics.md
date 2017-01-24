---
title: "Основы программирования для интернет-решений MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active - технология [C++]"
  - "элементы управления ActiveX [C++], Интернет"
  - "Интернет-приложения [C++]"
  - "Интернет-приложения [C++], Активная технология"
  - "Интернет-приложения [C++], элементы управления ActiveX"
  - "Интернет-приложения [C++], написание"
  - "Интернет-содержимое [C++]"
  - "ISAPI"
  - "Расширения ISAPI, программирование с ISAPI"
  - "Фильтры ISAPI, программирование с ISAPI"
  - "программирование [C++], Интернет"
  - "веб-приложения [C++], MFC - классы"
  - "WinInet - классы"
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Основы программирования для интернет-решений MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Корпорация Майкрософт предоставляет множество api\-интерфейсы для программирования и клиентских и серверных приложений.  Создавать множество применений для Интернета, и как технологии, возможности браузера и параметры безопасности, изменения будут записаны новые типы приложений.  Браузеры выполняются на клиентских компьютерах, предоставляя доступ в интернет, и страницы HTML, содержащая текст, графические элементы управления ActiveX и документы.  Серверы предоставляют FTP, HTTP и службы gopher приложения и расширения сервера выполняется с помощью CGI.  Пользовательское приложение может получить данные и предоставлять данные в Интернете.  
  
 ![Клиентские и серверные приложения](../mfc/media/vc38bq1.png "vc38BQ1")  
  
 MFC предоставляет классы, поддерживающие программирование Интернета.  Можно использовать функции [COleControl](../mfc/reference/colecontrol-class.md) и [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) и связывать классы MFC для создания элементов управления ActiveX и активные документы.  Можно использовать классы MFC \(например, [CInternetSession](../Topic/CInternetSession%20Class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md) и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) для извлечения файлов и информацию с помощью протоколы Интернета, таких как FTP, HTTP и gopher.  
  
## Содержание  
  
-   [Для связанных классов MFC](../mfc/internet-related-mfc-classes.md)  
  
-   [Сведения в интернете разделом](../Topic/Internet%20Information%20by%20Topic.md)  
  
-   [Сведения в интернете задачей](../mfc/internet-information-by-task.md)  
  
-   [Технология активной в Интернете](../mfc/active-technology-on-the-internet.md)  
  
-   [Основы WinInet](../mfc/wininet-basics.md)  
  
-   [Основы HTML](../mfc/html-basics.md)  
  
-   [Основы HTTP](../mfc/http-basics.md)  
  
## Связанные разделы  
  
-   [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)  
  
-   [Активные документы в Интернете](../Topic/Active%20Documents%20on%20the%20Internet.md)  
  
-   [Асинхронные моникеры в Интернете](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Расширения Win32 Интернета \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [Задачи интернет\-программирования MFC](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Варианты разработки приложения](../mfc/application-design-choices.md)  
  
-   [Создание приложения MFC](../mfc/writing-mfc-applications.md)  
  
-   [Интернет\-приложения тестирования](../mfc/testing-internet-applications.md)  
  
-   [Уровень безопасности в интернете](../Topic/Internet%20Security%20\(C++\).md)  
  
-   [Поддержка для элементов управления ATL DHTML](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> Веб\-сайты дополнительные сведения  
 Дополнительные сведения о технологии Microsoft Интернета см. на веб\-сайте [Microsoft Developer Network \(MSDN\)](http://go.microsoft.com/fwlink/?LinkID=56322). \(Ссылки, могут изменяться без предварительного уведомления\).  
  
 Это веб\-сайт для разработчиков содержит сведения об использовании средств разработки и технологий Майкрософт и основные события о последних и предстоящих конференциях.  На этой странице можно гиперссылку для нескольких связанных сайтов разработчика, включая .NET, и разработчик XML по центру.  Можно также загрузить пакет SDK и примеры бета.  
  
 [Консорциум W3C \(W3C\)](http://go.microsoft.com/fwlink/?LinkID=37125) публикует спецификации для HTML, HTTP, CGI и других технологий интернет.  
  
##  <a name="_core_more_internet_help"></a> Более справки в интернете  
 OLE раздел [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] содержит дополнительные сведения о программировании OLE.  Эти сведения предоставляют сведения об использовании функции Win32 WinInet напрямую, а не посредством классов MFC.  Он также содержит данные о технологиях просмотра Интернета.  
  
## См. также  
 [MFC Internet Programming \(NIB\)](http://msdn.microsoft.com/ru-ru/0f7a1f3a-385b-4d56-a55b-0d766840c58a)