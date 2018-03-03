---
title: "CAsyncSocket-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24ef9c6e39d72e756b95472daee46b7d39503943
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="casyncsocket-class"></a>CAsyncSocket-класс
Представляет Windows Socket — конечную точку обмена данными по сети.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Создает объект `CAsyncSocket`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|Принимает подключения через сокет.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Запросы уведомления о событии для сокета.|  
|[CAsyncSocket::Attach](#attach)|Прикрепляет дескриптор сокета `CAsyncSocket` объекта.|  
|[CAsyncSocket::Bind](#bind)|Связывает локальных адресов с сокетом.|  
|[CAsyncSocket::Close](#close)|Закрывает сокет.|  
|[CAsyncSocket::Connect](#connect)|Устанавливает подключение к сокету однорангового узла.|  
|[CAsyncSocket::Create](#create)|Создание сокета.|  
|[CAsyncSocket::Detach](#detach)|Отсоединяет дескриптор сокета из `CAsyncSocket` объекта.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Возвращает указатель на `CAsyncSocket` объект, заданный дескриптор сокета.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Возвращает состояние ошибки для последней операции, в котором произошел сбой.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Возвращает адрес сокета однорангового узла, к которому подключен сокета.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Возвращает адрес сокета однорангового узла, к которому сокет находится подключенного (маркеры адресов IPv6).|  
|[CAsyncSocket::GetSockName](#getsockname)|Возвращает локальное имя для сокета.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Возвращает локальное имя для сокета (маркеры адресов IPv6).|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Получает параметр сокета.|  
|[CAsyncSocket::IOCtl](#ioctl)|Управляет режимом сокета.|  
|[CAsyncSocket::Listen](#listen)|Устанавливает сокет для прослушивания входящих запросов на подключение.|  
|[CAsyncSocket::Receive](#receive)|Получает данные из сокета.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Получает датаграмму и сохраняет исходный адрес.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Получает датаграмму и сохраняет адрес источника (маркеры адресов IPv6).|  
|[CAsyncSocket::Send](#send)|Отправляет данные в подключенный сокет.|  
|[CAsyncSocket::SendTo](#sendto)|Отправляет данные в определенное место назначения.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Отправляет данные в определенное место назначения (маркеры адресов IPv6).|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Задает параметр сокета.|  
|[CAsyncSocket::ShutDown](#shutdown)|Отключает **отправки** и/или **Receive** вызывает для сокета.|  
|[CASyncSocket::Socket](#socket)|Выделяет дескриптор сокета.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Уведомляет прослушивающего сокета, он может принять ожидающих запросов на подключение, вызвав **Accept**.|  
|[CAsyncSocket::OnClose](#onclose)|Уведомляет закрыл сокет, подключенный сокет.|  
|[CAsyncSocket::OnConnect](#onconnect)|Уведомляет подключения сокета, попытки подключения выполнена, является ли успешно или с ошибкой.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Уведомляет принимающей сокета отсутствуют данные по каналу, предназначенные для чтения на сокет, обычно срочных сообщений.|  
|[CAsyncSocket::OnReceive](#onreceive)|Уведомляет прослушивающего сокета, что нет данных для полученного посредством обращения **Receive**.|  
|[CAsyncSocket::OnSend](#onsend)|Уведомляет сокета, что его можно отправить данные путем вызова **отправки**.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Присваивает новое значение для `CAsyncSocket` объекта.|  
|[CAsyncSocket::operator СОКЕТА](#operator_socket)|Этот оператор используется для получения **СОКЕТА** handle `CAsyncSocket` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Указывает **СОКЕТА** дескриптор, присоединенного к данному `CAsyncSocket` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CAsyncSocket` инкапсулирует Windows Socket функции API, предоставляя абстракцию объектно ориентированного для программистов, которые хотят использовать сокеты Windows в сочетании с MFC.  
  
 Этот класс основан на предположении, что вы понимаете сетевого взаимодействия. Вы несете ответственность за обработку блокировки различия порядка следования байтов и преобразования между Юникодом и многобайтовой набор строк (MBCS). Если требуется более удобный интерфейс, который управляет этих проблем см. класс [CSocket](../../mfc/reference/csocket-class.md).  
  
 Для использования `CAsyncSocket` , вызовите его конструктор затем вызвать [создать](#create) функцию, чтобы создать базовый дескриптор сокета (типа `SOCKET`), за исключением для сокетов, принятые на. Для вызова сокета сервера [прослушивания](#listen) функции-члена и для клиентского сокета вызова [Connect](#connect) функции-члена. Следует вызвать сокета сервера [Accept](#accept) функция при получении запроса на соединение. Использовать оставшиеся `CAsyncSocket` функции для выполнения обмена данными между сокетов. По завершении удаления `CAsyncSocket` объекта, если он был создан в куче; автоматически вызывает деструктор [закрыть](#close) функции. `SOCKET` Тип данных, описанное в статье [Windows Sockets: фон](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  При использовании сокетов второстепенных потоков в приложении MFC статически скомпонованной MFC, необходимо вызвать метод `AfxSocketInit` в каждый поток, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: использование класса CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) и связанные с ними статей. а также [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 Вызовите эту функцию-член для приема подключений на сокете.  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `rConnectedSocket`  
 Ссылка, определение новый сокет для подключения.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры, принимающая адрес подключения сокета, как записано в сети. Точный формат `lpSockAddr` аргумент определяется семейство адресов, установить при создании сокета. Если `lpSockAddr` и/или `lpSockAddrLen` равны **NULL**, то возвращаются сведения об удаленном адресе принятого сокета.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах. `lpSockAddrLen` Является параметром значение результата: изначально, она должна содержать расстояние, на который указывает `lpSockAddr`; при возврате, она будет содержать фактическую длину (в байтах) адрес, возвращенный.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINPROGRESS** блокирующий вызов Windows Sockets идет.  
  
- **WSAEINVAL** `Listen` не вызванного перед принять.  
  
- **WSAEMFILE** очередь пуста при вхождении в для приема и дескрипторы не доступны.  
  
- `WSAENOBUFS`Буфер не доступен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP** сокета, на которую указывает ссылка не является типом, поддерживающего службу, ориентированного на подключение.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и присутствуют подключения не принимаются.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура извлекает первое подключение в очереди ожидающих подключений, создает новый сокет с теми же свойствами, как этот сокет и прикрепляет его к `rConnectedSocket`. Если нет ожидающих подключений в очереди, **Accept** возвращает ноль и `GetLastError` возвращает сообщение об ошибке. Принятого сокета ( *rConnectedSocket)* не может использоваться для нескольких подключений. Исходный сокета остается открытой и прослушивания.  
  
 Аргумент `lpSockAddr` имеет параметр результата, который заполняется с использованием адреса подключения сокета, как известно, уровня коммуникаций. **Принять** используется с типами сокета на основе подключения, например **SOCK_STREAM**.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 Вызовите эту функцию-член для запроса уведомления о событии для сокета.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lEvent`  
 Битовая маска, который указывает сочетание сетевые события, в которых нужно получить приложение.  
  
- **FD_READ** хотите получать уведомления о готовности для чтения.  
  
- **FD_WRITE** хотите получать уведомления, когда данные доступны для чтения.  
  
- **FD_OOB** хотите получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** хотите получать уведомления о входящих подключений.  
  
- **FD_CONNECT** хотите получать уведомления о результаты соединения.  
  
- **FD_CLOSE** хотите получать уведомления, когда сокет был закрыт одноранговым узлом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** указывает, что один из указанных параметров недопустим.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для указания того, какие функции MFC обратного вызова уведомления будет вызываться для сокета. `AsyncSelect`автоматически устанавливает этот сокет неблокирующий режим. Дополнительные сведения см. в статье [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 Вызовите эту функцию-член для присоединения `hSocket` дескриптор `CAsyncSocket` объекта.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
 `lEvent`  
 Битовая маска, который указывает сочетание сетевые события, в которых нужно получить приложение.  
  
- **FD_READ** хотите получать уведомления о готовности для чтения.  
  
- **FD_WRITE** хотите получать уведомления, когда данные доступны для чтения.  
  
- **FD_OOB** хотите получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** хотите получать уведомления о входящих подключений.  
  
- **FD_CONNECT** хотите получать уведомления о результаты соединения.  
  
- **FD_CLOSE** хотите получать уведомления, когда сокет был закрыт одноранговым узлом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 **СОКЕТА** дескриптор хранится в объекте [m_hSocket](#m_hsocket) члена данных.  
  
##  <a name="bind"></a>CAsyncSocket::Bind  
 Вызовите эту функцию-член для присоединения к ним локальный адрес сокета.  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketPort`  
 Порт, идентифицирующая приложение сокета.  
  
 `lpszSocketAddress`  
 Сетевой адрес, пунктирная число, например «128.56.22.8». Передача **NULL** строку для этого параметра указывает **CAsyncSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес для назначения этим сокетом.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** указанный адрес уже используется. (См. **SO_REUSEADDR** параметра в разделе сокета [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** `nSockAddrLen` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINPROGRESS** блокирующий вызов Windows Sockets идет.  
  
- **WSAEAFNOSUPPORT** заданного семейства адресов не поддерживается для этого порта.  
  
- **WSAEINVAL** сокет уже связан с адресом.  
  
- `WSAENOBUFS`Недостаточно доступных буферов, слишком много подключений.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура используется в несвязанной датаграмм или сокета потока перед последующих **Connect** или `Listen` вызовов. Прежде чем он может принимать запросы на подключение, прослушивающего сокета сервера необходимо выберите номер порта и сделать ее известных Windows Sockets, вызвав **привязки**. **Привязать** устанавливает локальную ассоциацию (номер адреса и порта узла) сокета, назначив гнездо неименованные локальное имя.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 Создает объект пустым сокета.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, необходимо вызвать его **создать** функции-члена для создания **СОКЕТА** структуры данных и привязать ее адрес. (На стороне сервера Windows Sockets связи, когда прослушивающего сокета создает сокет для использования в **Accept** вызова не вызывается **создать** для этого сокета.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 Закрывает сокет.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция освобождает дескриптор сокета, чтобы дополнительные ссылки на него завершится с ошибкой **WSAENOTSOCK**. Если это последняя ссылка на основном сокете, связанной с ними информации об именах и очереди данных удаляются. Вызывает деструктор объекта сокета **закрыть** для вас.  
  
 Для `CAsyncSocket`, но не для `CSocket`, семантика **закрыть** затронутые параметры сокетов **SO_LINGER** и **SO_DONTLINGER**. Дополнительные сведения см. в разделе функции-члена `GetSockOpt`.  
  
##  <a name="connect"></a>CAsyncSocket::Connect  
 Вызовите эту функцию-член для установления соединения несвязанной поток или сокета датаграмм.  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszHostAddress`  
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная число, например «128.56.22.8».  
  
 `nHostPort`  
 Порт, идентифицирующая приложение сокета.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес подключенного сокета.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Если это указывает код ошибки **WSAEWOULDBLOCK**и ваше приложение использует overridable обратные вызовы, ваше приложение получит `OnConnect` сообщение по завершении операции подключения. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** указанный адрес уже используется.  
  
- **WSAEINPROGRESS** блокирующий вызов Windows Sockets идет.  
  
- **WSAEADDRNOTAVAIL** указанный адрес доступен не на локальном компьютере.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAECONNREFUSED** попытка подключения была отклонена.  
  
- **WSAEDESTADDRREQ** требуется адрес назначения.  
  
- **WSAEFAULT** `nSockAddrLen` Неверный аргумент.  
  
- **WSAEINVAL** адрес недопустимый узел.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных нет дополнительных дескрипторов файлов.  
  
- **WSAENETUNREACH** сети не могут использоваться для этого узла в данный момент.  
  
- `WSAENOBUFS`Буфер не доступен. Сокет не подключен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAETIMEDOUT** попытки подключения истекло без установления подключения.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый соединение не может быть немедленно завершена.  
  
### <a name="remarks"></a>Примечания  
 Если отменяется привязка сокета, уникальные значения присваиваются локальную ассоциацию системой и сокета помечается как привязать. Обратите внимание, что если поле адрес структуры имя представляет все нули **Connect** будет возвращено нулевое значение. Чтобы получить расширенные сведения об ошибке, вызовите `GetLastError` функции-члена.  
  
 Для сокетов потока (тип **SOCK_STREAM**), активное соединение инициируется внешнего узла. По завершении вызова сокета сокета готов для отправки и получения данных.  
  
 Для сокета датаграмм (тип **SOCK_DGRAM**), задать назначение по умолчанию, который будет использоваться на последующих **отправки** и **Receive** вызовов.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 Вызовите **создать** после создания объекта сокета Создание сокетов Windows и присоединение его функции-члена.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketPort`  
 Известный порт для использования с сокета, или 0, если требуется Windows Sockets порт.  
  
 `nSocketType`  
 **SOCK_STREAM** или **SOCK_DGRAM**.  
  
 `lEvent`  
 Битовая маска, который указывает сочетание сетевые события, в которых нужно получить приложение.  
  
- **FD_READ** хотите получать уведомления о готовности для чтения.  
  
- **FD_WRITE** хотите получать уведомления о готовности для записи.  
  
- **FD_OOB** хотите получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** хотите получать уведомления о входящих подключений.  
  
- **FD_CONNECT** хотите получать уведомления о завершенных соединения.  
  
- **FD_CLOSE** хотите получать уведомления о закрытием сокета.  
  
 *lpszSockAddress*  
 Указатель на строку, содержащую сетевой адрес подключенного сокета пунктирная число, например «128.56.22.8». Передача **NULL** строку для этого параметра указывает **CAsyncSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEAFNOSUPPORT** заданного семейства адресов не поддерживается.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEMFILE** доступных нет дополнительных дескрипторов файлов.  
  
- `WSAENOBUFS`Буфер не доступен. Не удается создать сокет.  
  
- **WSAEPROTONOSUPPORT** указанный порт не поддерживается.  
  
- **WSAEPROTOTYPE** указанный порт имеет неверный тип для этого сокета.  
  
- **WSAESOCKTNOSUPPORT** указанный тип сокета не поддерживается в данном семействе адресов.  
  
### <a name="remarks"></a>Примечания  
 **Создание** вызовы [сокета](#socket) и в случае успеха, он вызывает [привязки](#bind) привязке сокета по указанному адресу. Поддерживаются следующие типы сокета:  
  
- **SOCK_STREAM** виртуализации, обеспечивает надежный, дуплексная подключений байтовые потоки. Использует протокол управления передачей (TCP) для семейства адресов Интернета.  
  
- **SOCK_DGRAM** поддерживает датаграммы — пакеты без установления соединения, ненадежные фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета.  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Имейте в виду, что если этот объект сокета идет области видимости, соединение закрывается. Не вызывайте **создать** для этого нового объекта сокета.  
  
> [!IMPORTANT]
> **Создание** — **не** потокобезопасным.  При вызове он в многопоточной среде которых он может быть применено одновременно различными потоками, не забудьте защитить каждый вызов с мьютекс или другие блокировки синхронизации.  
  
 Дополнительные сведения о сокеты потока и датаграммы см. в статьях [Windows Sockets: фон](../../mfc/windows-sockets-background.md) и [Windows Sockets: порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md) и [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 Вызовите эту функцию-член для отсоединения **СОКЕТА** обработки в `m_hSocket` элемент данных из `CAsyncSocket` и задайте `m_hSocket` для **NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 Возвращает указатель на `CAsyncSocket` объект.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CAsyncSocket` объекта, или **NULL** при наличии не `CAsyncSocket` объект присоединен к `hSocket`.  
  
### <a name="remarks"></a>Примечания  
 Для заданного **СОКЕТА** обработки, если `CAsyncSocket` объект не присоединен к дескриптору, функция-член возвращает **NULL**.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 Вызовите эту функцию-член для получения состояния ошибки для последней операции, в котором произошел сбой.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, указывающее код ошибки для последней стандартных Windows Sockets API, выполняется этим потоком.  
  
### <a name="remarks"></a>Примечания  
 Если определенная функция-член указывает, что произошла ошибка, `GetLastError` должен вызываться для извлечения соответствующий код ошибки. В разделе описаний функций отдельных членов список кодов ошибок применимо.  
  
 Дополнительные сведения о кодах ошибок см. в разделе [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="getpeername"></a>CAsyncSocket::GetPeerName  
 Вызовите эту функцию-член для получения адреса сокета однорангового узла, к которому подключен этот сокет.  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Параметры  
 `rPeerAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rPeerPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, которая получает имя сокета однорангового узла.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах. При возвращении `lpSockAddrLen` аргумент содержит фактический размер `lpSockAddr` возвращается в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не может быть достаточно большим.  
  
- **WSAEINPROGRESS** блокирующий вызов Windows Sockets идет.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 Вызовите эту функцию-член для получения адреса сокета однорангового узла, к которому этот сокет находится подключенного (маркеры адресов IPv6).  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Параметры  
 `rPeerAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rPeerPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не может быть достаточно большим.  
  
- **WSAEINPROGRESS** блокирующий вызов Windows Sockets идет.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является таким же, как [CAsyncSocket::GetPeerName](#getpeername) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
##  <a name="getsockname"></a>CAsyncSocket::GetSockName  
 Вызовите эту функцию-член для получения локального имени для сокета.  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Параметры  
 `rSocketAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rSocketPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры, принимающая адрес сокета.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не может быть достаточно большим.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEINVAL** сокета не привязано к адрес с **привязки**.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов особенно полезна при **Connect** вызова без это **привязки** , этот вызов предоставляет единственное средство, с помощью которого можно определить локальную ассоциацию, который был задан система.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 Вызовите эту функцию-член для получения локального имени для сокета (маркеры адресов IPv6).  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Параметры  
 `rSocketAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rSocketPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не может быть достаточно большим.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEINVAL** сокета не привязано к адрес с **привязки**.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов является таким же, как [CAsyncSocket::GetSockName](#getsockname) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 Этот вызов особенно полезна при **Connect** вызова без это **привязки** , этот вызов предоставляет единственное средство, с помощью которого можно определить локальную ассоциацию, который был задан система.  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 Вызовите эту функцию-член для извлечения параметр сокета.  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Параметры  
 `nOptionName`  
 Параметр сокета, для которого требуется извлечь значение.  
  
 `lpOptionValue`  
 Указатель на буфер, в котором запрошенный параметр значение должно быть возвращено. Значение, связанное с выбранного параметра возвращается в буфере `lpOptionValue`. Целое число, на который указывает `lpOptionLen` первоначально должен содержать размера этого буфера в байтах; и при возврате, он будет присвоено размер возвращаемого значения. Для **SO_LINGER**, это будет размер `LINGER` структуры; для всех параметров имеет размер **BOOL** или `int`, в зависимости от параметра. См. список параметров и их размер в разделе "Примечания".  
  
 `lpOptionLen`  
 Указатель на размер `lpOptionValue` буфера в байтах.  
  
 `nLevel`  
 Уровень, с которой определен параметр; только поддерживаемые уровни **SOL_SOCKET** и **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Если параметр не был установлен с `SetSockOpt`, затем `GetSockOpt` возвращает значение по умолчанию для параметра. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpOptionLen` недопустимый аргумент.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOPROTOOPT** параметр неизвестен или не поддерживается. В частности **SO_BROADCAST** не поддерживается на сокетах типа **SOCK_STREAM**, пока **SO_ACCEPTCONN**, **SO_DONTLINGER**,  **SO_KEEPALIVE**, **SO_LINGER**, и **SO_OOBINLINE** не поддерживается на сокетах типа **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 `GetSockOpt`Возвращает текущее значение для параметра сокета, связанные с сокетом любого типа, в любом состоянии и сохраняет результат в `lpOptionValue`. Параметры влияют на операции сокета, например маршрутизации пакетов, передача данных по каналу и т. д.  
  
 Следующие параметры поддерживаются для `GetSockOpt`. Тип указывает тип данных, подразумевающие `lpOptionValue`. **TCP_NODELAY** параметр использует уровень **IPPROTO_TCP**; все прочие параметры использовать уровень **SOL_SOCKET**.  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Сокет прослушивает.|  
|**SO_BROADCAST**|**BOOL**|Сокет, настроенной для передачи широковещательных сообщений.|  
|**SO_DEBUG**|**BOOL**|Включена отладка.|  
|**SO_DONTLINGER**|**BOOL**|Если значение равно true, **SO_LINGER** параметр будет отключен.|  
|**SO_DONTROUTE**|**BOOL**|Маршрутизация отключена.|  
|**SO_ERROR**|`int`|Получить состояние ошибки и очистить.|  
|**SO_KEEPALIVE**|**BOOL**|Активность отправляются.|  
|**SO_LINGER**|**Структура ОЖИДАНИЯ**|Возвращает текущие параметры ожидания.|  
|**SO_OOBINLINE**|**BOOL**|Получения данных по каналу в обычном потоке данных.|  
|**SO_RCVBUF**|`int`|Получает размер буфера.|  
|**SO_REUSEADDR**|**BOOL**|Сокет можно привязать к адресу, который уже используется.|  
|**SO_SNDBUF**|`int`|Размер буфера для отправляет.|  
|**SO_TYPE**|`int`|Тип сокета (например, **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|Отключить алгоритм Nagle для отправки объединенных пакетов.|  
  
 Параметры распространения программного обеспечения Беркли (BSD) не поддерживается для `GetSockOpt` являются:  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Получите метку низкого уровня.|  
|**SO_RCVTIMEO**|`int`|Время ожидания получения.|  
|**SO_SNDLOWAT**|`int`|Отправьте метку низкого уровня.|  
|**SO_SNDTIMEO**|`int`|Отправьте время ожидания.|  
|**IP_OPTIONS**||Получение параметров в IP-заголовке.|  
|**TCP_MAXSEG**|`int`|Получите максимальный размер TCP.|  
  
 Вызов `GetSockOpt` неподдерживаемый параметр приведет к код ошибки **WSAENOPROTOOPT** , возвращенных `GetLastError`.  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 Вызовите эту функцию-член для управления режимом сокета.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>Параметры  
 `lCommand`  
 Команда для выполнения на сокете.  
  
 `lpArgument`  
 Указатель на параметр для `lCommand`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** `lCommand` не является допустимой команды, или `lpArgument` не является допустимым параметром для `lCommand`, или команда не применим к типу сокета указано.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура может использоваться любой сокете в любом состоянии. Он используется для получения или получить работы параметров, связанных с сокета, независимо от подсистемы протокола и связи. Поддерживаются следующие команды:  
  
- **FIONBIO** включения или отключения режима неблокируемый на сокете. `lpArgument` Указывает на параметр `DWORD`, являющийся ненулевым, если неблокирующий режим включения и нуль, если это требуется отключить. Если `AsyncSelect` была выполнена на сокете, то любая попытка вызова **IOCtl** присвоить сокета обратно в режим блокировки, будут завершаться **WSAEINVAL**. Значение сокета блокирующем режиме и с предотвращением **WSAEINVAL** ошибку, необходимо отключить приложение `AsyncSelect` путем вызова `AsyncSelect` с `lEvent` параметра равно 0, затем вызовите **IOCtl** .  
  
- **FIONREAD** определить максимальное число байтов, которые могут быть прочитаны с одним **Receive** вызовите из этого сокета. `lpArgument` Указывает на параметр `DWORD` в котором **IOCtl** сохраняет результат. Если этот сокет имеет тип **SOCK_STREAM**, **FIONREAD** возвращает общий объем данных, который может читать в одном **Receive**; это обычно то же самое, что общий объем данные в очередь на сокете. Если этот сокет имеет тип **SOCK_DGRAM**, **FIONREAD** возвращает размер первого датаграмм в очереди на сокете.  
  
- **SIOCATMARK** проверить чтения всех данных по каналу. Это относится только к сокету типа **SOCK_STREAM** которого был настроен для приема канала всех данных по каналу ( **SO_OOBINLINE**). Если нет данных по каналу для чтения, операция возвращает ненулевое значение. В противном случае возвращает 0, а теперь **Receive** или `ReceiveFrom` блокировкой сокет будет получают некоторые или все данные, предшествующей «метки», приложение должно использовать **SIOCATMARK** операции Определите, остается ли все данные. Если обычные данные, предшествующей «срочные» (внешнее) данных, он будут получены в порядке. (Обратите внимание, что **Receive** или `ReceiveFrom` будет никогда не смешивайте по каналу и обычных данных в одном вызове.) `lpArgument` Указывает на параметр `DWORD` в котором **IOCtl** сохраняет результат.  
  
 Эта функция представляет собой подмножество **ioctl()** в сокетов Беркли. В частности, нет ни одной команды, что эквивалентно **FIOASYNC**, пока **SIOCATMARK** команда только на уровне сокетов, который поддерживается.  
  
##  <a name="listen"></a>CAsyncSocket::Listen  
 Вызовите эту функцию-член для прослушивания входящих запросов на подключение.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Параметры  
 *nConnectionBacklog*  
 Максимальная длина, до которого может вырасти очередь ожидающих подключений. Допустимый диапазон — от 1 до 5.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** попытка прослушивания по адресу используется.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEINVAL** сокета не были связаны со **привязки** или уже подключен.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных нет дополнительных дескрипторов файлов.  
  
- `WSAENOBUFS`Буфер не доступен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP** сокета, на которую указывает ссылка, не относится к тип, поддерживающий `Listen` операции.  
  
### <a name="remarks"></a>Примечания  
 Для приема подключений, сокет сначала создается с **создать**, очередь для входящих подключений, указанном с помощью `Listen`, а затем принимаются подключения **Accept**. `Listen`применяется только к сокетов, которые поддерживают подключения, то есть биты типа **SOCK_STREAM**. Этот сокет переводится в режим «пассивный», где подтверждения и в очередь ожидающих принятия процессом входящие подключения.  
  
 Эта функция обычно используется серверов (или любого приложения, которое хочет принимать подключения), может иметь более одного запроса подключения одновременно: при получении запроса подключения с очередь переполнена, клиент появится сообщение об ошибке с указанием  **WSAECONNREFUSED**.  
  
 `Listen`предпринимается попытка продолжают функционировать разумно, если нет доступных портов (дескрипторы). Он будет принимать подключения до освобождения очереди. Если порты становятся доступными, последующий вызов `Listen` или **Accept** по возможности повторного заполнения очереди для текущего или последнего «невыполненную работу» и возобновить прослушивание входящих подключений.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 Содержит **СОКЕТА** дескриптор сокета, инкапсулированный этим `CAsyncSocket` объекта.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 Вызывается платформой для уведомления прослушивающего сокета, он может принять ожидающих запросов на подключение, вызвав [Accept](#accept) функции-члена.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяется к `OnAccept` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 Вызывается платформой для уведомления этот сокет, что закрывается соединенный сокет, его процесс.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяются к `OnClose` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAECONNRESET** соединение было сброшено удаленной стороной.  
  
- **WSAECONNABORTED** подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 Вызывается платформой для уведомления этого при подключении к сокету его попытки подключения завершение, является ли успешно или с ошибкой.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяются к `OnConnect` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAEADDRINUSE** указанный адрес уже используется.  
  
- **WSAEADDRNOTAVAIL** указанный адрес доступен не на локальном компьютере.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAECONNREFUSED** попытка подключения была принудительно отклонена.  
  
- **WSAEDESTADDRREQ** требуется адрес назначения.  
  
- **WSAEFAULT** `lpSockAddrLen` Неверный аргумент.  
  
- **WSAEINVAL** сокет уже связан с адресом.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных нет дополнительных дескрипторов файлов.  
  
- **WSAENETUNREACH** сети не могут использоваться для этого узла в данный момент.  
  
- `WSAENOBUFS`Буфер не доступен. Сокет не подключен.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** дескриптора — это файл, не сокета.  
  
- **WSAETIMEDOUT** подключения истекло время ожидания без установления подключения.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` функция уведомления никогда не вызывается. Для соединений, можно просто вызвать **Connect**, возвращающий при завершении соединения (успешно или с ошибкой). Обработки уведомления соединения является реализации MFC.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 Вызывается платформой для получения сокета с сокета отправки данных по каналу для отправки уведомления.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяются к `OnOutOfBandData` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 По каналу данных является логически независимым канал, связанный с каждой парой подключенных сокеты типа **SOCK_STREAM**. Канал обычно используется для отправки срочные данные.  
  
 MFC поддерживает данные по каналу, но пользователи класса `CAsyncSocket` , не рекомендуется использовать их. Простым способом является создавать второй сокет для передачи таких данных. Дополнительные сведения о данных по каналу см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 Вызывается платформой для уведомления этот сокет это данные в буфер, который можно получить, вызвав **Receive** функции-члена.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяются к `OnReceive` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 Вызывается платформой для уведомления сокета, что теперь отправки данных путем вызова **отправки** функции-члена.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самые последние ошибки на сокете. Следующие коды ошибок применяются к `OnSend` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 Присваивает новое значение для `CAsyncSocket` объекта.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Ссылка на существующий `CAsyncSocket` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для копирования существующих `CAsyncSocket` объекта в другой `CAsyncSocket` объекта.  
  
##  <a name="operator_socket"></a>CAsyncSocket::operator СОКЕТА  
 Этот оператор используется для получения **СОКЕТА** handle `CAsyncSocket` объекта.  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения дескриптор **СОКЕТА** объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.  
  
##  <a name="receive"></a>CAsyncSocket::Receive  
 Вызовите эту функцию-член для получения данных из сокета.  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер для входных данных.  
  
 `nBufLen`  
 Длина `lpBuf` в байтах.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** считывать входные данные. Данные копируются в буфер, но не удаляется из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, **Receive** возвращает число полученных байт. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать **Receive** на сокете после `ShutDown` был вызван с `nHow` в значение 0 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и **Receive** операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком большой для помещения в указанный буфер и было усечено.  
  
- **WSAEINVAL** сокета не были связаны со **привязки**.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для подключенного поток или сокеты датаграмм и используется для считывания входящих данных.  
  
 Для сокетов типа **SOCK_STREAM**, как возвращается большой объем информации, как в настоящее время доступна до размер предоставленного буфера. Если сокета был настроен для приема канала данных по каналу (параметра сокета **SO_OOBINLINE**) и данных по каналу непрочитанные, будут возвращены данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или [OnOutOfBandData](#onoutofbanddata) для определения, остается ли все данные более-резервному для чтения.  
  
 Для сокеты датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размер предоставленного буфера. Если датаграмма превышает размер буфера, предоставленного, буфер заполняется в первой части датаграмма, избыточные данные будут потеряны, и **Receive** возвращает значение **SOCKET_ERROR** с кодом ошибки присвоено значение **WSAEMSGSIZE**. Если входящие данные недоступны на сокет, значение **SOCKET_ERROR** возвращается с кодом ошибки **WSAEWOULDBLOCK**. [OnReceive](#onreceive) функция обратного вызова можно использовать для определения того, при поступлении дополнительных данных.  
  
 Если тип сокета **SOCK_STREAM** и удаленная сторона завершил работу соединения корректно, **Receive** будет немедленно завершена с 0 байт, полученных. Если сброс подключения **Receive** завершится с ошибкой **WSAECONNRESET**.  
  
 **Получать** должен вызываться только один раз для каждого времени [CAsyncSocket::OnReceive](#onreceive) вызывается.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 Вызовите эту функцию-член для получения датаграммы и сохранения исходного адреса в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в `rSocketAddress`.  
  
```  
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);

 
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер для входных данных.  
  
 `nBufLen`  
 Длина `lpBuf` в байтах.  
  
 `rSocketAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rSocketPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структура, которая содержит адрес источника после возврата.  
  
 `lpSockAddrLen`  
 Указатель на длину исходного адреса в `lpSockAddr` в байтах.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** считывать входные данные. Данные копируются в буфер, но не удаляется из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `ReceiveFrom` возвращает число полученных байт. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова `GetLastError`. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` недопустимый аргумент: `lpSockAddr` буфер слишком мал для размещения адреса узла.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEINVAL** сокета не были связаны со **привязки**.  
  
- **WSAENOTCONN** сокет не подключен ( **SOCK_STREAM** только).  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `ReceiveFrom` на сокете после `ShutDown` был вызван с `nHow` в значение 0 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и `ReceiveFrom` операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком большой для помещения в указанный буфер и было усечено.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для чтения входящих данных на сокет (возможно, подключенного) и записать адрес, с которого было отправлено данных.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Для сокетов типа **SOCK_STREAM**, как возвращается большой объем информации, как в настоящее время доступна до размер предоставленного буфера. Если сокета был настроен для приема канала данных по каналу (параметра сокета **SO_OOBINLINE**) и данных по каналу непрочитанные, будут возвращены данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или `OnOutOfBandData` для определения, остается ли все данные более-резервному для чтения. `lpSockAddr` И `lpSockAddrLen` параметры игнорируются для **SOCK_STREAM** сокетов.  
  
 Для сокеты датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размер предоставленного буфера. Если датаграмма превышает размер буфера, предоставленного, буфер заполняется первая часть сообщения, избыточные данные будут потеряны, и `ReceiveFrom` возвращает значение **SOCKET_ERROR** с кодом ошибки присвоено  **WSAEMSGSIZE**.  
  
 Если `lpSockAddr` отлично от нуля, и имеет тип сокета **SOCK_DGRAM**, сетевой адрес сокета, который отправил данные копируются в соответствующий [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на который указывает `lpSockAddrLen` изменяется при возвращении для указания размера фактические адреса, хранящиеся в ней и инициализируется до размера этой структуры. Если входящие данные недоступны на сокет, `ReceiveFrom` вызов ожидает поступления, если сокет не неблокируемый. В этом случае значение **SOCKET_ERROR** возвращается с кодом ошибки **WSAEWOULDBLOCK**. `OnReceive` Обратного вызова можно использовать для определения того, при поступлении дополнительных данных.  
  
 Если тип сокета **SOCK_STREAM** и удаленная сторона завершил работу соединения корректно, `ReceiveFrom` будет немедленно завершена с 0 байт, полученных.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 Вызовите эту функцию-член для получения датаграммы и сохранения исходного адреса в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в `rSocketAddress` (дескрипторы адресов IPv6).  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер для входных данных.  
  
 `nBufLen`  
 Длина `lpBuf` в байтах.  
  
 `rSocketAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rSocketPort`  
 Ссылка на **UINT** , в которых хранятся порт.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** считывать входные данные. Данные копируются в буфер, но не удаляется из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `ReceiveFromEx` возвращает число полученных байт. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова `GetLastError`. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` недопустимый аргумент: `lpSockAddr` буфер слишком мал для размещения адреса узла.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEINVAL** сокета не были связаны со **привязки**.  
  
- **WSAENOTCONN** сокет не подключен ( **SOCK_STREAM** только).  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `ReceiveFromEx` на сокете после `ShutDown` был вызван с `nHow` в значение 0 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и `ReceiveFromEx` операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком большой для помещения в указанный буфер и было усечено.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для чтения входящих данных на сокет (возможно, подключенного) и записать адрес, с которого было отправлено данных.  
  
 Эта функция является таким же, как [CAsyncSocket::ReceiveFrom](#receivefrom) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 Для сокетов типа **SOCK_STREAM**, как возвращается большой объем информации, как в настоящее время доступна до размер предоставленного буфера. Если сокета был настроен для приема канала данных по каналу (параметра сокета **SO_OOBINLINE**) и данных по каналу непрочитанные, будут возвращены данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или `OnOutOfBandData` для определения, остается ли все данные более-резервному для чтения. `lpSockAddr` И `lpSockAddrLen` параметры игнорируются для **SOCK_STREAM** сокетов.  
  
 Для сокеты датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размер предоставленного буфера. Если датаграмма превышает размер буфера, предоставленного, буфер заполняется первая часть сообщения, избыточные данные будут потеряны, и `ReceiveFromEx` возвращает значение **SOCKET_ERROR** с кодом ошибки присвоено  **WSAEMSGSIZE**.  
  
 Если `lpSockAddr` отлично от нуля, и имеет тип сокета **SOCK_DGRAM**, сетевой адрес сокета, который отправил данные копируются в соответствующий [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на который указывает `lpSockAddrLen` изменяется при возвращении для указания размера фактические адреса, хранящиеся в ней и инициализируется до размера этой структуры. Если входящие данные недоступны на сокет, `ReceiveFromEx` вызов ожидает поступления, если сокет не неблокируемый. В этом случае значение **SOCKET_ERROR** возвращается с кодом ошибки **WSAEWOULDBLOCK**. `OnReceive` Обратного вызова можно использовать для определения того, при поступлении дополнительных данных.  
  
 Если тип сокета **SOCK_STREAM** и удаленная сторона завершил работу соединения корректно, `ReceiveFromEx` будет немедленно завершена с 0 байт, полученных.  
  
##  <a name="send"></a>CAsyncSocket::Send  
 Вызовите эту функцию-член для отправки данных на подключенный сокет.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер, содержащий данные для передачи.  
  
 `nBufLen`  
 Длина данных в `lpBuf` в байтах.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **SOCK_STREAM** только).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, **отправки** возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEFAULT** `lpBuf` аргумент не является допустимой частью адресного пространства пользователя.  
  
- **WSAENETRESET** из-за удаления реализация Windows Sockets, его необходимо сбросить подключение.  
  
- `WSAENOBUFS`Реализация Windows Sockets о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать **отправки** на сокете после `ShutDown` был вызван с `nHow` в значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокета относится к типу **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAEINVAL** сокета не были связаны со **привязки**.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 **Отправить** используется для записи выходных данных на подключенный сокеты потока или датаграмм. Для сокеты датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, которая задана по **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры, возвращенный `AfxSocketInit`. Если данные слишком много атомарным образом проходить через базовый протокол ошибки **WSAEMSGSIZE** возвращаться через `GetLastError`, и данные не передаются.  
  
 Обратите внимание, что датаграммы сокета успешному **отправки** не указывает данные был успешно доставлен.  
  
 На `CAsyncSocket` объектов типа **SOCK_STREAM**, число записанных байтов может составлять от 1 до требуемой длине в зависимости от доступности буфера на узлах локальную и удаленную.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAsyncSocket::OnSend](#onsend).  
  
##  <a name="sendto"></a>CAsyncSocket::SendTo  
 Вызовите эту функцию-член для отправки данных в определенное место назначения.  
  
```  
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);

 
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер, содержащий данные для передачи.  
  
 `nBufLen`  
 Длина данных в `lpBuf` в байтах.  
  
 `nHostPort`  
 Порт, идентифицирующая приложение сокета.  
  
 `lpszHostAddress`  
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная число, например «128.56.22.8».  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **SOCK_STREAM** только).  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес сокета целевой.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `SendTo` возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEFAULT** `lpBuf` или `lpSockAddr` параметров не являются частью адресного пространства пользователя, или `lpSockAddr` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINVAL** указано недопустимое имя узла.  
  
- **WSAENETRESET** из-за удаления реализация Windows Sockets, его необходимо сбросить подключение.  
  
- `WSAENOBUFS`Реализация Windows Sockets о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен ( **SOCK_STREAM** только).  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `SendTo` на сокете после `ShutDown` был вызван с `nHow` в значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокета относится к типу **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
- **WSAEADDRNOTAVAIL** указанный адрес доступен не на локальном компьютере.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAEDESTADDRREQ** требуется адрес назначения.  
  
- **WSAENETUNREACH** сети не могут использоваться для этого узла в данный момент.  
  
### <a name="remarks"></a>Примечания  
 `SendTo`При использовании в сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокеты датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, которая задана по **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [ AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком много атомарным образом проходить через базовый протокол ошибки **WSAEMSGSIZE** возвращается, и данные не передаются.  
  
 Обратите внимание, что успешное завершение `SendTo` не указывает данные был успешно доставлен.  
  
 `SendTo`используется только на **SOCK_DGRAM** сокета, чтобы отправить датаграмму конкретных сокета определяется `lpSockAddr` параметра.  
  
 Для отправки на широковещательные (на **SOCK_DGRAM** только), в адрес `lpSockAddr` параметр должен быть создан с помощью специального IP-адреса **INADDR_BROADCAST** (определенных в заголовке сокеты Windows файл WINSOCK. H) вместе с номером нужный порт. Либо, если `lpszHostAddress` параметр **NULL**, сокета настроен для использования. Это обычно не задействуются широковещательных датаграммы к превышению размера, с которой может возникнуть фрагментация, это означает, что часть данных датаграмма (включая заголовки) не должна превышать 512 байт.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::SendToEx](#sendtoex).  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 Вызовите эту функцию-член для отправки данных в определенное место назначения (маркеры адресов IPv6).  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Буфер, содержащий данные для передачи.  
  
 `nBufLen`  
 Длина данных в `lpBuf` в байтах.  
  
 `nHostPort`  
 Порт, идентифицирующая приложение сокета.  
  
 `lpszHostAddress`  
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная число, например «128.56.22.8».  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметра. Последний создается путем объединения любой из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **SOCK_STREAM** только).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `SendToEx` возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получен путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEFAULT** `lpBuf` или `lpSockAddr` параметров не являются частью адресного пространства пользователя, или `lpSockAddr` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINVAL** указано недопустимое имя узла.  
  
- **WSAENETRESET** из-за удаления реализация Windows Sockets, его необходимо сбросить подключение.  
  
- `WSAENOBUFS`Реализация Windows Sockets о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен ( **SOCK_STREAM** только).  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `SendToEx` на сокете после `ShutDown` был вызван с `nHow` в значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокета помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокета относится к типу **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
- **WSAEADDRNOTAVAIL** указанный адрес доступен не на локальном компьютере.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAEDESTADDRREQ** требуется адрес назначения.  
  
- **WSAENETUNREACH** сети не могут использоваться для этого узла в данный момент.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является таким же, как [CAsyncSocket::SendTo](#sendto) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 `SendToEx`При использовании в сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокеты датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, которая задана по **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [ AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком много атомарным образом проходить через базовый протокол ошибки **WSAEMSGSIZE** возвращается, и данные не передаются.  
  
 Обратите внимание, что успешное завершение `SendToEx` не указывает данные был успешно доставлен.  
  
 `SendToEx`используется только на **SOCK_DGRAM** сокета, чтобы отправить датаграмму конкретных сокета определяется `lpSockAddr` параметра.  
  
 Для отправки на широковещательные (на **SOCK_DGRAM** только), в адрес `lpSockAddr` параметр должен быть создан с помощью специального IP-адреса **INADDR_BROADCAST** (определенных в заголовке сокеты Windows файл WINSOCK. H) вместе с номером нужный порт. Либо, если `lpszHostAddress` параметр **NULL**, сокета настроен для использования. Это обычно не задействуются широковещательных датаграммы к превышению размера, с которой может возникнуть фрагментация, это означает, что часть данных датаграмма (включая заголовки) не должна превышать 512 байт.  
  
##  <a name="setsockopt"></a>CAsyncSocket::SetSockOpt  
 Вызовите эту функцию-член для задания параметра сокета.  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Параметры  
 `nOptionName`  
 Параметр сокета, для которого требуется задать значение.  
  
 `lpOptionValue`  
 Указатель на буфер, в котором указано значение запрошенный параметр.  
  
 `nOptionLen`  
 Размер `lpOptionValue` буфера в байтах.  
  
 `nLevel`  
 Уровень, с которой определен параметр; только поддерживаемые уровни **SOL_SOCKET** и **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpOptionValue` не является допустимой частью адресного пространства процесса.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAEINVAL** `nLevel` является недопустимым, или данные в `lpOptionValue` является недопустимым.  
  
- **WSAENETRESET** ожидания соединения при **SO_KEEPALIVE** имеет значение.  
  
- **WSAENOPROTOOPT** параметр неизвестен или не поддерживается. В частности **SO_BROADCAST** не поддерживается на сокетах типа **SOCK_STREAM**, пока **SO_DONTLINGER**, **SO_KEEPALIVE**,  **SO_LINGER**, и **SO_OOBINLINE** не поддерживается на сокетах типа **SOCK_DGRAM**.  
  
- **WSAENOTCONN** соединение было сбросить при **SO_KEEPALIVE** имеет значение.  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 `SetSockOpt`Задает текущее значение для параметра сокета, связанные с сокетом любого типа, в любом состоянии. Несмотря на то, что параметры находятся на нескольких уровнях протокола, эта спецификация определяет только параметры, которые существуют на уровне верхнего края области «сокетов». Параметры влияют на операции сокета, например срочные данные, получен ли в обычном потоке данных, является ли широковещательных сообщений могут отправляться на сокет и т. д.  
  
 Существует два типа параметров сокета: включить или отключить компонент или поведение логическое параметров и параметров, требующих целочисленное значение или структуры. Для включения логического параметра, `lpOptionValue` указывает ненулевое значение, целое число со знаком. Чтобы отключить этот параметр `lpOptionValue` указывает на целое число, равное нулю. `nOptionLen`должно быть равно **sizeof(BOOL)** для логических параметров. Чтобы задать другие параметры `lpOptionValue` указывает на целое число или структура, содержащая нужное значение для параметра, и `nOptionLen` длина целого числа или структуры.  
  
 **SO_LINGER** действие, выполняемое при неотправленные данные в очереди на сокете элементов управления и **закрыть** функция, вызываемая для закрытия сокета.  
  
 По умолчанию не может быть привязан сокет (в разделе [привязки](#bind)) для локальных адресов, который уже используется. В некоторых случаях Однако он может возникнуть необходимость «повторно использовать «адрес таким образом. Поскольку каждое соединение однозначно идентифицируется сочетание локальных и удаленных адресов, то проблем не существует с входящим два сокетов, которые привязаны к один и тот же локальный адрес, при условии, что удаленного адреса отличаются.  
  
 Для информирования реализация Windows Sockets, **привязки** вызов на сокет не должны быть запрещены, так как нужный адрес уже используется другой сокета, приложение должно задать **SO_REUSEADDR**параметра для сокета перед выдачей сокета **привязки** вызова. Обратите внимание, что параметр интерпретируется только во время **привязки** вызова: он необязателен таким образом (но опасное) для задания параметра на сокете, которой не должен быть привязан к существующего адреса и установка или Сброс параметров после **Привязки** вызов имеет не влияет на это или какому сокету.  
  
 Приложение может запросить, что реализация Windows Sockets позволяют использовать «keep-alive» пакетов в соединениях протокола управления передачей (TCP), включив **SO_KEEPALIVE** параметра сокета. Реализация Windows Sockets не обязательно должна поддерживать использование активность: в этом случае семантику связаны с конкретной реализацией, но должны соответствовать RFC 1122 раздел 4.2.3.6: «требования к узлам Интернета — уровни взаимодействия.» При разрыве соединения в результате «активность» код ошибки **WSAENETRESET** возвращается сокете, на какие вызовы выполняется и все последующие вызовы завершатся ошибкой с **WSAENOTCONN**.  
  
 **TCP_NODELAY** параметр отключить алгоритм Nagle. Алгоритм Nagle используется для уменьшения количества небольших пакетов, отправленных в узле буферизации неподтвержденные отправки данных до полного размера пакета могут быть отправлены. Однако для некоторых приложений этот алгоритм может привести к снижению производительности, и **TCP_NODELAY** можно использовать для отключения этой функции. Разработчикам приложений не следует задавать **TCP_NODELAY** Если влияние этого хорошо понятны и нужный, так как параметр **TCP_NODELAY** может иметь существенное отрицательное влияние на производительность сети . **TCP_NODELAY** является единственным поддерживается параметр сокета, который использует уровень **IPPROTO_TCP**; все прочие параметры использовать уровень **SOL_SOCKET**.  
  
 Некоторые реализации источника питания Windows Sockets выводить отладочную информацию, если **SO_DEBUG** параметра, задаваемые приложением.  
  
 Следующие параметры поддерживаются для `SetSockOpt`. Тип указывает тип данных, подразумевающие `lpOptionValue`.  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Разрешить передачи широковещательных сообщений через сокет.|  
|**SO_DEBUG**|**BOOL**|Записать отладочную информацию.|  
|**SO_DONTLINGER**|**BOOL**|Не блокируют **закрыть** ожидание неотправленные данные для отправки. Установка этого параметра эквивалентно заданию для **SO_LINGER** с **l_onoff** равен нулю.|  
|**SO_DONTROUTE**|**BOOL**|Не направлять: send непосредственно к интерфейсу.|  
|**SO_KEEPALIVE**|**BOOL**|Отправьте активность.|  
|**SO_LINGER**|**Структура ОЖИДАНИЯ**|Задержка при **закрыть** Если неотправленные данные отсутствуют.|  
|**SO_OOBINLINE**|**BOOL**|Получение данных по каналу в обычном потоке данных.|  
|**SO_RCVBUF**|`int`|Укажите размер буфера для получения.|  
|**SO_REUSEADDR**|**BOOL**|Разрешить сокета ограничение на адрес, который уже используется. (См. [привязки](#bind).)|  
|**SO_SNDBUF**|`int`|Укажите размер буфера отправки.|  
|**TCP_NODELAY**|**BOOL**|Отключить алгоритм Nagle для отправки объединенных пакетов.|  
  
 Параметры распространения программного обеспечения Беркли (BSD) не поддерживается для `SetSockOpt` являются:  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Сокет прослушивает|  
|**SO_ERROR**|`int`|Получить состояние ошибки и выполнить очистку.|  
|**SO_RCVLOWAT**|`int`|Получите метку низкого уровня.|  
|**SO_RCVTIMEO**|`int`|Истекло время ожидания|  
|**SO_SNDLOWAT**|`int`|Отправьте метку низкого уровня.|  
|**SO_SNDTIMEO**|`int`|Отправьте время ожидания.|  
|**SO_TYPE**|`int`|Тип сокета.|  
|**IP_OPTIONS**||Задайте параметры поля в IP-заголовке.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 Получает вызов, чтобы отключить эту функцию-член отправляет, или оба через сокет.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Параметры  
 `nHow`  
 Флаг, который описывает, какие операции не разрешается, с помощью следующих значений:  
  
- **Получает = 0**  
  
- **отправляет = 1**  
  
- **как = 2**  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешной [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** `nHow` является недопустимым.  
  
- **WSAEINPROGRESS** операцию блокировки сокетов Windows выполняется в данный момент.  
  
- **WSAENOTCONN** сокет не подключен ( **SOCK_STREAM** только).  
  
- **WSAENOTSOCK** не дескриптор сокета.  
  
### <a name="remarks"></a>Примечания  
 `ShutDown`используется для всех типов сокетов для отключения приема и передачи. Если `nHow` равно 0, то последующие получил на сокет будет запрещена. Не действует на более низкие уровни протокола.  
  
 Окно TCP для протокола управления передачей (TCP), не изменяется и входящие данные будут приняты (но не подтвержденного), пока не будет исчерпан окна. Для протокола UDP (User Datagram), принимаются и в очередь входящих датаграмм. В любом случае будет создаваться ошибки ICMP-пакет. Если `nHow` имеет значение 1, последующие отправляет запрещены. Для сокетов TCP будет отправлено FIN. Параметр `nHow` 2 отключает обоих передачу и прием, как описано выше.  
  
 Обратите внимание, что `ShutDown` не закрыть сокет и ресурсами, сокета не будут освобождены до **закрыть** вызывается. Приложения, не следует полагаться на возможность повторного использования сокета, после завершения работы. В частности, реализация Windows Sockets не требуется для поддержки использования **Connect** таких сокет.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="socket"></a>CASyncSocket::Socket  
 Выделяет дескриптор сокета.  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketType`  
 Указывает `SOCK_STREAM` или `SOCK_DGRAM`.  
  
 `lEvent`  
 Битовая маска, определяющая сочетание сетевые события, в которых нужно получить приложение.  
  
- `FD_READ`: Требуется получать уведомления о готовности для чтения.  
  
- `FD_WRITE`: Требуется получать уведомления о готовности для записи.  
  
- `FD_OOB`: Требуется получать уведомления о получении данных по каналу.  
  
- `FD_ACCEPT`: Требуется получать уведомления о входящих подключений.  
  
- `FD_CONNECT`: Требуется получать уведомления о завершенных соединения.  
  
- `FD_CLOSE`: Требуется получать уведомления о закрытием сокета.  
  
 `nProtocolType`  
 Протокол, используемый с сокета, характерное для семейства указанный адрес.  
  
 `nAddressFormat`  
 Адрес спецификации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения `FALSE` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выделяет дескриптор сокета. Не вызывает [CAsyncSocket::Bind](#bind) для привязки сокета с определенным адресом, поэтому необходимо вызвать `Bind` позже, чтобы привязать сокета с определенным адресом. Можно использовать [CAsyncSocket::SetSockOpt](#setsockopt) для задания параметра сокета, прежде чем он привязан.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CSocket-класс](../../mfc/reference/csocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
