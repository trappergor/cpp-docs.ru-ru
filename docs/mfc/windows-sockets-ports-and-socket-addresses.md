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
ms.openlocfilehash: 791bf07c927e80e65e0fda79fae8a50235bc2def
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371049"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Сокеты Windows. Порты и адреса сокета

В этой статье разъясняются термины "порт" и "адрес", используемые в Windows Sockets.

## <a name="port"></a><a name="_core_port"></a>Порт

Порт определяет уникальный процесс, для которого может быть предоставлена услуга. В данном контексте порт связан с приложением, поддерживающим Windows Sockets. Идея заключается в том, чтобы идентифицировать каждое приложение Windows Sockets уникально, чтобы вы могли иметь более одного приложения Windows Sockets, работая на машине одновременно.

Некоторые порты зарезервированы для обычных служб, таких как FTP. Вы должны избегать использования этих портов, если вы предоставляете такую услугу. Спецификация Windows Sockets подробно описывает эти зарезервированные порты. Файл WINSOCK. H также перечисляет их.

Чтобы позволить Windows Sockets DLL выбрать для вас пригодный для упомятки порт, пройдите 0 в качестве значения порта. MFC выбирает значение порта, превышающее 1024 десятичных. Вы можете получить значение порта, выбранное MFC, позвонив в функцию [cAsyncSocket::GetSockName.](../mfc/reference/casyncsocket-class.md#getsockname)

## <a name="socket-address"></a><a name="_core_socket_address"></a>Розетка адрес

Каждый объект розетки связан с адресом Интернет-протокола (IP) в сети. Как правило, адрес — это имя машины, например "ftp.microsoft.com" или пунктирное число, например "128.56.22.8".

При поиске гнезда обычно не нужно указывать свой адрес.

> [!NOTE]
> Вполне возможно, что ваша машина имеет несколько сетевых карт (или ваше приложение может когда-нибудь запустить на такой машине), каждая из которых представляет собой другую сеть. Если это так, возможно, потребуется указать адрес, чтобы указать, какую сетевую карту будет использовать розетка. Это, несомненно, будет продвинутым использованием и возможной проблемой переносимости.

Дополнительные сведения см. в разделе:

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Работа сокетов с архивами](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также раздел

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
