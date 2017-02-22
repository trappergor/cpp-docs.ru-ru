---
title: "Сокеты Windows. Порты и адреса сокета | Microsoft Docs"
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
  - "адреса [C++], сокет"
  - "порты [C++]"
  - "порты [C++], определение"
  - "сокеты [C++], адреса"
  - "сокеты [C++], порты"
  - "Сокеты Windows [C++], адреса"
  - "Сокеты Windows [C++], порты"
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Сокеты Windows. Порты и адреса сокета
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается термин «порт» и «адрес», как используется с Windows SSL.  
  
##  <a name="_core_port"></a> Port  
 Задает уникальный порт процесса, для которого служба может быть предоставлена.  Присутствующем в контексте, порт связан с приложением, которое поддерживает Windows SSL.  Рекомендуется указывать каждое приложение Windows sockets уникальным, поэтому следует имеет более одного выполнения приложения Windows SSL на компьютере одновременно.  
  
 Некоторые порты зарезервировано для общих служб, например FTP.  Следует избегать использования этих портов без предоставления этот тип службы.  Сведения спецификации Windows эти порты SSL зарезервировано.  Файл WINSOCK.H также перечислены их.  
  
 Чтобы включить Windows sockets DLL выделяет годный к использованию порт автоматически, передает порт 0 в качестве значения.  MFC выделяет порт значение, десятичное число 1,024.  Можно извлечь значение порт, который выбрал MFC, вызвав функцию\-член [CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md).  
  
##  <a name="_core_socket_address"></a> Адрес сокета  
 Каждый объект сокета связан с адресом \(IP\) протокол IP в сети.  Как правило, адрес имя компьютера, например «ftp.microsoft.com» или точки, число, например «128.56.22.8».  
  
 При поиске создание сокет, обычно не требуется указывать собственный адрес.  
  
> [!NOTE]
>  Возможно, что компьютер имеет несколько сетевые карты \(или приложение когда\-нибудь может выполняться на одном компьютере\), каждый из которых представляет отдельную сети.  Если в этом случае может потребоваться предоставить адрес для определения, карту сети сокет будет использовать.  Это может быть расширенные потреблением и возможной причиной проблемы 64\-битной.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Windows SSL. С помощью класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows SSL. С помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows SSL. Как работают с архивами сокеты](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows SSL. Сокеты потока](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows SSL. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)