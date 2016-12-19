---
title: "Использование MFC для упрощения создания клиентских приложений в Интернете | Microsoft Docs"
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
  - "Интернет-приложения, MFC - библиотека"
  - "клиентские интернет-приложения, MFC - библиотека"
  - "MFC - библиотека, Интернет-приложения"
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование MFC для упрощения создания клиентских приложений в Интернете
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Классы инкапсулируют функции расширения Microsoft Foundation Win32 Интернета \(WinInet\) способом, который обеспечивает знакомый контекст для программистов MFC.  MFC предоставляет 3 класса файла Интернета \([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../Topic/CHttpFile%20Class.md) и [CGopherFile](../mfc/reference/cgopherfile-class.md)\) из производного класса [CStdioFile](../Topic/CStdioFile%20Class.md).  Не только эти классы позволяют извлекать и управление " " данных Интернета программистам, используемой `CStdioFile` для локальных файлов, но с этими классами можно локальные файлы и файлы Интернета дескриптора в последовательном, прозрачном способом.  
  
 Классы MFC WinInet обеспечивают те же функциональные возможности, `CStdioFile` для данных, которые передаются через Интернет.  Abstract этих классов протоколы Интернета для HTTP, FTP и gopher в высокоуровневый программный интерфейс, реализации быстрый и простой способ создания приложения для зависимым.  Например, для подключения к FTP\-серверу по\-прежнему требует нескольких действий на низком уровне, но разработчики MFC, необходимости вызывать один к `CInternetSession::GetFTPConnection` для создания создается подключение.  
  
 Кроме того, классы MFC WinInet обеспечивает следующие преимущества:  
  
-   Буферизованный ВВОДА\-ВЫВОДА  
  
-   Типобезопасные дескрипторы для данных.  
  
-   Параметры по умолчанию для многих функций  
  
-   Обработка исключений для общих ошибок Интернета  
  
-   Автоматическая очистка открытых дескрипторов и подключений  
  
## См. также  
 [Расширения Интернета Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Использование WinInet для упрощения создания клиентских приложений в Интернете](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)