---
title: Класс CAsyncSocket
ms.date: 11/04/2016
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
ms.openlocfilehash: 29fe705292b223a0ae367d34d67a99aa60fb719c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660022"
---
# <a name="casyncsocket-class"></a>Класс CAsyncSocket

Представляет сокет Windows — конечную точку сетевого взаимодействия.

## <a name="syntax"></a>Синтаксис

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Создает объект `CAsyncSocket`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::Accept](#accept)|Принимает подключения через сокет.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Запросы уведомления о событии для сокета.|
|[CAsyncSocket::Attach](#attach)|Прикрепляет дескриптор сокета `CAsyncSocket` объекта.|
|[CAsyncSocket::Bind](#bind)|Связывает локальный адрес с сокетом.|
|[CAsyncSocket::Close](#close)|Закрывает сокет.|
|[CAsyncSocket::Connect](#connect)|Устанавливает подключение к сокету однорангового узла.|
|[CAsyncSocket::Create](#create)|Создает сокет.|
|[CAsyncSocket::Detach](#detach)|Отсоединяет дескриптор сокета из `CAsyncSocket` объекта.|
|[CAsyncSocket::FromHandle](#fromhandle)|Возвращает указатель на `CAsyncSocket` объект, которому передан дескриптор сокета.|
|[CAsyncSocket::GetLastError](#getlasterror)|Получает состояние ошибки для последней операции со сбоем.|
|[CAsyncSocket::GetPeerName](#getpeername)|Возвращает адрес сокета однорангового узла, к которому подключен сокета.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Возвращает адрес сокета однорангового узла, к которому сокет является подключенной (маркеры IPv6-адресов).|
|[CAsyncSocket::GetSockName](#getsockname)|Возвращает локальное имя для сокета.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Возвращает локальное имя для сокета (маркеры IPv6-адресов).|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Получает параметр сокета.|
|[CAsyncSocket::IOCtl](#ioctl)|Управляет режимом сокета.|
|[CAsyncSocket::Listen](#listen)|Устанавливает сокет для прослушивания входящих запросов на подключение.|
|[CAsyncSocket::Receive](#receive)|Получает данные из сокета.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Принимает датаграмму и сохраняет исходный адрес.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Принимает датаграмму и сохраняет адрес источника (маркеры IPv6-адресов).|
|[CAsyncSocket::Send](#send)|Отправляет данные в подключенный сокет.|
|[CAsyncSocket::SendTo](#sendto)|Отправляет данные в определенное место назначения.|
|[CAsyncSocket::SendToEx](#sendtoex)|Отправляет данные в определенное место назначения (маркеры IPv6-адресов).|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Задает параметр сокета.|
|[CAsyncSocket::ShutDown](#shutdown)|Отключает `Send` и/или `Receive` вызывает на сокете.|
|[CASyncSocket::Socket](#socket)|Выделяет дескриптор сокета.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|Уведомляет прослушивающий сокет, который он может принять ожидающих запросов на подключение, вызвав `Accept`.|
|[CAsyncSocket::OnClose](#onclose)|Уведомляет закрыл сокет, сокет подключен к нему.|
|[CAsyncSocket::OnConnect](#onconnect)|Уведомляет подключения сокета, что попытка подключения завершена, является ли успешно или с ошибкой.|
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Уведомляет принимающий сокет-каналу данных для чтения для сокета, обычно сообщение срочных.|
|[CAsyncSocket::OnReceive](#onreceive)|Уведомляет сокете прослушивания данных требуется получить, вызвав `Receive`.|
|[CAsyncSocket::OnSend](#onsend)|Уведомляет сокету, что он может отправлять данные путем вызова `Send`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::operator =](#operator_eq)|Назначает новое значение для `CAsyncSocket` объекта.|
|[CAsyncSocket::operator СОКЕТА](#operator_socket)|Этот оператор используется для получения дескриптор СОКЕТА `CAsyncSocket` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Указывает дескриптор СОКЕТА, прикрепленный к этому `CAsyncSocket` объекта.|

## <a name="remarks"></a>Примечания

Класс `CAsyncSocket` инкапсулирует API функции сокетов Windows, предоставляя абстракцию объектно ориентированного для программистов, которые хотят использовать сокеты Windows в сочетании с MFC.

Этот класс основана на предположении, что вы понимаете сетевых подключений. Вы несете ответственность за обработку блокировки, различия порядка следования байтов и преобразования между Юникодом и многобайтовой задать строки (MBCS). Если требуется более удобный интерфейс, который управляет эти проблемы, см. в разделе класса [CSocket](../../mfc/reference/csocket-class.md).

Для использования `CAsyncSocket` объекта, вызовите его конструктор затем вызвать [создать](#create) функции, чтобы создать базовый дескриптор сокета (типа `SOCKET`), за исключением для сокетов, принятые на. Для вызова сокета сервера [прослушивания](#listen) функция-член и для вызова сокета клиента [Connect](#connect) функция-член. Сокет сервера следует вызывать [Accept](#accept) функции при получении запроса на подключение. Использовать оставшиеся `CAsyncSocket` функции, чтобы выполнить обмен данными между сокетов. По завершении удаления `CAsyncSocket` объекта, если он был создан в куче; автоматически вызывает деструктор [закрыть](#close) функции. Тип данных СОКЕТА описан в статье [Windows Sockets: фон](../../mfc/windows-sockets-background.md).

> [!NOTE]
>  С помощью сокетов MFC в второстепенных потоков в приложении MFC статически скомпонованной необходимо вызвать метод `AfxSocketInit` в каждом потоке, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.

Дополнительные сведения см. в разделе [Windows Sockets: использование класса CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) и связанных статей. а также [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

##  <a name="accept"></a>  CAsyncSocket::Accept

Эта функция члена принять подключение к сокету.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Параметры

*rConnectedSocket*<br/>
Ссылка, определяющий новый сокет, который доступен для подключения.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры, получающей адрес подключения сокета, как известные в сети. Точный формат *lpSockAddr* аргумент определяется семейство адресов, определяются, когда сокет был создан. Если *lpSockAddr* и/или *lpSockAddrLen* равны NULL, то данные об удаленном адресе допущенный сокет не возвращаются.

*lpSockAddrLen*<br/>
Указатель на длину адресов в *lpSockAddr* в байтах. *LpSockAddrLen* является параметром значения результат: изначально, она должна содержать объем пространства, на которые указывают *lpSockAddr*; при возврате, он будет содержать фактическая длина (в байтах) возвращает адрес.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).

- Объект WSAEINPROGRESS, вызовите блокировки сокетов Windows уже выполняется.

- WSAEINVAL `Listen` не вызванного перед принять.

- WSAEMFILE очередь пуста при входе, чтобы принять и нет дескрипторов доступны.

- Доступна WSAENOBUFS нет места в буфере.

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP указанный сокет не типом, поддерживающим службу, ориентированного на подключение.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и присутствуют соединения не принимаются.

### <a name="remarks"></a>Примечания

Эта процедура извлекает первое подключение в очереди ожидающих подключений, создает новый сокет с теми же свойствами, что этот сокет и присоединяет его к *rConnectedSocket*. Если нет ожидающих подключений в очереди, `Accept` возвращает ноль и `GetLastError` возвращает сообщение об ошибке. Допущенный сокет ( *rConnectedSocket)* не позволяет принимать дополнительные подключения. Исходное сокет остается открытым и ожидает передачи данных.

Аргумент *lpSockAddr* является параметр результата, который заполняется адрес подключения сокета, как известные. `Accept` используется с типами сокета на основе подключения, например SOCK_STREAM.

##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect

Вызовите эту функцию-член для запроса уведомления о событии для сокета.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Параметры

*lEvent*<br/>
Битовая маска, который указывает сочетание событий сети, в которых заинтересовано приложение.

- FD_READ хотите получать уведомления о готовности для чтения.

- FD_WRITE должны получать уведомления, когда данные доступны для чтения.

- FD_OOB должны получать уведомление о появлении-каналу данных.

- FD_ACCEPT хотите получать уведомления о входящих подключений.

- FD_CONNECT хотите получать уведомления о результаты соединения.

- FD_CLOSE хотите получать уведомления, когда сокет закрыт одноранговым узлом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEINVAL указывает, что один из указанных параметров был недопустимым.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

### <a name="remarks"></a>Примечания

Эта функция используется для указания, какие функции MFC обратного вызова уведомления будет вызываться для сокета. `AsyncSelect` автоматически устанавливает этот сокет в неблокирующем режиме. Дополнительные сведения см. в статье [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="attach"></a>  CAsyncSocket::Attach

Вызовите эту функцию-член для присоединения *hSocket* дескриптор `CAsyncSocket` объекта.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит дескриптор для сокета.

*lEvent*<br/>
Битовая маска, который указывает сочетание событий сети, в которых заинтересовано приложение.

- FD_READ хотите получать уведомления о готовности для чтения.

- FD_WRITE должны получать уведомления, когда данные доступны для чтения.

- FD_OOB должны получать уведомление о появлении-каналу данных.

- FD_ACCEPT хотите получать уведомления о входящих подключений.

- FD_CONNECT хотите получать уведомления о результаты соединения.

- FD_CLOSE хотите получать уведомления, когда сокет закрыт одноранговым узлом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно.

### <a name="remarks"></a>Примечания

Дескриптор СОКЕТА сохраняется в объекте [m_hSocket](#m_hsocket) данные-член.

##  <a name="bind"></a>  CAsyncSocket::Bind

Вызовите эту функцию-член должен быть сопоставлен локальный адрес сокета.

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Параметры

*nSocketPort*<br/>
Порт, идентифицирующая приложение сокета.

*lpszSocketAddress*<br/>
Сетевой адрес, пунктирная числа, например «128.56.22.8». Передача NULL строка этот параметр указывает `CAsyncSocket` экземпляр должен контролировать действия клиентов на всех сетевых интерфейсов.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес, связываемый с этим сокетом.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEADDRINUSE указанный адрес уже используется. (См. в разделе параметр сокета SO_REUSEADDR в [SetSockOpt](#setsockopt).)

- WSAEFAULT *nSockAddrLen* аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).

- Объект WSAEINPROGRESS, вызовите блокировки сокетов Windows уже выполняется.

- WSAEAFNOSUPPORT заданного семейства адресов не поддерживается по данному порту.

- WSAEINVAL сокет уже связан с адресом.

- WSAENOBUFS не достаточно буферов доступных, слишком много подключений.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

Она используется на неподключенный датаграмм или сокета потока, прежде чем последующих `Connect` или `Listen` вызовы. Прежде чем он может принимать запросы на подключение, прослушивающего сокета сервера необходимо выберите номер порта и сделать ее известных Windows Sockets, вызвав `Bind`. `Bind` Устанавливает локальную ассоциацию (номер адреса и порта узла) сокета путем назначения локального имени без имени сокета.

##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket

Создает объект пустым сокета.

```
CAsyncSocket();
```

### <a name="remarks"></a>Примечания

После создания объекта, необходимо вызвать его `Create` функция-член для создания структуры данных СОКЕТА и привязать его адрес. (На стороне сервера Windows Sockets связи, если прослушивающий сокет создает сокет для использования в `Accept` вызова не вызывается `Create` для этого сокета.)

##  <a name="close"></a>  CAsyncSocket::Close

Закрывает сокет.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Эта функция освобождает дескриптор сокета, таким образом, чтобы дополнительные ссылки на него завершится с ошибкой WSAENOTSOCK. Если это последняя ссылка на основном сокете, удаляются связанные сведения об именах и данных в очереди. Вызовы деструктора объекта сокета `Close` для вас.

Для `CAsyncSocket`, но не для `CSocket`, семантика `Close` влияют параметры сокета SO_LINGER и SO_DONTLINGER. Для получения дополнительных сведений см. в разделе функция-член `GetSockOpt`.

##  <a name="connect"></a>  CAsyncSocket::Connect

Вызовите эту функцию-член для установления соединения неподключенный поток или сокета датаграмм.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Параметры

*lpszHostAddress*<br/>
Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная числа, например «128.56.22.8».

*nHostPort*<br/>
Порт, идентифицирующая приложение сокета.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес подключенного сокета.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). Если приложение использует переопределяемый обратных вызовов это указывает код ошибки WSAEWOULDBLOCK, приложение получит `OnConnect` сообщение при завершении операции подключения. К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEADDRINUSE указанный адрес уже используется.

- Объект WSAEINPROGRESS, вызовите блокировки сокетов Windows уже выполняется.

- WSAEADDRNOTAVAIL указанный адрес не доступен на локальном компьютере.

- WSAEAFNOSUPPORT адреса из заданного семейства не может использоваться с этим сокетом.

- WSAECONNREFUSED попытка подключения была отклонена.

- Необходим адрес назначения WSAEDESTADDRREQ объект.

- WSAEFAULT *nSockAddrLen* Неверный аргумент.

- WSAEINVAL недопустимый адрес узла.

- WSAEISCONN сокет уже подключен.

- WSAEMFILE нет доступных дополнительных дескрипторов файлов.

- WSAENETUNREACH сеть недоступна с этого узла в настоящее время.

- Доступна WSAENOBUFS нет места в буфере. Сокет не подключен.

- WSAENOTSOCK дескриптор не сокета.

- WSAETIMEDOUT попытка соединения истекло без установления подключения.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и соединение не может быть закончена немедленно.

### <a name="remarks"></a>Примечания

Если отменяется привязка сокет, уникальные значения присваиваются локальную ассоциацию системой и сокет помечается как привязать. Обратите внимание, что если в поле адрес со структурой имени является все нули `Connect` возвращает нуль. Чтобы получить расширенные сведения об ошибке, вызовите `GetLastError` функция-член.

Для сокетов потока (тип SOCK_STREAM) активное соединение инициируется для внешнего размещения. По завершении вызова сокета сокет готов для отправки и приема данных.

Для сокета датаграмм (тип SOCK_DGRAM), имеет значение назначение по умолчанию, который будет использоваться на последующих `Send` и `Receive` вызовов.

##  <a name="create"></a>  CAsyncSocket::Create

Вызовите `Create` функция-член после построения объект сокета, чтобы создать сокет Windows и подключить его.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Параметры

*nSocketPort*<br/>
Известный порт для использования с сокет, или 0, если требуется Windows Sockets порт.

*nSocketType*<br/>
SOCK_STREAM или SOCK_DGRAM.

*lEvent*<br/>
Битовая маска, который указывает сочетание событий сети, в которых заинтересовано приложение.

- FD_READ хотите получать уведомления о готовности для чтения.

- FD_WRITE хотите получать уведомления о готовности для записи.

- FD_OOB должны получать уведомление о появлении-каналу данных.

- FD_ACCEPT хотите получать уведомления о входящих подключений.

- FD_CONNECT хотите получать уведомления о завершенных подключения.

- FD_CLOSE хотите получать уведомления о закрытии сокета.

*lpszSockAddress*<br/>
Указатель на строку, содержащую сетевой адрес подключенного сокета, пунктирная числа, например «128.56.22.8». Передача NULL строка этот параметр указывает `CAsyncSocket` экземпляр должен контролировать действия клиентов на всех сетевых интерфейсов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEAFNOSUPPORT заданного семейства адресов не поддерживается.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAEMFILE нет доступных дополнительных дескрипторов файлов.

- Доступна WSAENOBUFS нет места в буфере. Не удалось создать сокет.

- WSAEPROTONOSUPPORT указанный порт не поддерживается.

- WSAEPROTOTYPE указанный порт имеет неверный тип для этого сокета.

- WSAESOCKTNOSUPPORT указанный тип сокета не поддерживается в данном семействе адресов.

### <a name="remarks"></a>Примечания

`Create` вызовы [сокета](#socket) и в случае успешного выполнения она вызывает [привязать](#bind) для привязывает сокет к указанному адресу. Поддерживаются следующие типы сокета:

- SOCK_STREAM предоставляет виртуализации, надежный, дуплексная подключения, байтовые потоки. Использует протокол управления передачей (TCP) для семейства адресов Интернета.

- SOCK_DGRAM поддерживает датаграммы — без установления соединения, ненадежные пакеты фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета.

    > [!NOTE]
    >  `Accept` Функция-член принимает ссылку на новую, пустую `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода `Accept`. Имейте в виду, что если этот объект сокета идет области, соединение закрывается. Не вызывайте `Create` для этого нового объекта сокета.

> [!IMPORTANT]
> `Create` — **не** поточно ориентированными.  При вызове его в многопоточной среде где он может быть вызван одновременно разными потоками, не забудьте защитить каждый вызов с мьютекс или другая блокировка синхронизации.

Дополнительные сведения о stream и датаграмм сокетов, см. в статьях [Windows Sockets: фон](../../mfc/windows-sockets-background.md) и [Windows Sockets: порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md) и [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="detach"></a>  CAsyncSocket::Detach

Вызовите эту функцию-член для отсоединения дескриптора СОКЕТА в *m_hSocket* элемент данных из `CAsyncSocket` и задайте *m_hSocket* значение NULL.

```
SOCKET Detach();
```

##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle

Возвращает указатель на `CAsyncSocket` объект.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит дескриптор для сокета.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CAsyncSocket` объекта, или значение NULL, если не `CAsyncSocket` объект присоединен к *hSocket*.

### <a name="remarks"></a>Примечания

Когда дескриптор СОКЕТА, если `CAsyncSocket` объект не присоединен к дескриптору, функция-член возвращает значение NULL.

##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError

Эта функция члена для получения состояния ошибки для последней операции со сбоем.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение указывает код ошибки для последнего Windows Sockets API процедуры, выполняемые этим потоком.

### <a name="remarks"></a>Примечания

Когда функция-член указывает, что произошла ошибка, `GetLastError` должен вызываться для извлечения кода соответствующее сообщение об ошибке. См. в разделе описания отдельных членов функции список кодов ошибок применимо.

Дополнительные сведения о кодах ошибок см. в разделе [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="getpeername"></a>  CAsyncSocket::GetPeerName

Вызывайте эту функцию члена, чтобы получить адрес сокета однорангового узла, к которому подключен этот сокет.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Параметры

*rPeerAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rPeerPort*<br/>
Ссылка на целое число без знака, который хранит порт.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры, который получает имя однорангового узла сокета.

*lpSockAddrLen*<br/>
Указатель на длину адресов в *lpSockAddr* в байтах. При возвращении *lpSockAddrLen* аргумент содержит фактический размер *lpSockAddr* возвращается в байтах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* аргумент не может быть достаточно большим.

- Объект WSAEINPROGRESS, вызовите блокировки сокетов Windows уже выполняется.

- WSAENOTCONN сокет не подключен.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

Для обработки IPv6-адресов, использовать [CAsyncSocket::GetPeerNameEx](#getpeernameex).

##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx

Вызывайте эту функцию член, чтобы получить адрес сокета однорангового узла, к которому этот сокет находится подключенного (маркеры IPv6-адресов).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Параметры

*rPeerAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rPeerPort*<br/>
Ссылка на целое число без знака, который хранит порт.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* аргумент не может быть достаточно большим.

- Объект WSAEINPROGRESS, вызовите блокировки сокетов Windows уже выполняется.

- WSAENOTCONN сокет не подключен.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

Эта функция совпадает со значением [CAsyncSocket::GetPeerName](#getpeername) за исключением того, что он обрабатывает IPv6 адреса также, как можно более старые протоколы.

##  <a name="getsockname"></a>  CAsyncSocket::GetSockName

Вызывайте эту функцию члена, чтобы получить локальное имя для сокета.

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Параметры

*rSocketAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rSocketPort*<br/>
Ссылка на целое число без знака, который хранит порт.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры, получающей адрес сокета.

*lpSockAddrLen*<br/>
Указатель на длину адресов в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* аргумент не может быть достаточно большим.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOTSOCK дескриптор не сокета.

- Сокет не привязан к адрес с WSAEINVAL `Bind`.

### <a name="remarks"></a>Примечания

Этот вызов особенно полезна при `Connect` вызова без это `Bind` ; этот вызов обеспечивает исключительную с помощью которого можно определить локальную ассоциацию, который был задан в системе.

Для обработки IPv6-адресов, использовать [CAsyncSocket::GetSockNameEx](#getsocknameex)

##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx

Вызов этой функции-члена для получения локального имени для сокета (маркеры IPv6-адресов).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Параметры

*rSocketAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rSocketPort*<br/>
Ссылка на целое число без знака, который хранит порт.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* аргумент не может быть достаточно большим.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOTSOCK дескриптор не сокета.

- Сокет не привязан к адрес с WSAEINVAL `Bind`.

### <a name="remarks"></a>Примечания

Этот вызов является таким же, как [CAsyncSocket::GetSockName](#getsockname) за исключением того, что он обрабатывает IPv6 адреса также, как можно более старые протоколы.

Этот вызов особенно полезна при `Connect` вызова без это `Bind` ; этот вызов обеспечивает исключительную с помощью которого можно определить локальную ассоциацию, который был задан в системе.

##  <a name="getsockopt"></a>  CAsyncSocket::GetSockOpt

Вызовите эту функцию-член для извлечения параметра сокета.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Параметры

*nOptionName*<br/>
Параметр сокета, для которого, значение которого требуется получить.

*lpOptionValue*<br/>
Указатель на буфер, в котором запрошенный параметр значение должны быть возвращены. Значение, связанное с выбранным параметром возвращается в буфере *lpOptionValue*. Целое число, на которые указывают *lpOptionLen* изначально должен содержать размер буфера в байтах; и при возврате, он будет присвоено размер возвращаемого значения. Для SO_LINGER, это будет размер `LINGER` структуры; все остальные параметры она размер BOOL или **int**в зависимости от параметра. См. список параметров и их размеры в разделе "Примечания".

*lpOptionLen*<br/>
Указатель на размер *lpOptionValue* буфера в байтах.

*nLevel*<br/>
Уровень, по которому параметр определен; только поддерживаемые уровни: SOL_SOCKET и IPPROTO_TCP.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). Если параметр никогда не было установлено с помощью `SetSockOpt`, затем `GetSockOpt` возвращает значение по умолчанию для параметра. К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpOptionLen* предоставил недопустимый аргумент.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOPROTOOPT параметр неизвестен или не поддерживается. В частности SO_BROADCAST сокеты SOCK_STREAM при SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER и SO_OOBINLINE не поддерживаются для сокетов типа SOCK_DGRAM типа не поддерживается.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

`GetSockOpt` Извлекает текущее значение для параметра сокета, связанные с сокетом любого типа, в любом состоянии и сохраняет результат в *lpOptionValue*. Параметры влияют на операции сокета, например маршрутизации пакетов, передача данных каналу и т. д.

Следующие параметры поддерживаются для `GetSockOpt`. Тип указывает тип данных, адресуемый другим *lpOptionValue*. Параметр TCP_NODELAY использует уровня IPPROTO_TCP; все другие параметры могут использоваться уровень SOL_SOCKET.

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Сокет прослушивает.|
|SO_BROADCAST|BOOL|Сокета настроен для передачи широковещательных сообщений.|
|SO_DEBUG|BOOL|Отладка включена.|
|SO_DONTLINGER|BOOL|Значение true, если параметр SO_LINGER отключен.|
|SO_DONTROUTE|BOOL|Маршрутизация отключена.|
|SO_ERROR|**int**|Получить состояние ошибки и очистить.|
|SO_KEEPALIVE|BOOL|Активность отправляются.|
|SO_LINGER|`struct LINGER`|Возвращает текущие параметры ожидания.|
|SO_OOBINLINE|BOOL|Каналу данных принимается в обычном потоке данных.|
|SO_RCVBUF|int|Получает размер буфера для.|
|SO_REUSEADDR|BOOL|Сокет можно привязать к адресу, который уже используется.|
|SO_SNDBUF|**int**|Размер буфера для отправляет.|
|SO_TYPE|**int**|Тип сокета (например, SOCK_STREAM).|
|TCP_NODELAY|BOOL|Отключить алгоритм Nagle для отправки объединенных пакетов.|

Параметры Berkeley Software Distribution (BSD) не поддерживается для `GetSockOpt` являются:

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Получите метку низкого уровня.|
|SO_RCVTIMEO|**int**|Время ожидания получения.|
|SO_SNDLOWAT|**int**|Отправьте метку низкого уровня.|
|SO_SNDTIMEO|**int**|Отправьте время ожидания.|
|IP_OPTIONS||Получение параметров в заголовке IP-адрес.|
|TCP_MAXSEG|**int**|Получите максимальный размер TCP.|

Вызов `GetSockOpt` неподдерживаемый параметр приведет к с кодом ошибки, возвращаемой из WSAENOPROTOOPT `GetLastError`.

##  <a name="ioctl"></a>  CAsyncSocket::IOCtl

Вызовите эту функцию-член для управления режимом сокета.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Параметры

*lCommand*<br/>
Команда для выполнения на сокете.

*lpArgument*<br/>
Указатель на параметр для *lCommand*.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEINVAL *lCommand* не является допустимой команды, или *lpArgument* не является допустимым параметром для *lCommand*, или команда не применим к типу сокета предоставленные .

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

Эта процедура может использоваться на любой сокета в любом состоянии. Он используется для получения или извлечение работы параметров, связанную с сокетом, независимо от подсистемы протокола и коммуникаций. Поддерживаются следующие команды:

- Fionbio СПЕЦИФИКАЦИИ включить или отключить неблокирующем режиме на сокете. *LpArgument* указывает на параметр `DWORD`, который является ненулевым, если требуется включить неблокирующем режиме, и нуль, если это требуется отключить. Если `AsyncSelect` была выполнена на сокете, то любая попытка использовать `IOCtl` присвоить сокет обратно в блокирующем режиме завершится с WSAEINVAL. Чтобы задать сокет обратно в режим блокировки, ошибка не WSAEINVAL приложения необходимо сначала отключить `AsyncSelect` путем вызова `AsyncSelect` с *lEvent* параметра равно 0, затем вызвать `IOCtl`.

- Fionread СПЕЦИФИКАЦИИ определить максимальное число байтов, которые могут быть считаны с одним `Receive` вызов из этот сокет. *LpArgument* указывает параметр в `DWORD` в котором `IOCtl` сохраняет результат. Если этот сокет типа SOCK_STREAM, fionread СПЕЦИФИКАЦИИ возвращает общий объем данных, который можно считать в одном `Receive`; обычно это же, как общий объем данных в очередь на сокете. Если этот сокет имеет тип SOCK_DGRAM, fionread СПЕЦИФИКАЦИИ возвращает размер первого датаграмм в очереди на сокете.

- SIOCATMARK определить, имеет ли чтение всех-каналу данных. Это относится только к сокету типа SOCK_STREAM, который был настроен для приема канала каких-либо-каналу данных (SO_OOBINLINE). Если нет-каналу данных находится в состоянии ожидания для чтения, операция возвращает ненулевое значение. В противном случае возвращается 0, а теперь `Receive` или `ReceiveFrom` над сокет будет получить некоторые или все данные, предшествующие «пометить»; приложение должно использовать SIOCATMARK операцию, чтобы определить, остается ли все данные. Есть ли все обычные данные перед словом «срочно» (внешнего) данных, ее получения в порядке. (Обратите внимание, что `Receive` или `ReceiveFrom` никогда не будет сочетать-каналу и обычного распределения данных в одном вызове.) *LpArgument* указывает параметр в `DWORD` в котором `IOCtl` сохраняет результат.

Эта функция представляет собой подмножество `ioctl()` в сокетов Беркли. В частности нет ни одной команды, который представляет собой эквивалент fioasync СПЕЦИФИКАЦИИ, хотя SIOCATMARK — это команда только сокета на уровне, который поддерживается.

##  <a name="listen"></a>  CAsyncSocket::Listen

Вызовите эту функцию-член для прослушивания входящих запросов на подключение.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Параметры

*nConnectionBacklog*<br/>
Максимальная длина, до которого может вырасти очередь ожидающих подключений. Допустимый диапазон — от 1 до 5.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- Была предпринята попытка WSAEADDRINUSE прослушивать адреса используется.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- Сокет не привязанный к WSAEINVAL `Bind` или уже подключен.

- WSAEISCONN сокет уже подключен.

- WSAEMFILE нет доступных дополнительных дескрипторов файлов.

- Доступна WSAENOBUFS нет места в буфере.

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP, на которую указывает ссылка сокета не принадлежит тип, поддерживающий `Listen` операции.

### <a name="remarks"></a>Примечания

Для приема подключений, сокет сначала создается с помощью `Create`, невыполненной работы для входящих подключений указывается с помощью `Listen`, и затем будут приниматься соединения с `Accept`. `Listen` применяется только к сокетов, которые поддерживают подключения, то есть тех типа SOCK_STREAM. Этот сокет переводится в режим «пассивным», где подтвержден и в очередь, ожидающую принятия процессом входящие подключения.

Эта функция обычно используется серверов (или любое приложение, которое хочет принимать подключения), может выполнять несколько запросов на соединение в текущий момент: Если запрос подключения поступает с Переполнение очереди, клиент получит ошибку с указанием WSAECONNREFUSED.

`Listen` пытается продолжать функционировать разумно, если нет доступных портов (дескрипторы). Он будет принимать подключения, пока не будет очищена очереди. Если порты становятся доступными, последующий вызов `Listen` или `Accept` будет по возможности повторного заполнения очереди в текущем или последнем «невыполненную работу,» и возобновить прослушивание входящих подключений.

##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket

Содержит дескриптор СОКЕТА для сокета, инкапсулированный этим `CAsyncSocket` объекта.

```
SOCKET m_hSocket;
```

##  <a name="onaccept"></a>  CAsyncSocket::OnAccept

Вызывается платформой для уведомления прослушивающий сокет, который он может принять ожидающих запросов на подключение, вызвав [Accept](#accept) функция-член.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяется к `OnAccept` функция-член:

- **0** функция выполнена успешно.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onclose"></a>  CAsyncSocket::OnClose

Вызывается платформой для уведомления этот сокет о том, что подключенный сокет закрыт соответствующим процессом.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяются к `OnClose` функция-член:

- **0** функция выполнена успешно.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAECONNRESET подключение сброшено удаленной стороной.

- WSAECONNABORTED соединение прервано из-за истечения времени ожидания или другой сбой.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onconnect"></a>  CAsyncSocket::OnConnect

Вызывается платформой для уведомления этого при подключении к сокету, что его соединение закрылось, ли успешно или с ошибкой.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяются к `OnConnect` функция-член:

- **0** функция выполнена успешно.

- WSAEADDRINUSE указанный адрес уже используется.

- WSAEADDRNOTAVAIL указанный адрес не доступен на локальном компьютере.

- WSAEAFNOSUPPORT адреса из заданного семейства не может использоваться с этим сокетом.

- WSAECONNREFUSED попытка подключения была принудительно отклонена.

- Необходим адрес назначения WSAEDESTADDRREQ объект.

- WSAEFAULT *lpSockAddrLen* Неверный аргумент.

- WSAEINVAL сокет уже связан с адресом.

- WSAEISCONN сокет уже подключен.

- WSAEMFILE нет доступных дополнительных дескрипторов файлов.

- WSAENETUNREACH сеть недоступна с этого узла в настоящее время.

- Доступна WSAENOBUFS нет места в буфере. Сокет не подключен.

- WSAENOTCONN сокет не подключен.

- WSAENOTSOCK дескриптор — это файл, а не сокета.

- WSAETIMEDOUT попытка соединения истекло без установления подключения.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  В [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` функции уведомления никогда не вызывается. Для подключений, просто вызовите `Connect`, возвращающий по завершении соединения (успешно или с ошибкой). Как обрабатываются подключения уведомления — это деталь реализации MFC.

Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData

Вызывается платформой для принимающего сокета с отправляющего сокет-каналу данных для отправки уведомления.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяются к `OnOutOfBandData` функция-член:

- **0** функция выполнена успешно.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

### <a name="remarks"></a>Примечания

Каналу данных — это логически независимым канал, который связан с каждой парой подключенных сокетов типа SOCK_STREAM. Канал обычно используется для отправки срочные данные.

MFC поддерживает внешнее данные, но пользователи класса `CAsyncSocket` не рекомендуется использовать его. Простой способ — создать второй сокет для передачи таких данных. Дополнительные сведения о данных из внешнего, см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onreceive"></a>  CAsyncSocket::OnReceive

Вызывается платформой для уведомления этот сокет отсутствия данных в буфере, который можно получить, вызвав `Receive` функция-член.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяются к `OnReceive` функция-член:

- **0** функция выполнена успешно.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

##  <a name="onsend"></a>  CAsyncSocket::OnSend

Вызывается платформой для уведомления сокет о том, что он может отправлять данные путем вызова `Send` функция-член.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nErrorCode*<br/>
Последнюю ошибку сокета. Следующие коды ошибок применяются к `OnSend` функция-член:

- **0** функция выполнена успешно.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

##  <a name="operator_eq"></a>  CAsyncSocket::operator =

Назначает новое значение для `CAsyncSocket` объекта.

```
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Параметры

*rSrc*<br/>
Ссылка на существующий `CAsyncSocket` объекта.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы скопировать существующий `CAsyncSocket` объект с другим объектом `CAsyncSocket` объекта.

##  <a name="operator_socket"></a>  CAsyncSocket::operator СОКЕТА

Этот оператор используется для получения дескриптор СОКЕТА `CAsyncSocket` объекта.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения дескриптор объекта СОКЕТА. в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.

##  <a name="receive"></a>  CAsyncSocket::Receive

Вызов этой функции-члена для получения данных из сокета.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Буфер для входящих данных.

*nBufLen*<br/>
Длина *lpBuf* в байтах.

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_PEEK Просмотр входящих данных. Данные копируются в буфер, но не удаляется из входной очереди.

- Обработка MSG_OOB-каналу данных.

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `Receive` возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAENOTCONN сокет не подключен.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `Receive` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 0 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и `Receive` операция будет заблокирована.

- WSAEMSGSIZE датаграммы слишком велико для помещения в указанный буфер и был усечен.

- Сокет не привязанный к WSAEINVAL `Bind`.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

### <a name="remarks"></a>Примечания

Эта функция используется для подключенного поток или сокеты датаграмм и используется для считывания входящих данных.

Для сокетов типа SOCK_STREAM возвращается столько информации в данный момент доступна до размера размер предоставленного буфера. Если сокет был настроен для приема канала каналу данных (параметр сокета SO_OOBINLINE) и данные из внешнего непрочитанные, будет возвращаться только-каналу данных. Приложение может использовать `IOCtlSIOCATMARK` параметр или [OnOutOfBandData](#onoutofbanddata) для определения, остается ли все более-каналу данных для чтения.

Для сокета датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размера размер предоставленного буфера. Если датаграмма превышает размер предоставленного буфера, буфер заполняется в первой части датаграмма, избыточные данные теряются, и `Receive` возвращает SOCKET_ERROR с кодом ошибки значение WSAEMSGSIZE. Если входящие данные недоступны на сокет, код ошибки: значение WSAEWOULDBLOCK возвращается значение SOCKET_ERROR. [OnReceive](#onreceive) функцию обратного вызова можно использовать для определения, когда приходит больше данных.

Если сокет имеет тип SOCK_STREAM и удаленная сторона завершил работу соединения корректно, `Receive` будет немедленно завершена с получено 0 байт. Если соединение будет сброшено, `Receive` завершится с ошибкой WSAECONNRESET.

`Receive` должен вызываться только один раз для каждого времени [CAsyncSocket::OnReceive](#onreceive) вызывается.

### <a name="example"></a>Пример

  См. в примере [CAsyncSocket::OnReceive](#onreceive).

##  <a name="receivefrom"></a>  CAsyncSocket::ReceiveFrom

Вызов этой функции-члена для получения датаграммы и сохранения исходный адрес в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в *rSocketAddress*.

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

*/ / lpBuf*<br/>
Буфер для входящих данных.

*nBufLen*<br/>
Длина *lpBuf* в байтах.

*rSocketAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rSocketPort*<br/>
Ссылка на целое число без знака, который хранит порт.

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структура, которая содержит адрес источника при возврате.

*lpSockAddrLen*<br/>
Указатель на длину исходный адрес в *lpSockAddr* в байтах.

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_PEEK Просмотр входящих данных. Данные копируются в буфер, но не удаляется из входной очереди.

- Обработка MSG_OOB-каналу данных.

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `ReceiveFrom` возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав `GetLastError`. К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* предоставил недопустимый аргумент: *lpSockAddr* буфер слишком мал, чтобы вместить адрес однорангового узла.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- Сокет не привязанный к WSAEINVAL `Bind`.

- WSAENOTCONN сокет не подключен (SOCK_STREAM).

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `ReceiveFrom` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 0 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и `ReceiveFrom` операция будет заблокирована.

- WSAEMSGSIZE датаграммы слишком велико для помещения в указанный буфер и был усечен.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

### <a name="remarks"></a>Примечания

Эта функция используется для чтения входящие данные на сокет (возможно, подключения) и скопируйте адрес, с которого было отправлено данных.

Для обработки IPv6-адресов, использовать [CAsyncSocket::ReceiveFromEx](#receivefromex).

Для сокетов типа SOCK_STREAM возвращается столько информации в данный момент доступна до размера размер предоставленного буфера. Если сокет был настроен для приема канала каналу данных (параметр сокета SO_OOBINLINE) и данные из внешнего непрочитанные, будет возвращаться только-каналу данных. Приложение может использовать `IOCtlSIOCATMARK` параметр или `OnOutOfBandData` для определения, остается ли все более-каналу данных для чтения. *LpSockAddr* и *lpSockAddrLen* параметры игнорируются для SOCK_STREAM сокетов.

Для сокета датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размера размер предоставленного буфера. Если датаграмма превышает размер предоставленного буфера, буфер заполняется в первой части сообщения, избыточные данные теряются, и `ReceiveFrom` возвращает SOCKET_ERROR с кодом ошибки значение WSAEMSGSIZE.

Если *lpSockAddr* не равно нулю и имеет тип SOCK_DGRAM сокет, сетевой адрес сокета, который отправили в него данные копируются в соответствующие [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на которые указывают *lpSockAddrLen* инициализируется размер этой структуры, а также изменяется при возврате для указания фактического размера адреса, хранящиеся в ней. Если входящие данные недоступны на сокет, `ReceiveFrom` вызов ожидает поступления, если этот сокет данных неблокирующем. В этом случае код ошибки, значение WSAEWOULDBLOCK возвращается значение SOCKET_ERROR. `OnReceive` Обратного вызова можно использовать для определения, когда приходит больше данных.

Если сокет имеет тип SOCK_STREAM и удаленная сторона завершил работу соединения корректно, `ReceiveFrom` будет немедленно завершена с получено 0 байт.

##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx

Вызов этой функции-члена для получения датаграммы и сохранения исходный адрес в [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры или в *rSocketAddress* (обрабатывает IPv6-адресов).

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Буфер для входящих данных.

*nBufLen*<br/>
Длина *lpBuf* в байтах.

*rSocketAddress*<br/>
Ссылка на `CString` объект, получающий точечно число IP-адрес.

*rSocketPort*<br/>
Ссылка на целое число без знака, который хранит порт.

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_PEEK Просмотр входящих данных. Данные копируются в буфер, но не удаляется из входной очереди.

- Обработка MSG_OOB-каналу данных.

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `ReceiveFromEx` возвращает количество полученных байтов. Если соединение было закрыто, она возвращает 0. В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав `GetLastError`. К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpSockAddrLen* предоставил недопустимый аргумент: *lpSockAddr* буфер слишком мал, чтобы вместить адрес однорангового узла.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- Сокет не привязанный к WSAEINVAL `Bind`.

- WSAENOTCONN сокет не подключен (SOCK_STREAM).

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `ReceiveFromEx` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 0 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и `ReceiveFromEx` операция будет заблокирована.

- WSAEMSGSIZE датаграммы слишком велико для помещения в указанный буфер и был усечен.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

### <a name="remarks"></a>Примечания

Эта функция используется для чтения входящие данные на сокет (возможно, подключения) и скопируйте адрес, с которого было отправлено данных.

Эта функция совпадает со значением [CAsyncSocket::ReceiveFrom](#receivefrom) за исключением того, что он обрабатывает IPv6 адреса также, как можно более старые протоколы.

Для сокетов типа SOCK_STREAM возвращается столько информации в данный момент доступна до размера размер предоставленного буфера. Если сокет был настроен для приема канала каналу данных (параметр сокета SO_OOBINLINE) и данные из внешнего непрочитанные, будет возвращаться только-каналу данных. Приложение может использовать `IOCtlSIOCATMARK` параметр или `OnOutOfBandData` для определения, остается ли все более-каналу данных для чтения. *LpSockAddr* и *lpSockAddrLen* параметры игнорируются для SOCK_STREAM сокетов.

Для сокета датаграмм данные извлекаются из первой датаграммы из очереди, вплоть до размера размер предоставленного буфера. Если датаграмма превышает размер предоставленного буфера, буфер заполняется в первой части сообщения, избыточные данные теряются, и `ReceiveFromEx` возвращает SOCKET_ERROR с кодом ошибки значение WSAEMSGSIZE.

Если *lpSockAddr* не равно нулю и имеет тип SOCK_DGRAM сокет, сетевой адрес сокета, который отправили в него данные копируются в соответствующие [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры. Значение, на которые указывают *lpSockAddrLen* инициализируется размер этой структуры, а также изменяется при возврате для указания фактического размера адреса, хранящиеся в ней. Если входящие данные недоступны на сокет, `ReceiveFromEx` вызов ожидает поступления, если этот сокет данных неблокирующем. В этом случае код ошибки, значение WSAEWOULDBLOCK возвращается значение SOCKET_ERROR. `OnReceive` Обратного вызова можно использовать для определения, когда приходит больше данных.

Если сокет имеет тип SOCK_STREAM и удаленная сторона завершил работу соединения корректно, `ReceiveFromEx` будет немедленно завершена с получено 0 байт.

##  <a name="send"></a>  CAsyncSocket::Send

Вызов этой функции-члена для отправки данных на подключенный сокет.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Буфер, содержащий данные для передачи.

*nBufLen*<br/>
Длина данных в *lpBuf* в байтах.

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_DONTROUTE указывает, что данные не должны подчиняться маршрутизации. Можно выбрать поставщика Windows Sockets игнорируют этот флажок.

- Отправить MSG_OOB-каналу данных (SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `Send` возвращает общее число символов, отправленных. (Обратите внимание, что это может быть меньше числа, обозначены *nBufLen*.) В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEACCES запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAEFAULT *lpBuf* аргумент не является допустимой частью адресного пространства пользователя.

- Из-за удаления реализация Windows Sockets, его необходимо сбросить WSAENETRESET соединения.

- Реализация Windows Sockets WSAENOBUFS о взаимоблокировке буфера.

- WSAENOTCONN сокет не подключен.

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `Send` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 1 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и заблокирует запрошенную операцию.

- Имеет тип SOCK_DGRAM WSAEMSGSIZE сокет и датаграмм превышает максимальную длину, поддерживаемую реализация Windows Sockets.

- Сокет не привязанный к WSAEINVAL `Bind`.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

### <a name="remarks"></a>Примечания

`Send` используется для записи выходных данных на подключенном поток или сокеты датаграмм. Для сокета датаграмм, будьте осторожны не должно превышать максимальный размер пакета IP-адрес базовой подсетей, который определяется `iMaxUdpDg` элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структура, возвращенная `AfxSocketInit`. Если данные слишком длинное для прохождения базового протокола атомарным образом, WSAEMSGSIZE возвращается ошибка через `GetLastError`, и данные не передаются.

Обратите внимание, что датаграммы сокета успешного завершения `Send` не означает, что данные был успешно доставлен.

На `CAsyncSocket` объектов типа SOCK_STREAM, число записанных байтов может быть от 1 до запрошенного длину, в зависимости от доступности буфера на локальную и удаленную узлах.

### <a name="example"></a>Пример

  См. в примере [CAsyncSocket::OnSend](#onsend).

##  <a name="sendto"></a>  CAsyncSocket::SendTo

Вызов этой функции-члена для отправки данных в определенное место назначения.

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

*/ / lpBuf*<br/>
Буфер, содержащий данные для передачи.

*nBufLen*<br/>
Длина данных в *lpBuf* в байтах.

*nHostPort*<br/>
Порт, идентифицирующая приложение сокета.

*lpszHostAddress*<br/>
Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная числа, например «128.56.22.8».

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_DONTROUTE указывает, что данные не должны подчиняться маршрутизации. Можно выбрать поставщика Windows Sockets игнорируют этот флажок.

- Отправить MSG_OOB-каналу данных (SOCK_STREAM).

*lpSockAddr*<br/>
Указатель на [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуру, содержащую адрес сокета целевой объект.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `SendTo` возвращает общее число символов, отправленных. (Обратите внимание, что это может быть меньше числа, обозначены *nBufLen*.) В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEACCES запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAEFAULT *lpBuf* или *lpSockAddr* параметров не являются частью адресном пространстве пользователя или *lpSockAddr* аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).

- WSAEINVAL имя узла является недопустимым.

- Из-за удаления реализация Windows Sockets, его необходимо сбросить WSAENETRESET соединения.

- Реализация Windows Sockets WSAENOBUFS о взаимоблокировке буфера.

- WSAENOTCONN сокет не подключен (SOCK_STREAM).

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `SendTo` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 1 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и заблокирует запрошенную операцию.

- Имеет тип SOCK_DGRAM WSAEMSGSIZE сокет и датаграмм превышает максимальную длину, поддерживаемую реализация Windows Sockets.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

- WSAEADDRNOTAVAIL указанный адрес не доступен на локальном компьютере.

- WSAEAFNOSUPPORT адреса из заданного семейства не может использоваться с этим сокетом.

- Необходим адрес назначения WSAEDESTADDRREQ объект.

- WSAENETUNREACH сеть недоступна с этого узла в настоящее время.

### <a name="remarks"></a>Примечания

`SendTo` используется сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокета датаграмм, будьте осторожны не должно превышать максимальный размер пакета IP-адрес базовой подсетей, который определяется `iMaxUdpDg` элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком длинное для прохождения базового протокола атомарным образом, будет возвращена ошибка WSAEMSGSIZE и данные не передаются.

Обратите внимание, что успешное выполнение `SendTo` не означает, что данные был успешно доставлен.

`SendTo` используется только на сокете SOCK_DGRAM Чтобы отправить датаграмму в конкретных сокет, идентифицируемый *lpSockAddr* параметра.

Для отправки широковещательного сообщения (в SOCK_DGRAM только), адрес в *lpSockAddr* параметр должен быть создан с помощью специальный IP-адрес INADDR_BROADCAST (определенных в файле заголовка Windows Sockets WINSOCK. H) вместе с номером нужный порт. Или, если *lpszHostAddress* параметра равно NULL, сокета настроен для широковещательной передачи. Это обычно этом не задействуются широковещательных датаграммы к превышению размера, по которому фрагментации может произойти, что подразумевает, что часть данных датаграмма (за исключением заголовков) не должен превышать 512 байт.

Для обработки IPv6-адресов, использовать [CAsyncSocket::SendToEx](#sendtoex).

##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx

Вызов этой функции-члена для отправки данных в определенное место назначения (маркеры IPv6-адресов).

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Буфер, содержащий данные для передачи.

*nBufLen*<br/>
Длина данных в *lpBuf* в байтах.

*nHostPort*<br/>
Порт, идентифицирующая приложение сокета.

*lpszHostAddress*<br/>
Сетевой адрес сокета, к которому подключен этот объект: имя компьютера, например «ftp.microsoft.com» или пунктирная числа, например «128.56.22.8».

*nFlags*<br/>
Указывает способ, в котором выполняется вызов. Семантика этой функции определяется с помощью параметров сокета и *nFlags* параметра. Последний создается путем объединения любой из следующих значений с C++ **или** оператор:

- MSG_DONTROUTE указывает, что данные не должны подчиняться маршрутизации. Можно выбрать поставщика Windows Sockets игнорируют этот флажок.

- Отправить MSG_OOB-каналу данных (SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

При отсутствии ошибок, `SendToEx` возвращает общее число символов, отправленных. (Обратите внимание, что это может быть меньше числа, обозначены *nBufLen*.) В противном случае возвращается значение SOCKET_ERROR и конкретный код ошибки можно получить, вызвав [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEACCES запрошенный адрес является широковещательным адресом, но не был установлен соответствующий флаг.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAEFAULT *lpBuf* или *lpSockAddr* параметров не являются частью адресном пространстве пользователя или *lpSockAddr* аргумент слишком мал (меньше, чем размер [SOCKADDR](../../mfc/reference/sockaddr-structure.md) структуры).

- WSAEINVAL имя узла является недопустимым.

- Из-за удаления реализация Windows Sockets, его необходимо сбросить WSAENETRESET соединения.

- Реализация Windows Sockets WSAENOBUFS о взаимоблокировке буфера.

- WSAENOTCONN сокет не подключен (SOCK_STREAM).

- WSAENOTSOCK дескриптор не сокета.

- WSAEOPNOTSUPP MSG_OOB был указан, но сокет не относится к типу SOCK_STREAM.

- WSAESHUTDOWN сокет завершает работу; Невозможно вызвать `SendToEx` на сокете после `ShutDown` был вызван с *nHow* присвоено значение 1 или 2.

- WSAEWOULDBLOCK сокет помечается как неблокирующем и заблокирует запрошенную операцию.

- Имеет тип SOCK_DGRAM WSAEMSGSIZE сокет и датаграмм превышает максимальную длину, поддерживаемую реализация Windows Sockets.

- WSAECONNABORTED виртуальный канал была прервана из-за истечения времени ожидания или другой сбой.

- WSAECONNRESET виртуальный канал сброшено удаленной стороной.

- WSAEADDRNOTAVAIL указанный адрес не доступен на локальном компьютере.

- WSAEAFNOSUPPORT адреса из заданного семейства не может использоваться с этим сокетом.

- Необходим адрес назначения WSAEDESTADDRREQ объект.

- WSAENETUNREACH сеть недоступна с этого узла в настоящее время.

### <a name="remarks"></a>Примечания

Этот метод является таким же, как [CAsyncSocket::SendTo](#sendto) за исключением того, что он обрабатывает IPv6 адреса также, как можно более старые протоколы.

`SendToEx` используется сокеты датаграмм или поток и используется для записи выходных данных на сокете. Для сокета датаграмм, будьте осторожны не должно превышать максимальный размер пакета IP-адрес базовой подсетей, который определяется `iMaxUdpDg` элемент в [WSADATA](../../mfc/reference/wsadata-structure.md) структуры для заполнения [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Если данные слишком длинное для прохождения базового протокола атомарным образом, будет возвращена ошибка WSAEMSGSIZE и данные не передаются.

Обратите внимание, что успешное выполнение `SendToEx` не означает, что данные был успешно доставлен.

`SendToEx` используется только на сокете SOCK_DGRAM Чтобы отправить датаграмму в конкретных сокет, идентифицируемый *lpSockAddr* параметра.

Для отправки широковещательного сообщения (в SOCK_DGRAM только), адрес в *lpSockAddr* параметр должен быть создан с помощью специальный IP-адрес INADDR_BROADCAST (определенных в файле заголовка Windows Sockets WINSOCK. H) вместе с номером нужный порт. Или, если *lpszHostAddress* параметра равно NULL, сокета настроен для широковещательной передачи. Это обычно этом не задействуются широковещательных датаграммы к превышению размера, по которому фрагментации может произойти, что подразумевает, что часть данных датаграмма (за исключением заголовков) не должен превышать 512 байт.

##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt

Вызов этой функции-члена для задания параметра сокета.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Параметры

*nOptionName*<br/>
Параметр сокета, для которого будет устанавливаться значение.

*lpOptionValue*<br/>
Указатель на буфер, в котором предоставляется значение запрошенного параметра.

*nOptionLen*<br/>
Размер *lpOptionValue* буфера в байтах.

*nLevel*<br/>
Уровень, по которому параметр определен; только поддерживаемые уровни: SOL_SOCKET и IPPROTO_TCP.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEFAULT *lpOptionValue* не находится в допустимой частью адресного пространства процесса.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAEINVAL *nLevel* является недопустимым, или заполните *lpOptionValue* является недопустимым.

- WSAENETRESET подключения истекло, когда значение SO_KEEPALIVE.

- WSAENOPROTOOPT параметр неизвестен или не поддерживается. В частности SO_BROADCAST сокеты SOCK_STREAM при SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER и SO_OOBINLINE не поддерживаются для сокетов типа SOCK_DGRAM типа не поддерживается.

- WSAENOTCONN соединение будет сброшено при SO_KEEPALIVE имеет значение.

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

`SetSockOpt` Задает текущее значение для параметра сокета, связанные с сокетом любого типа, в любом состоянии. Несмотря на то, что параметры могут существовать на нескольких уровнях протокола, эта спецификация определяет только параметры, которые существуют на уровне верхнего края области «сокетов». Параметры влияют на операции сокета, например срочные данные, получен ли в обычном потоке данных, является ли широковещательных сообщений могут отправляться на сокете и т. д.

Существует два типа параметров сокета: логические параметры, включающие или отключающие определенную функцию или поведение и параметры, которые требуется указать целочисленное значение или структура. Чтобы включить логический параметр, *lpOptionValue* указывает виде ненулевого целого. Чтобы отключить параметр *lpOptionValue* указывает на целое число, равное нулю. *nOptionLen* должен быть равен `sizeof(BOOL)` для логические параметры. Другие варианты *lpOptionValue* указывает на целое число или структура, содержащая нужное значение для параметра и *nOptionLen* длина целое число или структуры.

SO_LINGER определяет действие, выполняемое при имеются неотправленные данные поставлен в очередь на сокете и `Close` функция, вызываемая для закрытия сокета.

По умолчанию не может быть привязан сокет (см. в разделе [привязать](#bind)) локальный адрес, который уже используется. В некоторых случаях тем не менее, она может возникнуть необходимость «повторного использования» адреса таким образом. Так как каждое соединение однозначно идентифицируется сочетание локальных и удаленных адресов, нет никаких проблем с входящим два разъема, привязан к один и тот же локальный адрес, до тех пор, пока удаленного адреса отличаются.

Для информирования реализация Windows Sockets, `Bind` вызов на сокете не должны быть запрещены, так как нужный адрес уже используется другой сокета, приложение должно задать параметр SO_REUSEADDR сокета для сокета перед выдачей `Bind` вызова. Обратите внимание, что параметр интерпретируется только во время `Bind` вызовите: поэтому нет необходимости (но с безопасным) для задания параметра на сокете, который не привязываться к существующего адреса, Установка и сброс параметр после `Bind` вызов не влияет на это или сокету.

Приложение может запрашивать, что реализация Windows Sockets позволяют использовать «-» пакеты проверки активности для подключений протокола управления передачей (TCP), включив параметр сокета SO_KEEPALIVE. Реализация Windows Sockets нужен не поддерживает использование активность: в этом случае точной семантики связаны с конкретной реализацией, но должны соответствовать разделе 4.2.3.6 стандарта RFC 1122: «требования для узлов Интернета — уровнями связи.» При разрыве соединения в результате «активность» код ошибки WSAENETRESET возвращается в любые вызовы выполняется на сокете, и все последующие вызовы будут завершаться WSAENOTCONN.

Параметр TCP_NODELAY отключить алгоритм Nagle. Алгоритм Nagle используется для сокращения числа небольших пакетов, отправляемых узлом буферизация неподтвержденных отправки данных до полного размера пакета может отправляться. Тем не менее для некоторых приложений этот алгоритм может снизить производительность и TCP_NODELAY можно отключить эту функцию. Разработчикам приложений не следует задавать TCP_NODELAY, если это так что оказывает влияние хорошо понятны и нежелательно, так как задание TCP_NODELAY может оказать существенное отрицательное влияние на производительность сети. TCP_NODELAY является единственным поддерживается параметр сокета, которая использует уровня IPPROTO_TCP; все другие параметры могут использоваться уровень SOL_SOCKET.

Некоторые реализации Windows Sockets питания выводить отладочную информацию, если параметр SO_DEBUG устанавливается путем приложения.

Следующие параметры поддерживаются для `SetSockOpt`. Тип указывает тип данных, адресуемый другим *lpOptionValue*.

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Разрешить передачи широковещательных сообщений в сокете.|
|SO_DEBUG|BOOL|Записать отладочную информацию.|
|SO_DONTLINGER|BOOL|Не блокируйте `Close` ожидание неотправленные данные для отправки. Установка этого параметра эквивалентно установке SO_LINGER с `l_onoff` присваивается нулевое значение.|
|SO_DONTROUTE|BOOL|Не направлять: send непосредственно к интерфейсу.|
|SO_KEEPALIVE|BOOL|Отправьте активность.|
|SO_LINGER|`struct LINGER`|Задержка при `Close` Если неотправленные данные отсутствуют.|
|SO_OOBINLINE|BOOL|Получите данные из внешнего в обычном потоке данных.|
|SO_RCVBUF|**int**|Укажите размер буфера для получения.|
|SO_REUSEADDR|BOOL|Разрешить сокет для был привязан к адресу, который уже используется. (См. в разделе [привязать](#bind).)|
|SO_SNDBUF|**int**|Укажите размер буфера для отправки.|
|TCP_NODELAY|BOOL|Отключить алгоритм Nagle для отправки объединенных пакетов.|

Параметры Berkeley Software Distribution (BSD) не поддерживается для `SetSockOpt` являются:

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Сокет прослушивает|
|SO_ERROR|**int**|Получить состояние ошибки и выполнить очистку.|
|SO_RCVLOWAT|**int**|Получите метку низкого уровня.|
|SO_RCVTIMEO|**int**|Время ожидания получения|
|SO_SNDLOWAT|**int**|Отправьте метку низкого уровня.|
|SO_SNDTIMEO|**int**|Отправьте время ожидания.|
|SO_TYPE|**int**|Тип сокета.|
|IP_OPTIONS||Задайте параметры поля в IP-заголовке.|

##  <a name="shutdown"></a>  CAsyncSocket::ShutDown

Получает вызов, чтобы отключить эту функцию-член отправляет, или оба на сокете.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Параметры

*nHow*<br/>
Флаг, который описывает, какие операции не разрешается, с помощью следующих значений:

- **Получает = 0**

- **отправляет = 1**

- **как = 2**

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова [GetLastError](#getlasterror). К этой функции-члена применяются следующие ошибки.

- Объект WSANOTINITIALISED успешно [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) перед использованием этого API.

- Реализация Windows Sockets WSAENETDOWN обнаружил, что подсистема сети произошел сбой.

- WSAEINVAL *nHow* является недопустимым.

- Операция блокировки Windows Sockets WSAEINPROGRESS объект уже выполняется.

- WSAENOTCONN сокет не подключен (SOCK_STREAM).

- WSAENOTSOCK дескриптор не сокета.

### <a name="remarks"></a>Примечания

`ShutDown` используется для всех типов сокетов для отключения приема и передачи. Если *nHow* равно 0, то последующие получил на сокет будет запрещена. Это не влияет на нижних слоев протокола.

Окно TCP для протокола управления передачей (TCP), не изменяются, а входящие данные будут приняты (но не подтверждено), пока не будет исчерпано окна. Для протокола UDP (User Datagram), принимаются и в очередь входящих датаграмм. В любом случае будет создаваться ошибка ICMP-пакет. Если *nHow* -1, последующие отправляет запрещены. Для TCP-сокетами будут отправляться FIN. Установка *nHow* 2 блокирует оба передачу и получение, как описано выше.

Обратите внимание, что `ShutDown` не закрыть сокет и ресурсам, прикрепленным к сокет не будут освобождены до `Close` вызывается. Приложения, не следует полагаться на возможность повторного использования сокет, после завершения работы. В частности, это реализация Windows Sockets не требуется для поддержки использования `Connect` таких сокета.

### <a name="example"></a>Пример

  См. в примере [CAsyncSocket::OnReceive](#onreceive).

##  <a name="socket"></a>  CASyncSocket::Socket

Выделяет дескриптор сокета.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>Параметры

*nSocketType*<br/>
Указывает `SOCK_STREAM` или `SOCK_DGRAM`.

*lEvent*<br/>
Битовая маска, определяющая сочетания событий сети, в которых заинтересовано приложение.

- `FD_READ`: Требуется получать уведомления о готовности для чтения.

- `FD_WRITE`: Требуется получать уведомления о готовности для записи.

- `FD_OOB`: Требуется получать уведомление о появлении-каналу данных.

- `FD_ACCEPT`: Требуется получать уведомления о входящих подключений.

- `FD_CONNECT`: Требуется получение уведомлений завершения подключения.

- `FD_CLOSE`: Требуется получать уведомления о закрытии сокета.

*nProtocolType*<br/>
Протокол, используемый с сокетом, относящиеся к семейству указанный адрес.

*nAddressFormat*<br/>
Адрес спецификации.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `TRUE` в случае успешного выполнения `FALSE` в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод выделяет дескриптор сокета. Он не вызывает [CAsyncSocket::Bind](#bind) для привязывает сокет к указанному адресу, поэтому необходимо вызвать `Bind` более позднюю версию для привязывает сокет к указанному адресу. Можно использовать [CAsyncSocket::SetSockOpt](#setsockopt) для задания параметра сокета, прежде чем он привязан.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
