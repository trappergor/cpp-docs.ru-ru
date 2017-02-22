---
title: "CSocket Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocket class"
  - "SOCKET handle"
  - "sockets classes"
  - "WinSock CSocket class"
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Наследуется от `CAsyncSocket`, наследует инкапсуляцию API Windows sockets и представляет более высокий уровень абстракции, чем из объекта `CAsyncSocket`.  
  
## Синтаксис  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSocket::CSocket](../Topic/CSocket::CSocket.md)|Создает объект `CSocket`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSocket::Attach](../Topic/CSocket::Attach.md)|Вложение дескриптор **СОКЕТ** к объекту `CSocket`.|  
|[CSocket::CancelBlockingCall](../Topic/CSocket::CancelBlockingCall.md)|Отменяет блокирующий вызов, который в данный момент.|  
|[CSocket::Create](../Topic/CSocket::Create.md)|Создает сокет.|  
|[CSocket::FromHandle](../Topic/CSocket::FromHandle.md)|Возвращает указатель на объект `CSocket` заданный дескриптор **СОКЕТ**.|  
|[CSocket::IsBlocking](../Topic/CSocket::IsBlocking.md)|Определяет, является ли блокирующий вызов выполняется.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSocket::OnMessagePending](../Topic/CSocket::OnMessagePending.md)|Вызываемый для обработки ожидающих сообщений при ожидании блокирующий вызов, чтобы завершить.|  
  
## Заметки  
 `CSocket` работает с классами `CSocketFile` и `CArchive` для управления отправки и получения данных.  
  
 Объект `CSocket` предоставляет также отключить, который необходим для синхронной операции `CArchive`.  Блокировка действует, как `Receive`, `Send`, `ReceiveFrom`, `SendTo` и `Accept` \(все\), унаследованное от `CAsyncSocket` не возвращает ошибку `WSAEWOULDBLOCK` в `CSocket`.  Вместо этого эти функции будут ожидать, пока операция не завершится.  Кроме того, вызов завершает исходный ошибка `WSAEINTR` если `CancelBlockingCall` вызываются, пока этих функций отключить.  
  
 Чтобы использовать объект `CSocket`, вызовите конструктор, то вызов `Create` чтобы создать основной маркер `SOCKET` \(тип `SOCKET`\).  Параметры по умолчанию `Create` создает сокет потока, но если не используется, когда сокет с объектом `CArchive`, то можно указать параметр для создания сокет датаграмм вместо или привязать к конкретному порту для создания сокета сервера.  Подключитесь к гнезду клиента с помощью `Connect``Accept` на стороне клиента и на стороне сервера.  Затем создайте объект `CSocketFile` и свяжите его к объекту `CSocket` в конструкторе `CSocketFile`.  Затем создайте объект `CArchive` для отправки и получения данные \(например, требуется\), а затем связать их с объектом `CSocketFile` в конструкторе `CArchive`.  При поступлении завершены, destroy `CArchive`, `CSocketFile` и объекты `CSocket`.  Тип данных `SOCKET` описана в статье [Windows sockets: фон](../../mfc/windows-sockets-background.md).  
  
 При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, когда `CSocket::Receive` вводит цикл \( `PumpMessages(FD_READ)`\) ожидания количество запрошенных байтов.  Это происходит потому, что Windows sockets допускают только один вызов recv в уведомление FD\_READ, но `CSocketFile` и `CSocket` допускают несколько вызовов recv в FD\_READ.  Если получено FD\_READ при отсутствии данных для чтения, приложение висит.  Если вы не получаете другое FD\_READ, то выполнение приложения остановится взаимодействия через гнездом.  
  
 Можно разрешить эту проблему следующим образом.  В методе `OnReceive` класса сокета, вызов `CAsyncSocket::IOCtl(FIONREAD, ...)` до вызова метода `Serialize` класса сообщений, когда требуемые данные, считываемых из одного сокета превышает размер пакета TCP \(MTU носитель сети, обычно не менее 1096 байт\).  Если размер доступные данные меньше требуется подождите все данные, которые требуется получить, и только затем начать операцию чтения.  
  
 В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получения.  Требуется объявить его в другом месте в коде.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/CPP/csocket-class_1.cpp)]  
  
> [!NOTE]
>  При использовании сокетов MFC в статической вторичных потоков в связанном приложении MFC, необходимо вызвать `AfxSocketInit` в каждом потоке, который использует сокета для инициализации библиотеки сокета.  По умолчанию `AfxSocketInit` вызываются только в основном потоке.  
  
 Дополнительные сведения см. в разделе [Windows sockets в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows sockets: Использование сокета с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows sockets: Как работают с архивами сокета](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows sockets: последовательность операций](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md), [Windows sockets: Пример сокетов использование файлов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)  
  
 `CSocket`  
  
## Требования  
 **заголовок:** afxsock.h  
  
## См. также  
 [CAsyncSocket Class](../Topic/CAsyncSocket%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../Topic/CAsyncSocket%20Class.md)   
 [CSocketFile Class](../Topic/CSocketFile%20Class.md)