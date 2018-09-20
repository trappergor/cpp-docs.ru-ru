---
title: 'Сокеты Windows: Последовательность операций | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9667bf7359677d00b54023cb5542ffd7977baa02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376056"
---
# <a name="windows-sockets-sequence-of-operations"></a>Сокеты Windows. Последовательность операций

В этой статье показано, бок о бок, последовательность операций для сокета сервера и сокета клиента. Так как сокеты используют `CArchive` объекты, они обязательно [потока сокетов](../mfc/windows-sockets-stream-sockets.md).

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Последовательность операций для подключения сокета Stream

Вплоть до создания `CSocketFile` объекта, следующая последовательность является точным (с некоторыми отличиями параметр) для обоих `CAsyncSocket` и `CSocket`. С этого момента последовательность подходит исключительно для `CSocket`. В следующей таблице показано, что последовательность операций по настройке взаимодействия между клиентом и сервером.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>Настройка обмена данными между клиентом и сервером

|Сервер|"Клиент";|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - или -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - или обоих-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - или -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - или обоих-|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - или -<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - или -<br /><br /> `arOut << dwValue;`6|

1. Где *nPort* — это номер порта. См. в разделе [Windows Sockets: порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md) Дополнительные сведения о портах.

2. Сервер всегда необходимо указать порт, чтобы клиенты могли подключаться. `Create` Вызовов иногда также указывает адрес. На стороне клиента можно используете параметры по умолчанию, которые запрашиваются MFC использовать любой доступный порт.

3. Где *nPort* — это номер порта и *strAddr* машинный адрес или адрес протокола Интернета (IP).

4. Адреса машин может принимать различные формы: «ftp.microsoft.com», «microsoft.com». IP-адреса используйте форму «с точками номер» «127.54.67.32». `Connect` Функция проверяет, находится ли адрес точечно номер (несмотря на то, что он проверяет номер — это допустимый машина в сети). В противном случае `Connect` предполагается, что имя компьютера, одного из других форм.

5. При вызове `Accept` на стороне сервера, можно передать ссылку на объект сокета. Необходимо сначала создать этот объект, но не следует вызывать `Create` для него. Имейте в виду, что если этот объект сокета идет области, соединение закрывается. Новый объект, который подключается MFC **СОКЕТА** обработки. Можно создать сокет в стеке, как показано или в куче.

6. Архив и файл сокетов, закрываются, если они выходят за пределы области. Также вызывает деструктор объекта сокета [закрыть](../mfc/reference/casyncsocket-class.md#close) функция-член для объекта сокета, когда объект выходит за пределы области или удаляется.

## <a name="additional-notes-about-the-sequence"></a>Дополнительные замечания о последовательности

Для сокета потока является последовательность вызовов, показано в предыдущей таблице. Сокеты датаграмм, которые являются без установления соединения, не требуют [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect), [прослушивания](../mfc/reference/casyncsocket-class.md#listen), и [Accept](../mfc/reference/casyncsocket-class.md#accept) вызовы (несмотря на то, что при необходимости можно использовать `Connect`). Вместо этого Если вы используете класс `CAsyncSocket`, использовать сокеты датаграмм `CAsyncSocket::SendTo` и `ReceiveFrom` функций-членов. (Если вы используете `Connect` с сокета датаграмм, использовании `Send` и `Receive`.) Так как `CArchive` не работает с помощью датаграмм, не используйте `CSocket` с архивом если сокет датаграммы.

[CSocketFile](../mfc/reference/csocketfile-class.md) не поддерживает все `CFile`его функциональности. `CFile` такие элементы, как `Seek`, который не имеет смысла для подключения сокета, будут недоступны. По этой причине некоторые по умолчанию MFC `Serialize` функции не совместимы с `CSocketFile`. Это особенно верно для `CEditView` класса. Не следует пытаться сериализации `CEditView` данных с помощью `CArchive` объект присоединен к `CSocketFile` с помощью `CEditView::SerializeRaw`; используйте `CEditView::Serialize` вместо (не документировано). [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) функция ожидает, что файл, который имеют функции, такие как `Seek`, в котором `CSocketFile` не поддерживает.

Дополнительные сведения:

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Класс CSocket](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

