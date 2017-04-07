---
title: "CAsyncSocket-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- network communications
- asynchronous Windows Sockets
- CAsyncSocket class
- Windows Sockets [C++], asynchronous
- communications [C++], network
- sockets [C++], Windows
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7a175fc12146d98becc5d06f80e975df5b5a008
ms.lasthandoff: 02/24/2017

---
# <a name="casyncsocket-class"></a>CAsyncSocket-класс
Представляет Windows Socket, конечная точка обмена данными.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Создает объект `CAsyncSocket`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|Принимает подключения на сокете.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Запросы уведомления о событии для сокета.|  
|[CAsyncSocket::Attach](#attach)|Присоединяет дескриптор сокета `CAsyncSocket` объекта.|  
|[CAsyncSocket::Bind](#bind)|Локальный адрес связывает с сокетом.|  
|[CAsyncSocket::Close](#close)|Закрывает сокет.|  
|[CAsyncSocket::Connect](#connect)|Устанавливает подключение к сокету однорангового узла.|  
|[CAsyncSocket::Create](#create)|Создание сокета.|  
|[CAsyncSocket::Detach](#detach)|Отсоединяет дескриптор сокета из `CAsyncSocket` объекта.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Возвращает указатель на `CAsyncSocket` объекта, учитывая дескриптор сокета.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Возвращает состояние ошибки для последней операции, в которой произошел сбой.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Возвращает адрес сокета однорангового узла, к которому подключается сокет.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Возвращает адрес сокета однорангового узла, к которому сокет является подключенной (маркеры IPv6-адресов).|  
|[CAsyncSocket::GetSockName](#getsockname)|Возвращает локальное имя для сокета.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Возвращает локальное имя для сокета (маркеры IPv6-адресов).|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Получает параметр сокета.|  
|[CAsyncSocket::IOCtl](#ioctl)|Управляет режимом сокета.|  
|[CAsyncSocket::Listen](#listen)|Устанавливает сокет для прослушивания входящих запросов на подключение.|  
|[CAsyncSocket::Receive](#receive)|Получает данные из сокета.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Получает датаграмму и сохраняет исходный адрес.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Получает датаграмму и сохраняет исходный адрес (маркеры IPv6-адресов).|  
|[CAsyncSocket::Send](#send)|Отправляет данные на подключенный сокет.|  
|[CAsyncSocket::SendTo](#sendto)|Отправляет данные в конкретное место назначения.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Отправляет данные в определенное конечное (маркеры IPv6-адресов).|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Задает параметр сокета.|  
|[CAsyncSocket::ShutDown](#shutdown)|Отключает **отправки** или **получения** вызывает для сокета.|  
|[CASyncSocket::Socket](#socket)|Выделяет дескриптор сокета.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Уведомляет прослушивающего сокета, который он может принять ожидающих запросов на подключение, вызвав **Accept**.|  
|[CAsyncSocket::OnClose](#onclose)|Уведомляет закрыл сокет, подключенный сокет.|  
|[CAsyncSocket::OnConnect](#onconnect)|Уведомляет подключение сокета, попытка подключения завершения ли успешно или с ошибкой.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Уведомляет сокет принимающей данные по каналу для чтения на сокет, обычно срочных сообщений.|  
|[CAsyncSocket::OnReceive](#onreceive)|Уведомляет прослушивающего сокета, данные можно получить путем вызова **получения**.|  
|[CAsyncSocket::OnSend](#onsend)|Уведомляет сокета, что он может отправлять данные путем вызова **отправки**.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Присваивает новое значение для `CAsyncSocket` объекта.|  
|[CAsyncSocket::operator СОКЕТА](#operator_socket)|Этот оператор используется для получения **СОКЕТА** handle `CAsyncSocket` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Указывает **СОКЕТА** дескриптор, присоединенные к этому `CAsyncSocket` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CAsyncSocket` инкапсулирует функций API Windows Socket, предоставляя абстракцию объектно ориентированного для программистов, которые хотят использовать сокеты Windows в сочетании с MFC.  
  
 Этот класс основан на предположении, что вы понимаете сетевых подключений. Вы несете ответственность за обработка блокировки различия порядка следования байтов и задать преобразования между Юникодом и многобайтовой строки (MBCS). Если требуется более удобный интерфейс, который управляет этих проблем см. класс [CSocket](../../mfc/reference/csocket-class.md).  
  
 Для использования `CAsyncSocket` объекта, вызывается его конструктор затем вызвать [создать](#create) функцию для создания основной дескриптор сокета (типа `SOCKET`), за исключением для сокетов, принятые на. Для вызова сокета сервера [прослушивания](#listen) функция-член и для вызова сокета клиента [подключение](#connect) функции-члена. Следует вызвать серверный сокет [Accept](#accept) функции при получении запроса на подключение. Использовать оставшиеся `CAsyncSocket` функции для выполнения связи между сокетов. По завершении удаления `CAsyncSocket` объекта, если он был создан в куче; автоматически вызывает деструктор [закрыть](#close) функции. `SOCKET` Тип данных, описанные в статье [Windows Sockets: фон](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  При использовании сокеты MFC в дополнительных потоках в приложении MFC статически скомпонованной, необходимо вызвать `AfxSocketInit` каждого потока, которая использует сокеты инициализировать библиотеку сокетов. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: использование класса CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) и связанных статей. а также [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 Вызовите эту функцию-член принять подключение к сокету.  
  
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
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, которая получает адрес подключения сокета, как известные в сети. Точный формат `lpSockAddr` аргумент определяется семейства адресов, установленных во время создания сокета. Если `lpSockAddr` или `lpSockAddrLen` , равно **NULL**, то возвращаются сведения об удаленном адресе принятого сокета.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах. `lpSockAddrLen` Является параметром результат значений: он изначально должен содержать объем пространства, который указывает `lpSockAddr`; при возвращении, он будет содержать фактическую длину (в байтах) возвращает адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINPROGRESS** Windows Sockets блокирующий вызов выполняется в данный момент.  
  
- **WSAEINVAL** `Listen` не вызываемый перед принять.  
  
- **WSAEMFILE** очередь пуста, после входа на прием и дескрипторы не доступны.  
  
- `WSAENOBUFS`Буферное пространство не доступны.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP** упоминаемого сокета не является типом, поддерживающего службу, ориентированного на подключение.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и присутствуют подключения не принимаются.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура извлекает первое подключение в очереди ожидающих подключений, создает новый сокет с теми же свойствами, как этот сокет и присоединяет его к `rConnectedSocket`. Если нет ожидающих соединений присутствуют в очереди **Accept** возвращает ноль и `GetLastError` возвращает сообщение об ошибке. Принятого сокета ( *rConnectedSocket)* не может использоваться для нескольких подключений. Исходное сокет остается открытым и прослушивания.  
  
 Аргумент `lpSockAddr` является параметр результат, который заносится адрес подключение сокета, как известно, уровня коммуникаций. **Принять** используется с типами сокета на основе подключения, например **неблокируемый**.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 Вызовите эту функцию-член для запроса уведомления о событии для сокета.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lEvent`  
 Битовая маска, который указывает сочетание события сети, в которых заинтересовано приложение.  
  
- **FD_READ** получать уведомления о готовности для чтения.  
  
- **FD_WRITE** получать уведомления, если данные доступны для чтения.  
  
- **FD_OOB** получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** получать уведомление о входящих подключений.  
  
- **FD_CONNECT** получать уведомления о результаты соединения.  
  
- **FD_CLOSE** нужно получать уведомления при сокет закрыт другим компьютером.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** указывает, что один из указанных параметров недопустим.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для указания, какие функции MFC обратного вызова уведомления будет вызываться для сокета. `AsyncSelect`автоматически устанавливает этот сокет неблокирующий режим. Дополнительные сведения см. в статье [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 Вызов этой функции-члена для присоединения `hSocket` дескриптор `CAsyncSocket` объекта.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
 `lEvent`  
 Битовая маска, который указывает сочетание события сети, в которых заинтересовано приложение.  
  
- **FD_READ** получать уведомления о готовности для чтения.  
  
- **FD_WRITE** получать уведомления, если данные доступны для чтения.  
  
- **FD_OOB** получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** получать уведомление о входящих подключений.  
  
- **FD_CONNECT** получать уведомления о результаты соединения.  
  
- **FD_CLOSE** нужно получать уведомления при сокет закрыт другим компьютером.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 **СОКЕТА** дескриптор хранятся в объекте [m_hSocket](#m_hsocket) данные-член.  
  
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
 Сетевой адрес, пунктирная номер, например «128.56.22.8». Передача **NULL** строка этот параметр указывает **CAsyncSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес для назначения этим сокетом.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** указанный адрес уже используется. (См. **SO_REUSEADDR** параметр сокета [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** `nSockAddrLen` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINPROGRESS** Windows Sockets блокирующий вызов выполняется в данный момент.  
  
- **WSAEAFNOSUPPORT** заданного семейства адресов не поддерживается для этого порта.  
  
- **WSAEINVAL** сокет уже связан с адресом.  
  
- `WSAENOBUFS`Недостаточно доступных буферов, слишком много подключений.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура используется в несвязанной датаграмм или сокета потока, перед последующих **подключение** или `Listen` вызовов. Прежде чем он может принимать запросы на подключение, прослушивающего сокета сервера необходимо выбрать номер порта и сделать ее известных Windows Sockets путем вызова **привязки**. **Привязка** устанавливает локальную ассоциацию (номер адреса и порта узла) сокета, присваивая безымянные сокета локальное имя.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 Создает объект пустым сокета.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, необходимо вызвать его **создать** функции-члена для создания **СОКЕТА** структуры данных и привязать его адрес. (На стороне сервера Windows Sockets связи, когда прослушивающего сокета создает сокет для применения в **Accept** вызова не вызывается **создать** для этого socket.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 Закрывает сокет.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция освобождает дескриптор сокета, таким образом, чтобы дополнительные ссылки на него завершится с ошибкой **WSAENOTSOCK**. Если это последняя ссылка на основном сокете, связанные сведения об именах и в очередь данные удаляются. Вызывает деструктор объекта сокета **закрыть** для вас.  
  
 Для `CAsyncSocket`, но не для `CSocket`, семантики **закрыть** затронутые параметры сокетов **SO_LINGER** и **SO_DONTLINGER**. Дополнительные сведения см. в разделе функции-члена `GetSockOpt`.  
  
##  <a name="connect"></a>CAsyncSocket::Connect  
 Вызовите эту функцию-член для установления соединения с несвязанной потока или сокета датаграмм.  
  
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
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная номер, например «128.56.22.8».  
  
 `nHostPort`  
 Порт, идентифицирующая приложение сокета.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес подключенного сокета.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Если это указывает код ошибки **WSAEWOULDBLOCK**и приложение использует overridable обратные вызовы, ваше приложение получит `OnConnect` сообщение по завершении операции подключения. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** указанный адрес уже используется.  
  
- **WSAEINPROGRESS** Windows Sockets блокирующий вызов выполняется в данный момент.  
  
- **WSAEADDRNOTAVAIL** на локальном компьютере недоступен по указанному адресу.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAECONNREFUSED** попытка подключения была отклонена.  
  
- **WSAEDESTADDRREQ** необходим адрес назначения.  
  
- **WSAEFAULT** `nSockAddrLen` Неверный аргумент.  
  
- **WSAEINVAL** Недопустимый сетевой адрес.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных дескрипторов файлов.  
  
- **WSAENETUNREACH** сети невозможен из этого узла в данный момент.  
  
- `WSAENOBUFS`Буферное пространство не доступны. Сокет не подключен.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAETIMEDOUT** попытки подключения тайм-аут без установления подключения.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый соединение не может быть завершена немедленно.  
  
### <a name="remarks"></a>Примечания  
 Если отменяется привязка сокет, уникальные значения присваиваются локальной связи в системе и сокет помечается как привязкой. Обратите внимание, что если поле адрес имя структуры представляет все нули **подключение** возвращается нуль. Чтобы получить расширенные сведения об ошибке, вызовите `GetLastError` функции-члена.  
  
 Для сокетов потока (тип **неблокируемый**), запускается активного подключения внешнего узла. По завершении вызова сокета сокет готов для отправки и приема данных.  
  
 Для сокета датаграмм (тип **SOCK_DGRAM**), задать назначение по умолчанию, который будет использоваться на последующих **отправки** и **получения** вызовов.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 Вызов **создать** после создания объекта сокета для создания Windows socket и присоединить его функции-члена.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketPort`  
 Известный порт для использования с сокет, или 0, если требуется Windows Sockets порт.  
  
 `nSocketType`  
 **Неблокируемый** или **SOCK_DGRAM**.  
  
 `lEvent`  
 Битовая маска, который указывает сочетание события сети, в которых заинтересовано приложение.  
  
- **FD_READ** получать уведомления о готовности для чтения.  
  
- **FD_WRITE** получать уведомления о готовности для записи.  
  
- **FD_OOB** получать уведомления о получении данных по каналу.  
  
- **FD_ACCEPT** получать уведомление о входящих подключений.  
  
- **FD_CONNECT** получать уведомления о завершенных подключения.  
  
- **FD_CLOSE** получать уведомления о закрытием сокета.  
  
 *lpszSockAddress*  
 Указатель на строку, содержащую сетевой адрес подключенного сокета, пунктирная номер, например «128.56.22.8». Передача **NULL** строка этот параметр указывает **CAsyncSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEAFNOSUPPORT** заданного семейства адресов не поддерживается.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEMFILE** доступных дескрипторов файлов.  
  
- `WSAENOBUFS`Буферное пространство не доступны. Не удалось создать сокет.  
  
- **WSAEPROTONOSUPPORT** указанный порт не поддерживается.  
  
- **WSAEPROTOTYPE** указанный порт имеет неверный тип для этого сокета.  
  
- **WSAESOCKTNOSUPPORT** указанный тип сокета не поддерживается в данном семействе адресов.  
  
### <a name="remarks"></a>Примечания  
 **Создание** вызовов [сокета](#socket) и в случае успеха, он вызывает [привязки](#bind) для привязки сокет по указанному адресу. Поддерживаются следующие типы сокета:  
  
- **Неблокируемый** виртуализации, предоставляет надежный, полный дуплекс подключений байтовые потоки. Использует протокол управления передачей (TCP) для семейства адресов Интернета.  
  
- **SOCK_DGRAM** поддерживает датаграммы — пакеты без установления соединения, ненадежное фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета.  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Имейте в виду, что если этот объект сокета идет области, соединение закрывается. Не следует вызывать **создать** для этого нового объекта сокета.  
  
> [!IMPORTANT]
> **Создание** — **не** поточно ориентированными.  При вызове его в многопоточной среде которого оно может вызвать одновременно разными потоками, не забудьте защитить каждый вызов с мьютекс или другие блокировки синхронизации.  
  
 Дополнительные сведения о сокеты потока и датаграммы см. в статьях [Windows Sockets: фон](../../mfc/windows-sockets-background.md) и [Windows Sockets: порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md) и [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 Вызов этой функции-члена для отсоединения **СОКЕТА** обработки в `m_hSocket` элемент данных из `CAsyncSocket` и задайте `m_hSocket` для **NULL**.  
  
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
 Указатель на `CAsyncSocket` объекта, или **NULL** при наличии не `CAsyncSocket` объект присоединяется к `hSocket`.  
  
### <a name="remarks"></a>Примечания  
 При наличии **СОКЕТА** обработки, если `CAsyncSocket` объект не присоединен к дескриптору, функция-член возвращает **NULL**.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 Вызовите эту функцию-член для получения состояния ошибки для последней операции, в которой произошел сбой.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение указывает код ошибки для последней процедуры Windows Sockets API, выполняется этим потоком.  
  
### <a name="remarks"></a>Примечания  
 Если определенная функция-член указывает, что произошла ошибка, `GetLastError` следует вызвать для получения соответствующего кода ошибки. В разделе описаний функций отдельных членов список кодов ошибок применимо.  
  
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
 Ссылка на **UINT** порт, в котором хранится.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, которая получает имя однорангового сокета.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах. При возвращении `lpSockAddrLen` аргумент содержит фактический размер `lpSockAddr` возвращается в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не является достаточным.  
  
- **WSAEINPROGRESS** Windows Sockets блокирующий вызов выполняется в данный момент.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 Вызовите эту функцию-член для получения адреса сокета однорангового узла, к которому этот сокет является подключенной (маркеры IPv6-адресов).  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Параметры  
 `rPeerAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rPeerPort`  
 Ссылка на **UINT** порт, в котором хранится.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не является достаточным.  
  
- **WSAEINPROGRESS** Windows Sockets блокирующий вызов выполняется в данный момент.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
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
 Ссылка на **UINT** порт, в котором хранится.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, которая получает адрес сокета.  
  
 `lpSockAddrLen`  
 Указатель на длину адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не является достаточным.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEINVAL** сокета не привязаны к адреса с **привязки**.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов является особенно полезно при **подключение** вызова без это **привязки** , этот вызов обеспечивает единственное средство, с помощью которого можно определить локальную ассоциацию, которое было задано системой.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 Вызовите эту функцию-член для получения локального имени для сокета (маркеры IPv6-адресов).  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Параметры  
 `rSocketAddress`  
 Ссылка на `CString` объект, получающий пунктирная номер IP-адрес.  
  
 `rSocketPort`  
 Ссылка на **UINT** порт, в котором хранится.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` аргумент не является достаточным.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEINVAL** сокета не привязаны к адреса с **привязки**.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов является таким же, как [CAsyncSocket::GetSockName](#getsockname) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 Этот вызов является особенно полезно при **подключение** вызова без это **привязки** , этот вызов обеспечивает единственное средство, с помощью которого можно определить локальную ассоциацию, которое было задано системой.  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 Вызовите эту функцию-член для получения параметра сокета.  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Параметры  
 `nOptionName`  
 Параметр сокета, для которого используется для извлечения.  
  
 `lpOptionValue`  
 Указатель на буфер, в который возвращается значение запрошенного параметра. Возвращается значение, связанное с параметром, выбранного в буфере `lpOptionValue`. Целое число, на который указывает `lpOptionLen` первоначально должен содержать размер буфера в байтах; и при возвращении устанавливается размер возвращаемого значения. Для **SO_LINGER**, это будет размер `LINGER` структуры; для всех параметров будет размер **BOOL** или `int`, в зависимости от параметра. Список параметров и их размеров, в разделе «Примечания».  
  
 `lpOptionLen`  
 Указатель на размер `lpOptionValue` буфера в байтах.  
  
 `nLevel`  
 Уровень, на котором определен параметр; только поддерживаемые уровни **SOL_SOCKET** и **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Если параметр не был установлен с `SetSockOpt`, то `GetSockOpt` возвращает значение по умолчанию для параметра. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpOptionLen` недопустимый аргумент.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOPROTOOPT** параметр неизвестен или не поддерживается. В частности **SO_BROADCAST** не поддерживается на сокеты типа **неблокируемый**, хотя **SO_ACCEPTCONN**, **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, и **SO_OOBINLINE** не поддерживается на сокеты типа **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 `GetSockOpt`Получает текущее значение для параметра сокета, связанное с сокетом любого типа, в любом состоянии и сохраняет результат в `lpOptionValue`. Параметры влияют на операции сокета, например маршрутизации пакетов, передачи данных по каналу и т. д.  
  
 Поддерживаются следующие параметры для `GetSockOpt`. Тип определяет тип данных, адресованное `lpOptionValue`. **TCP_NODELAY** используется уровень **IPPROTO_TCP**; все остальные параметры использовать уровень **SOL_SOCKET**.  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Сокет прослушивает.|  
|**SO_BROADCAST**|**BOOL**|Сокета настроен для пересылки широковещательных сообщений.|  
|**SO_DEBUG**|**BOOL**|Включена отладка.|  
|**SO_DONTLINGER**|**BOOL**|Если значение равно true, **SO_LINGER** параметр отключен.|  
|**SO_DONTROUTE**|**BOOL**|Маршрутизация отключена.|  
|**SO_ERROR**|`int`|Получить состояние ошибки и очистить.|  
|**SO_KEEPALIVE**|**BOOL**|Активность отправляются.|  
|**SO_LINGER**|**Структура LINGER**|Возвращает текущие параметры ожидания.|  
|**SO_OOBINLINE**|**BOOL**|Получения данных по каналу в обычном потоке данных.|  
|**СЧЕТЧИКА**|`int`|Получает размер буфера.|  
|**SO_REUSEADDR**|**BOOL**|Сокет может быть привязан к адрес, который уже используется.|  
|**SO_SNDBUF**|`int`|Размер буфера для отправляет.|  
|**SO_TYPE**|`int`|Тип сокета (например, **неблокируемый**).|  
|**TCP_NODELAY**|**BOOL**|Отключить алгоритм Nagle для отправки объединенных пакетов.|  
  
 Параметры Berkeley Software Distribution (BSD) не поддерживается для `GetSockOpt` являются:  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Получите метку низкого уровня.|  
|**SO_RCVTIMEO**|`int`|Время ожидания получения.|  
|**SO_SNDLOWAT**|`int`|Послать метку низкого уровня.|  
|**SO_SNDTIMEO**|`int`|Передать тайм-аут.|  
|**IP_OPTIONS**||Получите параметры в IP-заголовок.|  
|**TCP_MAXSEG**|`int`|Получите TCP максимального размера сегмента.|  
  
 Вызов `GetSockOpt` с неподдерживаемый параметр приведет к код ошибки **WSAENOPROTOOPT** , возвращаемого из `GetLastError`.  
  
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
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** `lCommand` не является допустимой командой или `lpArgument` не является приемлемым параметр `lCommand`, или команда не применим к типу сокета указано.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 Эта процедура может использоваться любой сокетом в любом состоянии. Он используется для получения или получения рабочих параметров, связанных с сокета, независимо от протокола и коммуникаций подсистемы. Поддерживаются следующие команды:  
  
- **FIONBIO** включения или отключения режима неблокируемый на сокете. `lpArgument` Параметр указывает на `DWORD`, который является ненулевым, если требуется включить неблокирующий режим и ноль, если это требуется отключить. Если `AsyncSelect` была выполнена на сокет, то любая попытка использовать **IOCtl** значение сокет блокирующем режиме не удастся с **WSAEINVAL**. Чтобы снова установить сокет блокирующем режиме и предотвратить **WSAEINVAL** ошибку, приложение необходимо сначала отключить `AsyncSelect` путем вызова `AsyncSelect` с `lEvent` параметра равно 0, затем вызовите **IOCtl**.  
  
- **FIONREAD** определить максимальное число байтов, считываемых с одним **получения** вызовите из этого сокета. `lpArgument` Параметр указывает на `DWORD` в которой **IOCtl** сохраняет результат. Если этот сокет имеет тип **неблокируемый**, **FIONREAD** возвращает общий объем данных, которыми можно ознакомиться в одном **получения**; это обычно то же самое как общий объем данных в очередь на сокете. Если этот сокет имеет тип **SOCK_DGRAM**, **FIONREAD** возвращает размер первого датаграмм в очереди на сокете.  
  
- **SIOCATMARK** определить, имеет ли чтение всех данных по каналу. Это относится только к сокету типа **неблокируемый** которого был настроен для приема канала данных по каналу ( **SO_OOBINLINE**). Если данные по каналу, не находится в ожидании для чтения, операция возвращает ненулевое значение. В противном случае возвращается 0, а теперь **получения** или `ReceiveFrom` на сокет будет получают некоторые или все данные, предшествующие «марка», приложение должно использовать **SIOCATMARK** операцию, чтобы определить, остается ли все данные. Если есть обычные данные, предшествующие «срочно» (внешнее) данных, он будет получено в порядке. (Обратите внимание, что **получения** или `ReceiveFrom` будет никогда не смешивайте по каналу и обычных данных в рамках одного вызова.) `lpArgument` Параметр указывает на `DWORD` в которой **IOCtl** сохраняет результат.  
  
 Эта функция является подмножеством **ioctl()** в Беркли сокетов. В частности, нет команды аналогичен **FIOASYNC**, хотя **SIOCATMARK** команда только на уровне сокетов, который поддерживается.  
  
##  <a name="listen"></a>CAsyncSocket::Listen  
 Вызовите эту функцию-член для прослушивания входящих запросов на подключение.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Параметры  
 *nConnectionBacklog*  
 Максимальная длина, до которого может расти очереди ожидающих подключений. Допустимый диапазон — от 1 до 5.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEADDRINUSE** попытка прослушивать адреса используется.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEINVAL** сокета не привязанный к **привязки** или уже подключен.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных дескрипторов файлов.  
  
- `WSAENOBUFS`Буферное пространство не доступны.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP** упоминаемого сокета не типа, который поддерживает `Listen` операцию.  
  
### <a name="remarks"></a>Примечания  
 Для приема подключений, сокет сначала создается с **создать**, очередь для входящих подключений, указанном с помощью `Listen`, и затем подключения принимаются с **Accept**. `Listen`применяется только к сокетов, которые поддерживают подключения, то есть, имеющих тип **неблокируемый**. Этот сокет переводится в режим «пассивный», где прочли и в очередь ожидающих приемки процессом входящих подключений.  
  
 Эта функция обычно используется на серверах (или любое приложение, которое хочет принимать подключения), может иметь более одного запроса подключения одновременно: при получении запроса соединения с Переполнение очереди, клиент получит сообщение об ошибке с указанием **WSAECONNREFUSED**.  
  
 `Listen`предпринимает попытку продолжить работать разумно, если отсутствуют доступные порты (дескрипторы). Он будет принимать подключения, пока очередь очищается. Если порты становятся доступными, последующий вызов `Listen` или **Accept** по возможности повторного заполнения очереди для текущего или последнего» невыполненную работу» и возобновить прослушивание входящих подключений.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 Содержит **СОКЕТА** дескриптор для сокета, инкапсулируемого этим `CAsyncSocket` объекта.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 Вызывается платформой для уведомления прослушивающего сокета, который он может принять ожидающих запросов на подключение, вызвав [Accept](#accept) функции-члена.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяется к `OnAccept` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 Вызывается платформой для уведомления этот сокет, что подключенный сокет закрывается его процессом.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяются к `OnClose` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAECONNRESET** соединение было сброшено удаленной стороной.  
  
- **WSAECONNABORTED** подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 Вызывается платформой для уведомления этого при подключении к сокету его попытка подключения завершение, является ли успешно или с ошибкой.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяются к `OnConnect` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAEADDRINUSE** указанный адрес уже используется.  
  
- **WSAEADDRNOTAVAIL** на локальном компьютере недоступен по указанному адресу.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAECONNREFUSED** попытка подключения была принудительно отклонена.  
  
- **WSAEDESTADDRREQ** необходим адрес назначения.  
  
- **WSAEFAULT** `lpSockAddrLen` Неверный аргумент.  
  
- **WSAEINVAL** сокет уже связан с адресом.  
  
- **WSAEISCONN** сокет уже подключен.  
  
- **WSAEMFILE** доступных дескрипторов файлов.  
  
- **WSAENETUNREACH** сети невозможен из этого узла в данный момент.  
  
- `WSAENOBUFS`Буферное пространство не доступны. Сокет не подключен.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** дескриптор является файлом, а не сокета.  
  
- **WSAETIMEDOUT** попытка соединения истекло без установления подключения.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` функция уведомления никогда не вызывается. Для соединений, можно просто вызвать **подключение**, возвращающий при завершении соединения (успешно или с ошибкой). Как обрабатываются уведомления соединения является реализации MFC.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket&#1;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 Вызывается платформой для принимающего сокета с сокета отправки данных по каналу для отправки уведомления.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяются к `OnOutOfBandData` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Данные по каналу является логически независимые канал, связанный с каждой парой подключенных сокетов типа **неблокируемый**. Канал обычно используется для отправки срочные данные.  
  
 Библиотека MFC поддерживает данные по каналу, но пользователи класса `CAsyncSocket` , не рекомендуется использовать их. Более простым способом является создание второй сокет для передачи таких данных. Дополнительные сведения о данных по каналу в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 Вызывается платформой для уведомления этот сокет наличии данных в буфере, можно получить, вызвав **получения** функции-члена.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяются к `OnReceive` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket&#2;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 Вызывается платформой для уведомления сокета, что он теперь можно отправлять данные путем вызова **отправки** функции-члена.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrorCode`  
 Самой последней ошибки на сокете. Следующие коды ошибок применяются к `OnSend` функции-члена:  
  
- **0** функция выполнена успешно.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAsyncSocket&#3;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
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
 В случае успеха дескриптор **СОКЕТА** объекта; в противном случае — **NULL**.  
  
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
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** Просмотр входящих данных. Данные копируются в буфер, но не удалены из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, **получения** возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать **получения** на сокете после `ShutDown` был вызван с `nHow` равным 0 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и **получения** операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком велик для помещения в указанный буфер и было усечено.  
  
- **WSAEINVAL** сокета не привязанный к **привязки**.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для подключенного поток или сокеты датаграмм и используется для считывания входящих данных.  
  
 Для сокетов типа **неблокируемый**, как много информации, как в настоящее время доступен до размера буфера, предоставленного возвращается. Если сокет был настроен для приема канала данных по каналу (параметр сокета **SO_OOBINLINE**) и данные по каналу непрочитанные, возвращаются данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или [OnOutOfBandData](#onoutofbanddata) для определения, остается ли все более-резервному данные для чтения.  
  
 Для сокетов датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до указанного размера буфера, предоставленного. Если датаграмма превышает размер предоставленного буфера, он заполняется первой частью датаграмма, избыточные данные теряются, и **получения** возвращает значение **SOCKET_ERROR** с кодом ошибки равным **WSAEMSGSIZE**. Если входящие данные недоступны на сокет значение **SOCKET_ERROR** возвращается код ошибки, равным **WSAEWOULDBLOCK**. [OnReceive](#onreceive) функции обратного вызова можно использовать для определения, при поступлении дополнительных данных.  
  
 Если сокет имеет тип **неблокируемый** и удаленная сторона закрыл соединение корректно, **получения** будет немедленно завершена с 0 байт, полученных. Если сброс подключения **получения** завершится с ошибкой **WSAECONNRESET**.  
  
 **Получение** должен вызываться только один раз при каждом [CAsyncSocket::OnReceive](#onreceive) вызывается.  
  
### <a name="example"></a>Пример  
  В примере показано [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 Вызовите эту функцию-член для получения датаграммы и хранить исходный адрес в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в `rSocketAddress`.  
  
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
 Ссылка на **UINT** порт, в котором хранится.  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структура, которая содержит адрес источника после возврата.  
  
 `lpSockAddrLen`  
 Указатель на исходный адрес в длину `lpSockAddr` в байтах.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** Просмотр входящих данных. Данные копируются в буфер, но не удалены из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `ReceiveFrom` возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова `GetLastError`. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` недопустимый аргумент: `lpSockAddr` буфер слишком мал, чтобы вместить адрес однорангового узла.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEINVAL** сокета не привязанный к **привязки**.  
  
- **WSAENOTCONN** сокет не подключен ( **неблокируемый** только).  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `ReceiveFrom` на сокете после `ShutDown` был вызван с `nHow` равным 0 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и `ReceiveFrom` операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком велик для помещения в указанный буфер и было усечено.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для чтения входящих данных на сокет (возможно подключение установлено) и записать адрес, с которого было отправлено данных.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Для сокетов типа **неблокируемый**, как много информации, как в настоящее время доступен до размера буфера, предоставленного возвращается. Если сокет был настроен для приема канала данных по каналу (параметр сокета **SO_OOBINLINE**) и данные по каналу непрочитанные, возвращаются данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или `OnOutOfBandData` для определения, остается ли все более-резервному данные для чтения. `lpSockAddr` И `lpSockAddrLen` параметры игнорируются для **неблокируемый** сокетов.  
  
 Для сокетов датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до указанного размера буфера, предоставленного. Если датаграмма превышает размер предоставленного буфера, он заполняется первой частью сообщения, избыточные данные теряются, и `ReceiveFrom` возвращает значение **SOCKET_ERROR** с кодом ошибки равным **WSAEMSGSIZE**.  
  
 Если `lpSockAddr` отлично от нуля, и имеет тип сокета **SOCK_DGRAM**, сетевой адрес сокета, который отправил данные копируются в соответствующий [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на который указывает `lpSockAddrLen` инициализируется размер этой структуры и изменяется при возврате для указания адреса, хранящиеся в ней фактический размер. Если входящие данные недоступны на сокет, `ReceiveFrom` вызов ожидает поступления, если сокет данных неблокируемый. В этом случае значение **SOCKET_ERROR** возвращается код ошибки, равным **WSAEWOULDBLOCK**. `OnReceive` Обратного вызова можно использовать для определения, при поступлении дополнительных данных.  
  
 Если тип сокета **неблокируемый** и удаленная сторона закрыл соединение корректно, `ReceiveFrom` будет немедленно завершена с 0 байт, полученных.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 Вызовите эту функцию-член для получения датаграммы и хранить исходный адрес в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в `rSocketAddress` (дескрипторы IPv6-адресов).  
  
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
 Ссылка на **UINT** порт, в котором хранится.  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_PEEK** Просмотр входящих данных. Данные копируются в буфер, но не удалены из входной очереди.  
  
- **MSG_OOB** обработки данных по каналу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `ReceiveFromEx` возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова `GetLastError`. Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpSockAddrLen` недопустимый аргумент: `lpSockAddr` буфер слишком мал, чтобы вместить адрес однорангового узла.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEINVAL** сокета не привязанный к **привязки**.  
  
- **WSAENOTCONN** сокет не подключен ( **неблокируемый** только).  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `ReceiveFromEx` на сокете после `ShutDown` был вызван с `nHow` равным 0 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и `ReceiveFromEx` операция будет заблокирована.  
  
- **WSAEMSGSIZE** датаграмма слишком велик для помещения в указанный буфер и было усечено.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для чтения входящих данных на сокет (возможно подключение установлено) и записать адрес, с которого было отправлено данных.  
  
 Эта функция является таким же, как [CAsyncSocket::ReceiveFrom](#receivefrom) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 Для сокетов типа **неблокируемый**, как много информации, как в настоящее время доступен до размера буфера, предоставленного возвращается. Если сокет был настроен для приема канала данных по каналу (параметр сокета **SO_OOBINLINE**) и данные по каналу непрочитанные, возвращаются данные только из аппаратного. Приложение может использовать **IOCtlSIOCATMARK** параметр или `OnOutOfBandData` для определения, остается ли все более-резервному данные для чтения. `lpSockAddr` И `lpSockAddrLen` параметры игнорируются для **неблокируемый** сокетов.  
  
 Для сокетов датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до указанного размера буфера, предоставленного. Если датаграмма превышает размер предоставленного буфера, он заполняется первой частью сообщения, избыточные данные теряются, и `ReceiveFromEx` возвращает значение **SOCKET_ERROR** с кодом ошибки равным **WSAEMSGSIZE**.  
  
 Если `lpSockAddr` отлично от нуля, и имеет тип сокета **SOCK_DGRAM**, сетевой адрес сокета, который отправил данные копируются в соответствующий [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на который указывает `lpSockAddrLen` инициализируется размер этой структуры и изменяется при возврате для указания адреса, хранящиеся в ней фактический размер. Если входящие данные недоступны на сокет, `ReceiveFromEx` вызов ожидает поступления, если сокет данных неблокируемый. В этом случае значение **SOCKET_ERROR** возвращается код ошибки, равным **WSAEWOULDBLOCK**. `OnReceive` Обратного вызова можно использовать для определения, при поступлении дополнительных данных.  
  
 Если тип сокета **неблокируемый** и удаленная сторона закрыл соединение корректно, `ReceiveFromEx` будет немедленно завершена с 0 байт, полученных.  
  
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
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **неблокируемый** только).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, **отправки** возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEFAULT** `lpBuf` аргумент не является допустимой частью адресного пространства пользователя.  
  
- **WSAENETRESET** соединения должны быть сброшены, поскольку реализация Windows Sockets удалить его.  
  
- `WSAENOBUFS`Реализация Windows Sockets сообщает сведения о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать **отправки** на сокете после `ShutDown` был вызван с `nHow` присвоено значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокет имеет тип **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAEINVAL** сокета не привязанный к **привязки**.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
### <a name="remarks"></a>Примечания  
 **Отправить** используется для записи выходных данных на подключенных сокетов потока или датаграммы. Для сокетов датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, который задается **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структура, возвращенная `AfxSocketInit`. Если данные слишком длинный атомарным образом проходить через базового протокола, ошибка **WSAEMSGSIZE** возвращается через `GetLastError`, и данные не передаются.  
  
 Обратите внимание, что датаграммы сокета успешная **отправки** не означает, что данные успешно доставлены.  
  
 На `CAsyncSocket` объектов типа **неблокируемый**, число записанных байтов может быть от 1 до требуемой длине в зависимости от доступности буфера на локальную и удаленную узлах.  
  
### <a name="example"></a>Пример  
  В примере показано [CAsyncSocket::OnSend](#onsend).  
  
##  <a name="sendto"></a>CAsyncSocket::SendTo  
 Вызовите эту функцию-член для отправки данных в конкретное место назначения.  
  
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
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная номер, например «128.56.22.8».  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **неблокируемый** только).  
  
 `lpSockAddr`  
 Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес Конечный сокет.  
  
 `nSockAddrLen`  
 Длина адреса в `lpSockAddr` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `SendTo` возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEFAULT** `lpBuf` или `lpSockAddr` параметров не являются частью адресное пространство пользователя или `lpSockAddr` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINVAL** указано недопустимое имя узла.  
  
- **WSAENETRESET** соединения должны быть сброшены, поскольку реализация Windows Sockets удалить его.  
  
- `WSAENOBUFS`Реализация Windows Sockets сообщает сведения о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен ( **неблокируемый** только).  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `SendTo` на сокете после `ShutDown` был вызван с `nHow` присвоено значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокет имеет тип **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
- **WSAEADDRNOTAVAIL** на локальном компьютере недоступен по указанному адресу.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAEDESTADDRREQ** необходим адрес назначения.  
  
- **WSAENETUNREACH** сети невозможен из этого узла в данный момент.  
  
### <a name="remarks"></a>Примечания  
 `SendTo`используется на сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокетов датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, который задается **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком длинный атомарным образом проходить через базового протокола, ошибка **WSAEMSGSIZE** возвращается, и данные не передаются.  
  
 Обратите внимание, что успешная `SendTo` не означает, что данные успешно доставлены.  
  
 `SendTo`используется только на **SOCK_DGRAM** сокета пересылать датаграммы конкретных сокет, идентифицируемый `lpSockAddr` параметр.  
  
 Чтобы послать широковещательное сообщение (на **SOCK_DGRAM** только), адрес в `lpSockAddr` параметр должен быть создан с помощью специальный IP-адрес **INADDR_BROADCAST** (определенный в файле заголовка Windows Sockets WINSOCK. (H) вместе с номером нужный порт. Или, если `lpszHostAddress` параметр **NULL**, сокета настроен для использования. Это обычно задействуются широковещательных датаграммы к превышению размера, с которой может возникнуть фрагментация, которая подразумевает, что часть данных (включая заголовки) датаграмма не должна превышать 512 байт.  
  
 Чтобы обработать IPv6-адресов, используйте [CAsyncSocket::SendToEx](#sendtoex).  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 Вызовите эту функцию-член для отправки данных в определенное конечное (маркеры IPv6-адресов).  
  
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
 Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная номер, например «128.56.22.8».  
  
 `nFlags`  
 Указывает способ, в котором был сделан вызов. Семантика этой функции определяется параметрами сокета и `nFlags` параметр. Последний формируется путем объединения любое из следующих значений с C++ `OR` оператор:  
  
- **MSG_DONTROUTE** указывает, что данные не должны подчиняться маршрутизации. Поставщик Windows Sockets можно игнорировать этот флаг.  
  
- **MSG_OOB** передачи данных по каналу ( **неблокируемый** только).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ошибок нет, `SendToEx` возвращает общее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем количество обозначается `nBufLen`.) В противном случае — значение **SOCKET_ERROR** возвращается, и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEACCES** запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEFAULT** `lpBuf` или `lpSockAddr` параметров не являются частью адресное пространство пользователя или `lpSockAddr` аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).  
  
- **WSAEINVAL** указано недопустимое имя узла.  
  
- **WSAENETRESET** соединения должны быть сброшены, поскольку реализация Windows Sockets удалить его.  
  
- `WSAENOBUFS`Реализация Windows Sockets сообщает сведения о взаимоблокировке буфера.  
  
- **WSAENOTCONN** сокет не подключен ( **неблокируемый** только).  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
- **WSAEOPNOTSUPP MSG_OOB** был указан, но сокета не относится к типу **неблокируемый**.  
  
- **WSAESHUTDOWN** сокета была завершена; невозможно вызвать `SendToEx` на сокете после `ShutDown` был вызван с `nHow` присвоено значение 1 или 2.  
  
- **WSAEWOULDBLOCK** сокет помечен как неблокируемый и Запрошенная операция будет заблокирована.  
  
- **WSAEMSGSIZE** сокет имеет тип **SOCK_DGRAM**, и датаграмма превышает максимальную длину, поддерживаемую реализация Windows Sockets.  
  
- **WSAECONNABORTED** виртуальное подключение было прервано из-за истечения времени ожидания или другой сбой.  
  
- **WSAECONNRESET** виртуальное подключение было сброшено удаленной стороной.  
  
- **WSAEADDRNOTAVAIL** на локальном компьютере недоступен по указанному адресу.  
  
- **WSAEAFNOSUPPORT** адреса из заданного семейства нельзя использовать с этим сокетом.  
  
- **WSAEDESTADDRREQ** необходим адрес назначения.  
  
- **WSAENETUNREACH** сети невозможен из этого узла в данный момент.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является таким же, как [CAsyncSocket::SendTo](#sendto) за исключением того, что он обрабатывает IPv6 адреса также как старые протоколы.  
  
 `SendToEx`используется на сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокетов датаграмм, необходимо соблюдать осторожность не должно превышать максимальный размер пакета IP базовой подсетей, который задается **iMaxUdpDg** элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком длинный атомарным образом проходить через базового протокола, ошибка **WSAEMSGSIZE** возвращается, и данные не передаются.  
  
 Обратите внимание, что успешная `SendToEx` не означает, что данные успешно доставлены.  
  
 `SendToEx`используется только на **SOCK_DGRAM** сокета пересылать датаграммы конкретных сокет, идентифицируемый `lpSockAddr` параметр.  
  
 Чтобы послать широковещательное сообщение (на **SOCK_DGRAM** только), адрес в `lpSockAddr` параметр должен быть создан с помощью специальный IP-адрес **INADDR_BROADCAST** (определенный в файле заголовка Windows Sockets WINSOCK. (H) вместе с номером нужный порт. Или, если `lpszHostAddress` параметр **NULL**, сокета настроен для использования. Это обычно задействуются широковещательных датаграммы к превышению размера, с которой может возникнуть фрагментация, которая подразумевает, что часть данных (включая заголовки) датаграмма не должна превышать 512 байт.  
  
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
 Параметр сокета, для которого для задается значение.  
  
 `lpOptionValue`  
 Указатель на буфер, в котором предоставляется значение запрошенного параметра.  
  
 `nOptionLen`  
 Размер `lpOptionValue` буфера в байтах.  
  
 `nLevel`  
 Уровень, на котором определен параметр; только поддерживаемые уровни **SOL_SOCKET** и **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEFAULT** `lpOptionValue` не является допустимой частью адресного пространства процесса.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAEINVAL** `nLevel` является недопустимым, или информации `lpOptionValue` является недопустимым.  
  
- **WSAENETRESET** ожидания соединения при **SO_KEEPALIVE** имеет значение.  
  
- **WSAENOPROTOOPT** параметр неизвестен или не поддерживается. В частности **SO_BROADCAST** не поддерживается на сокеты типа **неблокируемый**, хотя **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, и **SO_OOBINLINE** не поддерживается на сокеты типа **SOCK_DGRAM**.  
  
- **WSAENOTCONN** соединение было сброшены при **SO_KEEPALIVE** имеет значение.  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 `SetSockOpt`Задает текущее значение для параметра сокета, связанное с сокетом любого типа, в любом состоянии. Несмотря на то, что параметры находятся на нескольких уровнях протокола, эта спецификация определяет только параметры, которые существуют на уровне верхнего края области «сокетов». Параметры влияют на операции сокета, например срочные данные получен ли в обычном потоке данных, является ли широковещательные сообщения могут отправляться на сокет и т. д.  
  
 Существует два типа параметров сокета: логическое параметры включить или отключить функцию или поведение и требующих целочисленное значение или структуры. Для включения логического параметра, `lpOptionValue` указывает от нуля целое число со знаком. Чтобы отключить параметр `lpOptionValue` указывает на целое число, равное нулю. `nOptionLen`должно быть равно **sizeof(BOOL)** для параметров типа Boolean. Другие варианты `lpOptionValue` указывает на целое число или структура, содержащая нужное значение для параметра, и `nOptionLen` длина целого числа или структуры.  
  
 **SO_LINGER** действие, выполняемое при неотправленные данные в очереди на сокете, элементы управления и **закрыть** функция вызывается, чтобы закрыть сокет.  
  
 По умолчанию не может быть привязан сокет (см. [привязки](#bind)) по локальному адресу, который уже используется. В некоторых случаях Однако она может возникнуть необходимость «повторного использования» таким образом адреса. Поскольку каждое соединение однозначно идентифицируется сочетание локальных и удаленных адресов, нет ничего страшного за два разъема привязан к один и тот же локальный адрес, поскольку удаленные адреса отличаются.  
  
 Для информирования реализация Windows Sockets, **привязки** вызов на сокете не должны быть запрещены, так как нужный адрес уже используется другой сокета, приложение должно задать **SO_REUSEADDR** параметра для сокета перед выдачей сокета **привязки** вызова. Обратите внимание, что параметр интерпретируется только во время **привязки** вызова: необязательно таким образом (но) для задания параметра на сокете, который не привязан к существующего адреса, и задание или сброс параметра после **привязки** вызов не имеет никакого влияния на этот или любой другой разъем.  
  
 Приложение может запросить, что реализация Windows Sockets задействовать «keep-alive» пакетов для подключений протокола управления передачей (TCP), включив **SO_KEEPALIVE** параметра сокета. Реализация Windows Sockets не требуется поддерживает использование активность: в этом случае семантику зависит от реализации, но должны соответствовать RFC 1122 раздел 4.2.3.6: «Requirements for Internet Hosts — уровни взаимодействия.» При разрыве соединения в результате «активность» код ошибки **WSAENETRESET** возвращается все вызовы выполняется на сокет, и все последующие вызовы завершатся ошибкой с **WSAENOTCONN**.  
  
 **TCP_NODELAY** параметр отключить алгоритм Nagle. Алгоритм Nagle используется для уменьшения числа небольших пакетов, отправленных в узле буферизации неподтвержденные отправки данных до полного размера пакета могут быть отправлены. Однако для некоторых приложений этот алгоритм может снизить производительность, и **TCP_NODELAY** можно использовать для отключения этой функции. Разработчикам приложений не следует задавать **TCP_NODELAY** Если влияние этого хорошо понятны и требуемой, поскольку параметр **TCP_NODELAY** может иметь существенное отрицательное влияние на производительность сети. **TCP_NODELAY** является единственным поддерживается параметр сокета, который использует уровень **IPPROTO_TCP**; все остальные параметры использовать уровень **SOL_SOCKET**.  
  
 В некоторых реализациях питания Windows Sockets выводить отладочную информацию, если **SO_DEBUG** был установлен приложением.  
  
 Поддерживаются следующие параметры для `SetSockOpt`. Тип определяет тип данных, адресованное `lpOptionValue`.  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Разрешить передачу широковещательных сообщений в сокет.|  
|**SO_DEBUG**|**BOOL**|Записать отладочную информацию.|  
|**SO_DONTLINGER**|**BOOL**|Не блокируют **закрыть** ожидание передаваемые неотправленные данные. Этот параметр эквивалентен параметру **SO_LINGER** с **l_onoff** равен нулю.|  
|**SO_DONTROUTE**|**BOOL**|Не направлять: send непосредственно к интерфейсу.|  
|**SO_KEEPALIVE**|**BOOL**|Отправка активность.|  
|**SO_LINGER**|**Структура LINGER**|Задержка при **закрыть** Если неотправленные данные отсутствуют.|  
|**SO_OOBINLINE**|**BOOL**|Получение данных по каналу в обычном потоке данных.|  
|**СЧЕТЧИКА**|`int`|Укажите размер буфера для получения.|  
|**SO_REUSEADDR**|**BOOL**|Разрешить сокета ограничение на адрес, который уже используется. (See [Bind](#bind).)|  
|**SO_SNDBUF**|`int`|Укажите размер буфера отправки.|  
|**TCP_NODELAY**|**BOOL**|Отключить алгоритм Nagle для отправки объединенных пакетов.|  
  
 Параметры Berkeley Software Distribution (BSD) не поддерживается для `SetSockOpt` являются:  
  
|Значение|Тип|Значение|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Сокет прослушивает|  
|**SO_ERROR**|`int`|Получить состояние ошибки и выполнить очистку.|  
|**SO_RCVLOWAT**|`int`|Получите метку низкого уровня.|  
|**SO_RCVTIMEO**|`int`|Время ожидания получения|  
|**SO_SNDLOWAT**|`int`|Послать метку низкого уровня.|  
|**SO_SNDTIMEO**|`int`|Передать тайм-аут.|  
|**SO_TYPE**|`int`|Тип сокета.|  
|**IP_OPTIONS**||Задайте параметры поля в IP-заголовок.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 Получает вызов, отправляет отключить эту функцию-член, или оба сокетом.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Параметры  
 `nHow`  
 Флаг, который описывает, какие типы операции больше не разрешается, с помощью следующих значений:  
  
- **Получает = 0**  
  
- **отправляет = 1**  
  
- **как = 2**  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова [GetLastError](#getlasterror). Для этой функции-члена применяются следующие ошибки:  
  
- **WSANOTINITIALISED** успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.  
  
- **WSAENETDOWN** реализация Windows Sockets обнаружил сбой подсистемы сети.  
  
- **WSAEINVAL** `nHow` является недопустимым.  
  
- **WSAEINPROGRESS** блокирующие операции Windows Sockets.  
  
- **WSAENOTCONN** сокет не подключен ( **неблокируемый** только).  
  
- **WSAENOTSOCK** дескриптор не сокета.  
  
### <a name="remarks"></a>Примечания  
 `ShutDown`используется для всех типов сокетов для отключения приема и передачи. Если `nHow` равно 0, последующие получает на сокет будет запрещена. Это не влияет на нижнем уровне протокола.  
  
 Окно TCP для Transmission Control Protocol (TCP), не изменяются и входящие данные будут приняты (но не подтвержденного), пока не будет исчерпан окна. Для протокола UDP (User Datagram), входящие датаграммы принимаются и в очередь. В любом случае будет создаваться ошибки ICMP-пакет. Если `nHow` имеет значение 1, последующие отправляет запрещены. Сокеты TCP будут отправляться FIN. Параметр `nHow` 2 отключает обоих передачу и прием, как описано выше.  
  
 Обратите внимание, что `ShutDown` не закрыть сокет и ресурсами, сокет не будут освобождены до **закрыть** вызывается. Приложение не следует полагаться на возможность повторного использования сокет, после завершения работы. В частности, реализация Windows Sockets не требуется для поддержки использования **подключение** таких сокетом.  
  
### <a name="example"></a>Пример  
  В примере показано [CAsyncSocket::OnReceive](#onreceive).  
  
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
 Битовая маска, определяющая сочетание события сети, в которых заинтересовано приложение.  
  
- `FD_READ`: Нужно получать уведомления о готовности для чтения.  
  
- `FD_WRITE`: Нужно получать уведомления о готовности для записи.  
  
- `FD_OOB`: Нужно получать уведомления о получении данных по каналу.  
  
- `FD_ACCEPT`: Нужно получать уведомления о входящих подключений.  
  
- `FD_CONNECT`: Нужно получать уведомления о завершенных подключения.  
  
- `FD_CLOSE`: Нужно получать уведомления о закрытием сокета.  
  
 `nProtocolType`  
 Протокол, используемый с сокетом, относящиеся к семейству указанный адрес.  
  
 `nAddressFormat`  
 Адрес семейства спецификации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения `FALSE` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выделяет дескриптор сокета. Он не вызывает [CAsyncSocket::Bind](#bind) для привязки сокет с определенным адресом, поэтому необходимо вызвать `Bind` позже, чтобы привязать сокет с определенным адресом. Можно использовать [CAsyncSocket::SetSockOpt](#setsockopt) для задания параметра сокета, прежде чем он привязан.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CSocket-класс](../../mfc/reference/csocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)

