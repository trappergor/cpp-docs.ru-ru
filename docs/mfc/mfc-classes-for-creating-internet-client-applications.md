---
title: "Классы MFC для создания клиентских приложений в Интернете | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "классы [C++], MFC - библиотека"
  - "Интернет-приложения, MFC - библиотека"
  - "клиентские интернет-приложения, MFC - библиотека"
  - "MFC - библиотека, WinInet - классы"
  - "WinInet - классы, классы"
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы MFC для создания клиентских приложений в Интернете
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет следующие классы и глобальные функции для создания приложений Интернет\-клиента.  Отступ указывает, что класс является производным от класса unindented над ним.  `CGopherFile` и `CHttpFile` являются производными от `CInternetFile`, например.  Эти классы и глобальные функции объявляются в AFXINET.H, за исключением `CFileFind`, который объявлен в AFX.H.  
  
## Классы  
  
-   [CInternetSession](../Topic/CInternetSession%20Class.md)  
  
-   [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
    -   [CFtpConnection](../mfc/reference/cftpconnection-class.md)  
  
    -   [CGopherConnection](../mfc/reference/cgopherconnection-class.md)  
  
    -   [CHttpConnection](../mfc/reference/chttpconnection-class.md)  
  
-   [CInternetFile](../mfc/reference/cinternetfile-class.md)  
  
    -   [CGopherFile](../mfc/reference/cgopherfile-class.md)  
  
    -   [CHttpFile](../Topic/CHttpFile%20Class.md)  
  
-   [CFileFind](../mfc/reference/cfilefind-class.md)  
  
    -   [CFtpFileFind](../Topic/CFtpFileFind%20Class.md)  
  
    -   [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)  
  
-   [CGopherLocator](../Topic/CGopherLocator%20Class.md)  
  
-   [CInternetException](../mfc/reference/cinternetexception-class.md)  
  
## Глобальные функции  
  
-   [AfxParseURL](../Topic/AfxParseURL.md)  
  
-   [AfxGetInternetHandleType](../Topic/AfxGetInternetHandleType.md)  
  
-   [AfxThrowInternetException](../Topic/AfxThrowInternetException.md)  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Необходимые компоненты для клиентских классов в Интернете](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)