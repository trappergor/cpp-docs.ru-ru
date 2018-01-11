---
title: "Сокеты Windows: Последовательность операций | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70765d94b0104cf905130ce043c2b0e35b26a41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-sequence-of-operations"></a>Сокеты Windows. Последовательность операций
В этой статье рассмотрены рядом друг с другом, последовательность операций для сокета сервера и клиентского сокета. Так как использование сокетов `CArchive` объекты, они обязательно [потока сокетов](../mfc/windows-sockets-stream-sockets.md).  
  
## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Последовательность операций для подключения сокета потока  
 До момента создания `CSocketFile` объекта следующую последовательность является точным (с некоторыми отличиями параметра) для обоих `CAsyncSocket` и `CSocket`. С этого момента последовательности подходит исключительно для `CSocket`. В следующей таблице показаны последовательность операций для настройки связи между клиентом и сервером.  
  
### <a name="setting-up-communication-between-a-server-and-a-client"></a>Настройка обмена данными между клиентом и сервером  
  
|Сервер|"Клиент";|  
|------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - или -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - или -|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - или -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - или -|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - или -<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - или -<br /><br /> `arOut << dwValue;`6|  
  
 1. Где `nPort` — номер порта. В разделе [Windows Sockets: порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md) подробные сведения о портах.  
  
 2. Сервер всегда необходимо указать порт, чтобы клиенты могли подключаться. **Создать** вызов иногда также указывает адрес. На стороне клиента используйте параметры по умолчанию, которые попросите MFC, позволяющий использовать любой доступный порт.  
  
 3. Где `nPort` — номер порта и *strAddr* представляет машинный адрес или адрес протокола Интернета (IP).  
  
 4. Адреса компьютера может принимать несколько форм: «ftp.microsoft.com», «microsoft.com». IP-адреса используйте форму «точечные номер» «127.54.67.32». **Connect** функция проверяет, является ли адрес пунктирная номер (несмотря на то, что он не проверяет, убедитесь, что число является допустимым компьютеру в сети). В противном случае **Connect** предполагается имя машины одной из других форм.  
  
 5. При вызове **Accept** на стороне сервера можно передать ссылку на объект сокета. Вначале необходимо создать этот объект, но не нужно вызывать **создать** для него. Имейте в виду, что если этот объект сокета идет области видимости, соединение закрывается. MFC подключается новый объект в **СОКЕТА** обработки. Вы можете создать сокет, как показано в стеке или в куче.  
  
 6. Архив и файл сокетов закрываются при выходе из области. Также вызывает деструктор объекта сокета [закрыть](../mfc/reference/casyncsocket-class.md#close) функции-члена для объекта сокета, когда объект выходит за пределы области или удаляется.  
  
## <a name="additional-notes-about-the-sequence"></a>Дополнительные замечания о последовательности  
 Для сокета потока является последовательность вызовов, показано в предыдущей таблице. Сокеты датаграмм, которые являются без установления соединения, не требуют [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect), [прослушивания](../mfc/reference/casyncsocket-class.md#listen), и [Accept](../mfc/reference/casyncsocket-class.md#accept) вызовов (несмотря на то, что вы можете использовать **Подключения**). Вместо этого при использовании класса `CAsyncSocket`, сокеты датаграмм используют `CAsyncSocket::SendTo` и `ReceiveFrom` функции-члены. (При использовании **Connect** на сокет датаграммы используется **отправки** и **Receive**.) Поскольку `CArchive` не работает с датаграмм, не используйте `CSocket` архивом если сокет датаграммы.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) поддерживают не все `CFile`его функциональные возможности; `CFile` такие элементы, как `Seek`, который не имеет смысла для соединения сокета, будут недоступны. По этой причине некоторые по умолчанию MFC `Serialize` функции не совместимы с `CSocketFile`. Это особенно верно для `CEditView` класса. Не рекомендуется для сериализации `CEditView` данных с помощью `CArchive` объект присоединен к `CSocketFile` с помощью `CEditView::SerializeRaw`; используйте **CEditView::Serialize** вместо (не документированы). [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) функция ожидает объект файла, содержат функции, такие как `Seek`, которая `CSocketFile` не поддерживает.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket-класс](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)   
 [CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

