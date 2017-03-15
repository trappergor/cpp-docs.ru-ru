---
title: "Сокеты Windows в MFC | Microsoft Docs"
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
  - "MFC [C++], Сокеты Windows"
  - "сокеты [C++], MFC - библиотека"
  - "сокеты [C++], модели программирования"
  - "Сокеты Windows [C++], поддержка MFC"
  - "Сокеты Windows [C++], модели программирования"
  - "WINSOCK.DLL"
  - "WSOCK32.DLL"
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Сокеты Windows в MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  MFC поддерживает SSL Windows 1, но не поддерживает [Windows 2 SSL](http://msdn.microsoft.com/library/windows/desktop/ms740673).  Windows 2 сначала погруженные SSL с Windows 98 и версия, включенному в Windows 2000.  
  
 MFC предоставляет 2 модели написания коммуникационные программы сети с Windows SSL, овеществленной в 2 классов MFC.  В этом разделе описываются поддержки сокетов MFC этих моделей и дальнейших подробностей.  «Сокет» конечная точка сообщения: объект, с помощью которого приложение взаимодействует с другими приложениями Windows SSL по сети.  
  
 Сведения о Windows SSL, включая объяснение понятий сокета см. в разделе [Windows SSL. Фон](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a> Модель программирования сокетов  
 2 Модели программирования MFC Windows sockets поддерживаются следующие классы:  
  
-   `CAsyncSocket`  
  
     Этот класс инкапсулирует API Windows SSL.  [CAsyncSocket](../Topic/CAsyncSocket%20Class.md) для программистов, знающие программирование сети и желающих возможности программирования непосредственно в API сокетов, но также можно поддерживать функций обратного вызова для получения уведомления событий сети.  Кроме сокетов пакета в объектно\-ориентированной форме для использования в C\+\+, единственным дополнительная абстракция предоставляет этого класса преобразования некоторые сокет\- связанные сообщения Windows в обратные вызовы.  Дополнительные сведения см. в разделе [Windows SSL. Уведомления сокета](../Topic/Windows%20Sockets:%20Socket%20Notifications.md).  
  
-   `CSocket`  
  
     Этот класс, производный от `CAsyncSocket`, предоставляет абстракцию уровня для работы с сокетами через объект [CArchive](../mfc/reference/carchive-class.md) библиотеки MFC.  Использование сокет с архивом значительно напоминает протоколу сериализации файла MFC.  Это облегчает использование, чем модель `CAsyncSocket`.  [CSocket](../mfc/reference/csocket-class.md) многие функции\-члены наследуется из `CAsyncSocket`, которые инкапсулируют API Windows SSL; можно использовать некоторые из этих функций и сокеты общие сведения о программировании в целом.  Но `CSocket` управляет множество аспектов сообщений, необходимо сделать использование или необработанные API или класс `CAsyncSocket`.  Самое главное, `CSocket` предоставляет блокировку \(с фоновый обработки сообщений Windows\), которая необходима для синхронной операции `CArchive`.  
  
 Создание и использование `CSocket` и объектов `CAsyncSocket` приведены в разделе [Windows SSL. С помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows SSL. С помощью класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Библиотека DLL Windows SSL  
 Операционные системы Microsoft Windows предоставляют библиотеки динамической компоновки Windows \(DLL\) SSL.  Предоставляет Visual C\+\+ соответствующие файлы заголовка и библиотеки и спецификация Windows SSL.  
  
> [!NOTE]
>  В Windows NT и Windows 2000, Windows 16 поддержка SSL для разрядных приложений на основе WINSOCK.DLL.  Для 32\-разрядных приложений поддержка в WSOCK32.DLL.  Предоставленные интерфейсы API идентичны за исключением того, что 32\-разрядные версии имеют расширенные параметры в 32 битам.  В Win32, обеспечивается потокобезопасность.  
  
 Дополнительные сведения о Windows SSL см. в разделе:  
  
-   [Windows SSL. Сокеты потока](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows SSL. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows SSL. С помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows SSL. Последовательность операций](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md)  
  
-   [Windows SSL. Пример с помощью сокетов архивы](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows SSL. Как работают с архивами сокеты](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows SSL. С помощью класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows SSL. Наследование от классов socket](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows SSL. Уведомления сокета](../Topic/Windows%20Sockets:%20Socket%20Notifications.md)  
  
-   [Windows SSL. Блокировка](../Topic/Windows%20Sockets:%20Blocking.md)  
  
-   [Windows SSL. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows SSL. Преобразования строк](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows SSL. Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## См. также  
 [Сокеты Windows](../mfc/windows-sockets.md)