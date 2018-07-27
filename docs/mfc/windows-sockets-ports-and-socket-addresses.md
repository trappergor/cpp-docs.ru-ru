---
title: 'Сокеты Windows: Порты и адреса сокета | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ea9b8a39de8d36ecb621164d98e072a4041211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383991"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Сокеты Windows. Порты и адреса сокета
Объясняются термины «порт» и «адрес» как при использовании Windows Sockets.  
  
##  <a name="_core_port"></a> Порт  
 Порт определяет уникальный процесс, для которого могут быть предоставлены службой. В контексте присутствует порта — связан с приложением, которая поддерживает Windows Sockets. Идея заключается в том, чтобы однозначно идентифицировать каждого приложения Windows Sockets, поэтому может иметь более одного приложения Windows Sockets, выполняющийся на компьютере, в то же время.  
  
 Определенные порты, зарезервированы для общих служб, таких как FTP. Следует избегать использования этих портов, если вы указываете такого рода службы. Спецификации Windows Sockets подробное описание этих зарезервированных портов. Файл WINSOCK. H перечислены их.  
  
 Чтобы позволить выберите для использования порта библиотека DLL Windows Sockets, передайте 0 как номер порта. MFC выбирает больше 1024 десятичное значение порта. Можно получить номер порта, выбранное в MFC путем вызова [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) функции-члена.  
  
##  <a name="_core_socket_address"></a> Адреса сокета  
 Каждый объект сокета связан с адресом протокола Интернета (IP) в сети. Как правило адрес является имя компьютера, например «ftp.microsoft.com» или пунктирная число, например «128.56.22.8».  
  
 При выполнении поиска создать сокет, обычно не требуется указать свой адрес.  
  
> [!NOTE]
>  Это возможно, ваш компьютер имеет несколько сетевых плат (или когда-нибудь может выполняться приложение на такой машине), каждый из которых представляет другую сеть. В этом случае может потребоваться предоставить адрес, чтобы указать, какой сетевой адаптер будет использовать сокета. Это быть расширенное использование и проблемы переносимости возможных.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Работа сокетов с архивами](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)

