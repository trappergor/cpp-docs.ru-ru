---
title: Сокеты Windows. Порты и адреса сокета
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: c33ec1376c1898272cf80e8d77c5cc273e16f9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389376"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Сокеты Windows. Порты и адреса сокета

Здесь объясняются термины «порт» и «адрес», как используемого с помощью сокетов Windows.

##  <a name="_core_port"></a> Порт

Порт определяет уникальный процесс, для которого может предоставляться услуга. В контексте присутствует порт связан с приложение, поддерживающее Windows Sockets. Идея состоит в том, для уникальной идентификации каждого приложения Windows Sockets, тем самым давая возможность более чем одним приложением Windows Sockets, работающей на машине, в то же время.

Определенные порты, зарезервированы для распространенных служб, таких как FTP. Следует избегать использования этих портов, если вы предоставляете такого рода службы. В спецификации Windows Sockets подробно эти резервные порты. Файл WINSOCK. H также перечислены их.

Чтобы библиотеки DLL Windows Sockets выберите порт может использоваться для, передайте 0 в качестве значения порта. MFC выбирает значение порта больше 1024 decimal. Можно получить номер порта, выбранное в MFC, вызвав [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) функция-член.

##  <a name="_core_socket_address"></a> Адрес сокета

Каждый объект сокета связан с адресом протокола Интернета (IP) в сети. Как правило адрес — это имя компьютера, например «ftp.microsoft.com», или точками номер, например «128.56.22.8».

При выполнении поиска создать сокет, обычно не нужно указать свой адрес.

> [!NOTE]
>  Возможно, что компьютер имеет несколько сетевых карт (или когда-нибудь может выполняться приложение такому компьютеру), каждый из которых представляет другую сеть. Если это так, может потребоваться предоставить адрес, чтобы указать, какой сетевой карты, сокет будет использовать. Это быть расширенное использование и проблема возможных переносимости.

Дополнительные сведения:

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Работа сокетов с архивами](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
