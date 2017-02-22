---
title: "Сокеты Windows. Преобразование строк | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сокеты [C++], проблемы преобразования строк многобайтовых знаков"
  - "преобразование строк, многобайтовые строки символов"
  - "Сокеты Windows [C++], преобразование строк многобайтовых знаков"
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Сокеты Windows. Преобразование строк
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данная статья базы знаний 2 и сопутствующей описан ряд проблем в программировании Windows SSL.  В этой статье рассматриваются преобразования строк.  Другие проблемы описаны в [Windows SSL. Блокировка](../Topic/Windows%20Sockets:%20Blocking.md) и [Windows SSL. Порядок байтов](../mfc/windows-sockets-byte-ordering.md).  
  
 При использовании или является производным от класса [CAsyncSocket](../Topic/CAsyncSocket%20Class.md), необходимо самостоятельно управлять этих проблем.  При использовании или является производным от класса [CSocket](../mfc/reference/csocket-class.md), MFC управляет их автоматически.  
  
## Преобразования строк  
 Если сообщения между приложениями, которые используют строки, которые хранятся в различных форматах юникод, например юникод или многобайтовые кодировки \(многобайтовая кодировка\) или между одним из этих и приложением с помощью символьные строки ANSI, должны самостоятельно управлять преобразования в `CAsyncSocket`.  Объект `CArchive`, используемый с объектом `CSocket` управляет это преобразование для вас через возможности класса [CString](../atl-mfc-shared/reference/cstringt-class.md).  Дополнительные сведения см. в спецификации Windows SSL, расположенная в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Windows SSL. С помощью класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows SSL. С помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows SSL. Фон](../mfc/windows-sockets-background.md)  
  
-   [Windows SSL. Сокеты потока](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows SSL. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)