---
title: Класс CAsyncSocket
ms.date: 09/03/2019
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
ms.openlocfilehash: e384be534bdbb355554c28383e9e214e9084f217
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753027"
---
# <a name="casyncsocket-class"></a>Класс CAsyncSocket

Представляет Windows Socket - конечную точку сетевой коммуникации.

## <a name="syntax"></a>Синтаксис

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Формирует объект `CAsyncSocket`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::Принять](#accept)|Принимает соединение на розетке.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Запрос уведомления о событии для розетки.|
|[CAsyncSocket:Attach](#attach)|Прикрепляет ручку розетки к объекту. `CAsyncSocket`|
|[CAsyncSocket::Bind](#bind)|Связывает местный адрес с розеткой.|
|[CAsyncSocket::Закрыть](#close)|Закрывает розетку.|
|[CAsyncSocket::Connect](#connect)|Устанавливает соединение с одноранговой розеткой.|
|[CAsyncSocket::Create](#create)|Создает розетку.|
|[CAsyncSocket::Detach](#detach)|Отсоединяет ручку `CAsyncSocket` розетки от объекта.|
|[CAsyncSocket::FromHandle](#fromhandle)|Возвращает указатель на `CAsyncSocket` объект, учитывая ручку розетки.|
|[CAsyncSocket::GetLastError](#getlasterror)|Получает состояние ошибки для последней операции, которая не удалась.|
|[CAsyncSocket::GetPeerName](#getpeername)|Получает адрес одноранговой розетки, к которой подключена розетка.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Получает адрес одноранговой розетки, к которой подключена розетка (обрабатывает адреса IPv6).|
|[CAsyncSocket::GetSockName](#getsockname)|Получает местное название для розетки.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Получает локальное название для розетки (обрабатывает адреса IPv6).|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Извлекает опцию розетки.|
|[CAsyncSocket::IOCtl](#ioctl)|Контролирует режим розетки.|
|[CAsyncSocket::Слушай](#listen)|Устанавливает розетку для прослушивания запросов на входящие соединения.|
|[CAsyncSocket::Прием](#receive)|Получает данные из розетки.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Получает грамму данных и хранит исходный адрес.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Получает грамму данных и хранит исходный адрес (обрабатывает адреса IPv6).|
|[CAsyncSocket::Отправить](#send)|Отправляет данные в подключенный сокет.|
|[CAsyncSocket::SendTo](#sendto)|Отправляет данные в определенный пункт назначения.|
|[CAsyncSocket::SendToEx](#sendtoex)|Отправляет данные в определенный пункт назначения (обрабатывает адреса IPv6).|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Устанавливает опцию розетки.|
|[CAsyncSocket::Shutdown](#shutdown)|Отстраняется `Send` от `Receive` разъема и/или вызывает розетку.|
|[CASyncSocket::Socket](#socket)|Выделяет ручку розетки.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::Неприемлемо](#onaccept)|Уведомляет разъем для прослушивания, `Accept`что он может принимать ожидающие запросы на подключение, вызывая .|
|[CAsyncSocket::Закрытие](#onclose)|Уведомляет розетку, что розетка, подключенная к ней, была закрыта.|
|[CAsyncSocket::OnConnect](#onconnect)|Уведомляет разъем подключения о завершении попытки соединения, будь то успешно или по ошибке.|
|[CAsyncSocket::OnoutOfBandData](#onoutofbanddata)|Уведомляет принимающую розетку о том, что на розетке обычно имеется внедиапазоне данных, которые необходимо прочитать, как правило, срочное сообщение.|
|[CAsyncSocket::OnReceive](#onreceive)|Уведомляет прослушиваемую розетку о том, что есть данные, которые необходимо получить, позвонив. `Receive`|
|[CAsyncSocket::OnSend](#onsend)|Уведомляет розетку о том, `Send`что она может отправлять данные, позвонив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::оператор](#operator_eq)|Присваивает объекту `CAsyncSocket` новое значение.|
|[CAsyncSocket::оператор SOCKET](#operator_socket)|Используйте этот оператор для получения ручки `CAsyncSocket` объекта SOCKET.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Указывает на ручку SOCKET, прикрепленную к этому `CAsyncSocket` объекту.|

## <a name="remarks"></a>Remarks

Класс `CAsyncSocket` инкапсулирует API функций Windows, обеспечивая объектно-ориентированную абстракцию для программистов, которые хотят использовать Windows Sockets совместно с MFC.

Этот класс основан на предположении, что вы понимаете сетевые коммуникации. Вы несете ответственность за обработку блокировок, различий в заказе и конверсиях между строками Unicode и набором мультибайт (MBCS). Если вы хотите более удобный интерфейс, который управляет [CSocket](../../mfc/reference/csocket-class.md)этими проблемами для вас, см.

Чтобы использовать `CAsyncSocket` объект, позвоните в его конструктор, а затем позвоните функции `SOCKET` [Create](#create) для создания основной ручки розетки (типа), за исключением принятых розеток. Для серверной розетки вызов функции участника [Listen,](#listen) а для клиента гнездо вызова функции члена [Connect.](#connect) Разъем сервера должен вызвать функцию [Accept](#accept) при получении запроса на подключение. Используйте `CAsyncSocket` оставшиеся функции для выполнения связи между розетками. После завершения, `CAsyncSocket` уничтожить объект, если он был создан на куче; деструктор автоматически вызывает функцию [Close.](#close) Тип данных SOCKET описан в статье [Windows Sockets: Background](../../mfc/windows-sockets-background.md).

> [!NOTE]
> При использовании разъемов MFC во вторичных потоках в `AfxSocketInit` статично связанном приложении MFC необходимо вызвать каждый поток, который использует розетки для инициализации библиотек розетки. По умолчанию, `AfxSocketInit` называется только в основном потоке.

Для получения дополнительной информации [см. Windows Sockets: Использование класса CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) и связанных с ними статей., а также [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

## <a name="casyncsocketaccept"></a><a name="accept"></a>CAsyncSocket::Принять

Вызов ими функции участника, чтобы принять соединение на розетке.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Параметры

*rConnectedSocket*<br/>
Ссылка, идентифицирующая новую розетку, которая доступна для подключения.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) которая получает адрес соединительной розетки, как известно в сети. Точный формат аргумента *lpSockAddr* определяется семейством адресов, установленных при создании розетки. Если *lpSockAddr* и/или *lpSockAddrLen* равны NULL, то никакая информация об удаленном адресе принятой розетки не возвращается.

*lpSockAddrLen*<br/>
Указатель на длину адреса в *lpSockAddr* в байтах. *lpSockAddrLen* является параметром значения результата: он должен первоначально содержать количество пространства, на которое указывает *lpSockAddr;* по возвращении он будет содержать фактическую длину (в байтах) возвращенного адреса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- АРГУМЕНТ WSAEFAULT the *lpSockAddrLen* слишком мал (меньше, чем размер структуры [SOCKADDR).](/windows/win32/winsock/sockaddr-2)

- WSAEINPROGRESS Блокировка Windows Розеты вызова находится в процессе.

- WSAEINVAL `Listen` не был вызван до принятия.

- WSAEMFILE Очередь пуста при входе, чтобы принять и Есть нет дескрипторов доступны.

- WSAENOBUFS Буферное пространство не доступно.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP Ссылка гнездо не является типом, который поддерживает подключение ориентированных службы.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и никаких соединений не присутствует, чтобы быть принятым.

### <a name="remarks"></a>Remarks

Эта рутина извлекает первое соединение в очереди ожидающих соединений, создает новую розетку с теми же свойствами, что и эта розетка, и прикрепляет ее к *rConnectedSocket.* Если в очереди нет ожидающих подключений, `Accept` возвращается ноль и `GetLastError` возвращает ошибку. Принятая розетка *(rConnectedSocket)* не может быть использована для приема большего количества соединений. Оригинальная розетка остается открытой и прослушивание.

Аргумент *lpSockAddr* является параметром результата, который заполняется с адресом соединительной розетки, как известно, суслойка связи. `Accept`используется с типами розетки на основе соединения, такими как SOCK_STREAM.

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a>CAsyncSocket::AsyncSelect

Вызовите эту функцию участника, чтобы запросить уведомление о событии для гнезда.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Параметры

*Levent*<br/>
Битовая маска, которая определяет сочетание сетевых событий, в которых приложение заинтересовано.

- FD_READ Хотите получить уведомление о готовности к чтению.

- FD_WRITE Хотите получать уведомления, когда данные доступны для чтения.

- FD_OOB Хотите получать уведомления о поступлении внедиапазона данных.

- FD_ACCEPT Хотите получать уведомления о входящих соединениях.

- FD_CONNECT Хотите получать уведомления о результатах подключения.

- FD_CLOSE Хотите получать уведомления, когда розетка была закрыта одноранговой.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEINVAL указывает, что один из указанных параметров был недействительным.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

### <a name="remarks"></a>Remarks

Эта функция используется для указания того, какие функции уведомления о вызове MFC будут вызваны для гнезда. `AsyncSelect`автоматически устанавливает эту розетку в режим неблокирования. Для получения дополнительной информации смотрите статью [Windows Sockets: Уведомления о розетке](../../mfc/windows-sockets-socket-notifications.md).

## <a name="casyncsocketattach"></a><a name="attach"></a>CAsyncSocket:Attach

Вызов эту функцию члена, чтобы прикрепить ручку *hSocket* к объекту. `CAsyncSocket`

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит ручку к розетке.

*Levent*<br/>
Битовая маска, которая определяет сочетание сетевых событий, в которых приложение заинтересовано.

- FD_READ Хотите получить уведомление о готовности к чтению.

- FD_WRITE Хотите получать уведомления, когда данные доступны для чтения.

- FD_OOB Хотите получать уведомления о поступлении внедиапазона данных.

- FD_ACCEPT Хотите получать уведомления о входящих соединениях.

- FD_CONNECT Хотите получать уведомления о результатах подключения.

- FD_CLOSE Хотите получать уведомления, когда розетка была закрыта одноранговой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно.

### <a name="remarks"></a>Remarks

Ручка SOCKET хранится в [m_hSocket](#m_hsocket) члена данных объекта.

## <a name="casyncsocketbind"></a><a name="bind"></a>CAsyncSocket::Bind

Вызовите эту функцию участника, чтобы связать локальный адрес с гнездом.

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
Порт, идентифицирующий приложение розетки.

*lpszSocketАдрес*<br/>
Сетевой адрес, пунктирный номер, такой как "128.56.22.8". Прохождение строки NULL для `CAsyncSocket` этого параметра указывает на то, что экземпляр должен прослушивать активность клиента на всех сетевых интерфейсах.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) содержащую адрес для присвоения этой розетки.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). Следующий список охватывает несколько ошибок, которые могут быть возвращены. Для полного списка [см.](/windows/win32/winsock/windows-sockets-error-codes-2)

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEADDRINUSE Указанный адрес уже используется. (См. вариант SO_REUSEADDR розетки под [SetSockOpt](#setsockopt).)

- АРГУМЕНТ WSAEFAULT *аргумент nSockAddrLen* слишком мал (меньше, чем размер структуры [SOCKADDR).](/windows/win32/winsock/sockaddr-2)

- WSAEINPROGRESS Блокировка Windows Розеты вызова находится в процессе.

- WSAEAFNOSUPPORT Указанный адрес семьи не поддерживается этим портом.

- WSAEINVAL Гнездо уже связано с адресом.

- WSAENOBUFS Не хватает буферов, слишком много соединений.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

Эта процедура используется на неподключенной диаграмме данных `Connect` или `Listen` разъеме потока, перед последующим или вызовом. Прежде чем он сможет принимать запросы на подключение, разъем сервера прослушивающего `Bind`сервера должен выбрать номер порта и сделать его известным для Windows Sockets, позвонив. `Bind`устанавливает местную ассоциацию (адрес хозяина/номер порта) гнездо, назначив локальное имя неназванной розетке.

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket

Строит пустой объект розетки.

```
CAsyncSocket();
```

### <a name="remarks"></a>Remarks

После построения объекта необходимо `Create` вызвать функцию его члена, чтобы создать структуру данных SOCKET и связать его адрес. (На стороне сервера связи Windows Sockets, когда прослушивание розетки `Accept` создает гнездо для `Create` использования в вызове, вы не вызываете эту розетку.)

## <a name="casyncsocketclose"></a><a name="close"></a>CAsyncSocket::Закрыть

Закрывает розетку.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Эта функция выпускает разъемыде, так что дальнейшие ссылки на него не удастся с ошибкой WSAENOTSOCK. Если это последняя ссылка на основной разъем, связанная информация именования и данные в очереди отбрасываются. Разрушитель разъема требует `Close` вас.

Для, `CAsyncSocket`но `CSocket`не для , `Close` семантика зависит от вариантов розетки SO_LINGER и SO_DONTLINGER. Для получения дополнительной информации см функции `GetSockOpt`участника .

## <a name="casyncsocketconnect"></a><a name="connect"></a>CAsyncSocket::Connect

Вызовите эту функцию участника, чтобы установить подключение к неподключенной разъему потока или диаграммы данных.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Параметры

*lpszHostАдрес*<br/>
Сетевой адрес розетки, к которому подключен этот объект: название машины, например "ftp.microsoft.com" или пунктирный номер, такой как "128.56.22.8".

*nHostPort*<br/>
Порт, идентифицирующий приложение розетки.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) содержащую адрес подключенной розетки.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). Если это указывает на код ошибки WSAEWOULDBLOCK, а приложение использует переизликие обратных вызовов, приложение получит `OnConnect` сообщение по завершении операции подключения. К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEADDRINUSE Указанный адрес уже используется.

- WSAEINPROGRESS Блокировка Windows Розеты вызова находится в процессе.

- WSAEADDRNOTAVAIL Указанный адрес недоступен из локальной машины.

- WSAEAFNOSUPPORT Адреса в указанном семейство не могут быть использованы с этой розеткой.

- WSAECONNREFUSED Попытка подключения была отклонена.

- WSAEDESTADDRRE- Адрес назначения не требуется.

- WSAEFAULT Аргумент *nSockAddrLen* неверен.

- Адрес хозяина WSAEINVAL.

- WSAEISCONN Розетка уже подключена.

- WSAEMFILE Нет больше дескрипторов файла доступны.

- WSAENETUNREACH Сеть не может быть достигнута от этого узла в настоящее время.

- WSAENOBUFS Буферное пространство не доступно. Розетка не может быть подключена.

- WSAENOTSOCK Дескриптор не розетка.

- WSAETIMEDOUT Попытка подключения приурочена без установления соединения.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующее и соединение не может быть завершено немедленно.

### <a name="remarks"></a>Remarks

Если розетка не связана, система назначает локальной ассоциации уникальные значения, а розетка помечается как связанная. Обратите внимание, что если адресное поле `Connect` структуры имен является нулевым, вернется ноль. Чтобы получить расширенную информацию об ошибке, позвоните в функцию `GetLastError` участника.

Для потоковых розеток (тип SOCK_STREAM) активное соединение инициируется с иностранным хостом. Когда вызов розетки завершается успешно, розетка готова к отправке/приему данных.

Для разъема datagram (тип SOCK_DGRAM) устанавливается пункт назначения `Send` по `Receive` умолчанию, который будет использоваться при последующих и вызовах.

## <a name="casyncsocketcreate"></a><a name="create"></a>CAsyncSocket::Создание

Вызов `Create` функции участника после построения объекта розетки для создания разъема Windows и прикрепите ее.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Параметры

*nSocketPort*<br/>
Известный порт, который будет использоваться с розеткой, или 0, если вы хотите, чтобы Windows Sockets выбрать порт.

*nSocketType*<br/>
SOCK_STREAM или SOCK_DGRAM.

*Levent*<br/>
Битовая маска, которая определяет сочетание сетевых событий, в которых приложение заинтересовано.

- FD_READ Хотите получить уведомление о готовности к чтению.

- FD_WRITE Хотите получить уведомление о готовности к написанию.

- FD_OOB Хотите получать уведомления о поступлении внедиапазона данных.

- FD_ACCEPT Хотите получать уведомления о входящих соединениях.

- FD_CONNECT Хотите получить уведомление о завершении подключения.

- FD_CLOSE Хотите получить уведомление о закрытии розетки.

*lpszSockАдрес*<br/>
Указатель на строку, содержащую сетевой адрес подключенной розетки, пунктирный номер, такой как "128.56.22.8". Прохождение строки NULL для `CAsyncSocket` этого параметра указывает на то, что экземпляр должен прослушивать активность клиента на всех сетевых интерфейсах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEAFNOSUPPORT Указанный адрес семьи не поддерживается.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEMFILE Нет больше дескрипторов файла доступны.

- WSAENOBUFS Буферное пространство не доступно. Разъем не может быть создан.

- WSAEPROTONOSUPPORT Указанный порт не поддерживается.

- WSAEPROTOTYPE Указанный порт является неправильным типом для этой розетки.

- WSAESOCKNoSUPPORT Указанный тип розетки не поддерживается в этом семейство адреса.

### <a name="remarks"></a>Remarks

`Create`вызывает [Socket](#socket) и в случае успеха, он вызывает [Bind](#bind) для того чтобы связать гнездо к указанному адресу. Поддерживаются следующие типы розетки:

- SOCK_STREAM обеспечивает секвенированные, надежные, полнодуплексные, основанные на подключении потоки байт. Использует протокол управления передачей (TCP) для семейства адресов Интернета.

- SOCK_DGRAM поддерживает данные, которые являются неусключаемыми, ненадежными пакетами фиксированной (обычно небольшой) максимальной длины. Использует протокол Datagram пользователя (UDP) для семейства адресов Интернета.

    > [!NOTE]
    >  Функция `Accept` члена берет в качестве параметра ссылку на новый пустой `CSocket` объект. Вы должны построить этот `Accept`объект, прежде чем вы звоните. Имейте в виду, что если этот объект розетки выходит за рамки, соединение закрывается. Не вызывайте `Create` этот новый объект розетки.

> [!IMPORTANT]
> `Create`**не** является безопасным потоком.  Если вы вызываете его в многопоточной среде, где он может вызываться одновременно различными потоками, не забудьте защитить каждый вызов с помощью блокировки mutex или другой блокировки синхронизации.

Для получения дополнительной информации о разъемах для потоковой передачи и диаграммы данных смотрите статьи [Windows Sockets: Background](../../mfc/windows-sockets-background.md) and [Windows Sockets: Ports and Sockets Addresses](../../mfc/windows-sockets-ports-and-socket-addresses.md) и Windows [Sockets 2 API.](/windows/win32/WinSock/windows-sockets-start-page-2)

## <a name="casyncsocketdetach"></a><a name="detach"></a>CAsyncSocket::Detach

Вызовите эту функцию участника, чтобы отсоединить ручку SOCKET в *m_hSocket* членом данных от `CAsyncSocket` объекта и установите *m_hSocket* null.

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a>CAsyncSocket::FromHandle

Возвращает указатель объекту. `CAsyncSocket`

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит ручку к розетке.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CAsyncSocket` объект, или NULL, `CAsyncSocket` если нет объекта, прикрепленного к *hSocket*.

### <a name="remarks"></a>Remarks

При приведении ручки SOCKET, если `CAsyncSocket` объект не прикреплен к ручке, функция участника возвращает NULL.

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a>CAsyncSocket::GetLastError

Вызовите эту функцию участника, чтобы получить статус ошибки для последней операции, которая не удалась.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Возвращаемое значение

Значение возврата указывает на код ошибки для последней процедуры Aockets API Windows, выполняемой этим потоком.

### <a name="remarks"></a>Remarks

Когда функция конкретного члена указывает на `GetLastError` ошибку, следует вызываться для получения соответствующего кода ошибки. Ознакомьтесь с описаниями функций отдельных членов для получения списка применимых кодов ошибок.

Для получения дополнительной информации о [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)кодах ошибок см.

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a>CAsyncSocket::GetPeerName

Вызовите эту функцию участника, чтобы получить адрес одноранговой розетки, к которому подключен этот разъем.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Параметры

*rPeerАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rPeerPort*<br/>
Ссылка на UINT, который хранит порт.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) которая получает название одноранговой розетки.

*lpSockAddrLen*<br/>
Указатель на длину адреса в *lpSockAddr* в байтах. На возвращении, аргумент *lpSockAddrLen* содержит фактический размер *lpSockAddr* возвращенного в байтах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT *аргумент lpSockAddrLen* недостаточно велик.

- WSAEINPROGRESS Блокировка Windows Розеты вызова находится в процессе.

- WSAENOTCONN Розетка не подключена.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

Для обработки адресов IPv6 используйте [CAsyncSocket::GetPeerNameEx](#getpeernameex).

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx

Вызовите эту функцию участника, чтобы получить адрес одноранговой розетки, к которому подключен этот разъем (обрабатывает адреса IPv6).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Параметры

*rPeerАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rPeerPort*<br/>
Ссылка на UINT, который хранит порт.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT *аргумент lpSockAddrLen* недостаточно велик.

- WSAEINPROGRESS Блокировка Windows Розеты вызова находится в процессе.

- WSAENOTCONN Розетка не подключена.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

Эта функция такая же, как [CAsyncSocket::GetPeerName,](#getpeername) за исключением того, что он обрабатывает адреса IPv6, а также старые протоколы.

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a>CAsyncSocket::GetSockName

Вызовите эту функцию участника, чтобы получить локальное название для гнезда.

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Параметры

*rSocketАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rSocketPort*<br/>
Ссылка на UINT, который хранит порт.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) которая получает адрес розетки.

*lpSockAddrLen*<br/>
Указатель на длину адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT *аргумент lpSockAddrLen* недостаточно велик.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEINVAL Гнездо не был связан с `Bind`адресом с .

### <a name="remarks"></a>Remarks

Этот вызов особенно полезен, когда `Connect` вызов `Bind` был сделан без первого; этот вызов предоставляет единственное средство, с помощью которого вы можете определить локальную ассоциацию, которая была установлена системой.

Для обработки адресов IPv6 используйте [CAsyncSocket::GetSockNameEx](#getsocknameex)

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx

Вызовите эту функцию участника, чтобы получить локальное название для гнезда (обрабатывает адреса IPv6).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Параметры

*rSocketАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rSocketPort*<br/>
Ссылка на UINT, который хранит порт.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT *аргумент lpSockAddrLen* недостаточно велик.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEINVAL Гнездо не был связан с `Bind`адресом с .

### <a name="remarks"></a>Remarks

Этот вызов такой же, как [CAsyncSocket::GetSockName,](#getsockname) за исключением того, что он обрабатывает адреса IPv6, а также старые протоколы.

Этот вызов особенно полезен, когда `Connect` вызов `Bind` был сделан без первого; этот вызов предоставляет единственное средство, с помощью которого вы можете определить локальную ассоциацию, которая была установлена системой.

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a>CAsyncSocket::GetSockOpt

Вызов эту функцию участника, чтобы получить опцию розетки.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Параметры

*nOptionName*<br/>
Опция розетки, для которой значение должно быть извлечено.

*lpOptionValue*<br/>
Указатель на буфер, в котором должно быть возвращено значение запрашиваемого параметра. Значение, связанное с выбранным вариантом, возвращается в буфер *lpOptionValue.* Цель, на которую указывает *lpOptionLen,* должна первоначально содержать размер этого буфера в байтах; и по возвращении он будет установлен на размер возвращенного значения. Для SO_LINGER это будет размер `LINGER` структуры; для всех других вариантов это будет размер BOOL или **Int**, в зависимости от опции. Список опций и их размеров смотрите в разделе Замечания.

*lpOptionLen*<br/>
Указатель на размер буфера *lpOptionValue* в байтах.

*nУровень*<br/>
Уровень, на котором определен опцион; единственными поддерживаемыми уровнями являются SOL_SOCKET и IPPROTO_TCP.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). Если опцион никогда `SetSockOpt`не `GetSockOpt` был установлен с, то возвращает значение по умолчанию для опциона. К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT Аргумент *lpOptionLen* был недействительным.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOPROTOOPT Опция неизвестна или не поддерживается. В частности, SO_BROADCAST не поддерживается на разъемах SOCK_STREAM типа, а SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER и SO_OOBINLINE не поддерживаются на розетках типа SOCK_DGRAM.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

`GetSockOpt`получает текущее значение для разъема, связанного с розеткой любого типа, в любом состоянии, и хранит результат в *lpOptionValue.* Параметры влияют на операции розетки, такие как разгром пакетов, передача данных вне диапазона и так далее.

Следующие варианты `GetSockOpt`поддерживаются для . Тип определяет тип данных, адресованных *lpOptionValue.* В TCP_NODELAY опции используется IPPROTO_TCP уровня; все другие варианты использования уровня SOL_SOCKET.

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Розетка слушает.|
|SO_BROADCAST|BOOL|Розетка настроена для передачи вещательных сообщений.|
|SO_DEBUG|BOOL|Дибагинг включен.|
|SO_DONTLINGER|BOOL|Если это так, то SO_LINGER опция отключена.|
|SO_DONTROUTE|BOOL|Реутовство отключено.|
|SO_ERROR|**int**|Восстановить состояние ошибки и очистить.|
|SO_KEEPALIVE|BOOL|Продолжаются жизни.|
|SO_LINGER|`struct LINGER`|Возвращает текущие параметры задерживающегося.|
|SO_OOBINLINE|BOOL|Внедиапазонные данные поступают в обычном потоке данных.|
|SO_RCVBUF|INT|Размер буфера для получения.|
|SO_REUSEADDR|BOOL|Розетка может быть привязана к адресу, который уже используется.|
|So_sndbuf|**int**|Размер буфера для отправки.|
|SO_TYPE|**int**|Тип розетки (например, SOCK_STREAM).|
|TCP_NODELAY|BOOL|Отключить алгоритм Nagle для отправки объединенных пакетов.|

Параметры Berkeley Software Distribution (BSD) не `GetSockOpt` поддерживаются:

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Получайте низкую отметку воды.|
|SO_RCVTIMEO|**int**|Получение тайм-аута.|
|SO_SNDLOWAT|**int**|Отправить низкий знак воды.|
|SO_SNDTIMEO|**int**|Отправить тайм-аут.|
|IP_OPTIONS||Получите опции в заголовке IP.|
|TCP_MAXSEG|**int**|Получите максимальный размер сегмента TCP.|

Вызов `GetSockOpt` с неподдерживаемой опцией приведет к возвращению из `GetLastError`кода ошибки WSAENOPROTOOPT.

## <a name="casyncsocketioctl"></a><a name="ioctl"></a>CAsyncSocket::IOCtl

Вызов этой функции элемента для управления режимом розетки.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Параметры

*lКоманда*<br/>
Команда для выполнения на розетке.

*lpАргумент*<br/>
Указатель на параметр для *lCommand*.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEINVAL *lCommand* не является действительной командой, или *lpArgument* не является приемлемым параметром для *lCommand,* или команда не применима к типу поставляемой розетки.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

Эта процедура может быть использована на любой розетке в любом состоянии. Он используется для получения или извлечения операционных параметров, связанных с розеткой, независимо от протокола и подсистемы связи. Поддерживаются следующие команды:

- FIONBIO Включить или отключить режим неблокировки на розетке. Параметр *lpArgument* указывает `DWORD`на , который является ненулевым, если режим неблокировки должен быть включен и ноль, если он должен быть отключен. Если `AsyncSelect` был выпущен на розетке, то `IOCtl` любая попытка использовать для установки розетки обратно в режим блокировки не увенчается неудачей с WSAEINVAL. Чтобы настроить розетку обратно в режим блокировки и предотвратить ошибку WSAEINVAL, приложение должно сначала `AsyncSelect` отключить, позвонив `AsyncSelect` с параметром *lEvent,* равным 0, а затем вызвать. `IOCtl`

- FIONREAD Определите максимальное количество байтов, `Receive` которые можно прочитать с помощью одного звонка из этой розетки. Параметр *lpArgument* указывает `DWORD` на `IOCtl` то, в котором хранится результат. Если эта розетка имеет тип SOCK_STREAM, FIONREAD возвращает общий объем `Receive`данных, которые можно прочитать в одном; это обычно то же самое, что и общее количество данных, выложено в очередь на розетке. Если эта розетка имеет тип SOCK_DGRAM, FIONREAD возвращает размер первой грамма данных в очереди на розетке.

- SIOCATMARK Определите, были ли прочитаны все внеполосные данные. Это относится только к розетке типа SOCK_STREAM которая была настроена для встроенного приема любых внедиапазонных данных (SO_OOBINLINE). Если не ожидайте чтения внедиапазонных данных, операция возвращается ненулево. В противном случае он `Receive` `ReceiveFrom` возвращает 0, а следующий или выполненный на гнезде получит часть или все данные, предшествующие "знаку"; приложение должно использовать операцию SIOCATMARK для определения того, остаются ли какие-либо данные. Если есть какие-либо нормальные данные, предшествующие "срочным" (вне диапазона) данных, он будет получен в порядке. (Обратите внимание, что `Receive` или `ReceiveFrom` никогда не будет смешивать вне диапазона и нормальные данные в том же вызове.) Параметр *lpArgument* указывает `DWORD` на `IOCtl` то, в котором хранится результат.

Эта функция представляет собой `ioctl()` подмножество, используемое в разъемах Berkeley. В частности, нет команды, эквивалентной FIOASYNC, в то время как SIOCATMARK является единственной командой уровня розетки, которая поддерживается.

## <a name="casyncsocketlisten"></a><a name="listen"></a>CAsyncSocket::Слушай

Вызовите эту функцию участника для прослушивания запросов на входящие соединения.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Параметры

*nConnectionBacklog*<br/>
Максимальная продолжительность, до которой может увеличиваться очередь ожидающих соединения. Допустимый диапазон составляет от 1 до 5.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEADDRINUSE Попытка прослушивания по адресу в использовании.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEINVAL Гнездо не было связано с `Bind` или уже подключено.

- WSAEISCONN Розетка уже подключена.

- WSAEMFILE Нет больше дескрипторов файла доступны.

- WSAENOBUFS Буферное пространство не доступно.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP Ссылка гнездо не типа, который `Listen` поддерживает операцию.

### <a name="remarks"></a>Remarks

Для принятия соединений, розетка `Create`сначала создается с , отставание `Listen`для входящих соединений указывается с , а затем соединения принимаются с `Accept`. `Listen`применяется только к розетам, поддерживающим соединения, т.е. к SOCK_STREAM типа. Эта розетка переведена в "пассивный" режим, когда входящие соединения признаются и стоят в очереди в ожидании принятия процессом.

Эта функция обычно используется серверами (или любым приложением, которое хочет принимать соединения), которые могут иметь более одного запроса на подключение одновременно: если запрос на подключение поступает с полной очередью, клиент получит ошибку с указанием WSAECONNREFUSED.

`Listen`попытки продолжать рационально функционировать, когда нет доступных портов (дескрипторов). Он будет принимать соединения до тех пор, пока очередь не опустеет. Если порты становятся `Listen` доступными, более поздний вызов или `Accept` пополнение очереди в текущую или самую недавнюю «запор», если это возможно, и возобновить прослушивание входящих соединений.

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a>CAsyncSocket::m_hSocket

Содержит ручку SOCKET для розетки, `CAsyncSocket` инкапсулированной этим объектом.

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a>CAsyncSocket::Неприемлемо

Вызывается в рамках, чтобы уведомить прослушивающий гнездо, что он может принимать ожидающие запросы соединения, вызывая функцию участника [Accept.](#accept)

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnAccept` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../../mfc/windows-sockets-socket-notifications.md)

## <a name="casyncsocketonclose"></a><a name="onclose"></a>CAsyncSocket::Закрытие

Вызывается фреймворком, чтобы уведомить эту розетку о том, что подключенная розетка закрывается своим процессом.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnClose` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAECONNRESET Соединение было сбросить с удаленной стороны.

- WSAECONNABORTED Соединение было прервано из-за тайм-аута или другого сбоя.

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../../mfc/windows-sockets-socket-notifications.md)

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a>CAsyncSocket::OnConnect

Вызывается фрекингом, чтобы уведомить эту разъем для подключения о том, что попытка подключения завершена, будь то успешно или по ошибке.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnConnect` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAEADDRINUSE Указанный адрес уже используется.

- WSAEADDRNOTAVAIL Указанный адрес недоступен из локальной машины.

- WSAEAFNOSUPPORT Адреса в указанном семейство не могут быть использованы с этой розеткой.

- WSAECONNREFUSED Попытка подключения была решительно отвергнута.

- WSAEDESTADDRRE- Адрес назначения не требуется.

- WSAEFAULT Аргумент *lpSockAddrLen* неверен.

- WSAEINVAL Гнездо уже связано с адресом.

- WSAEISCONN Розетка уже подключена.

- WSAEMFILE Нет больше дескрипторов файла доступны.

- WSAENETUNREACH Сеть не может быть достигнута от этого узла в настоящее время.

- WSAENOBUFS Буферное пространство не доступно. Розетка не может быть подключена.

- WSAENOTCONN Розетка не подключена.

- WSAENOTSOCK Дескриптор файл, а не розетка.

- WSAETIMEDOUT Попытка подключения приурочена без установления подключения.

### <a name="remarks"></a>Remarks

> [!NOTE]
> В [CSocket](../../mfc/reference/csocket-class.md) `OnConnect` функция уведомления никогда не вызывается. Для подключений `Connect`вы просто звоните, который будет возвращаться, когда соединение будет завершено (успешно или по ошибке). Обработка уведомлений о подключении — это деталь реализации MFC.

Для получения дополнительной [информации см.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a>CAsyncSocket::OnoutOfBandData

Вызывается по системе, чтобы уведомить принимающей розетку, что отправка гнездо имеет вне диапазона данных для отправки.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnOutOfBandData` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

### <a name="remarks"></a>Remarks

Внеполосные данные — это логически независимый канал, связанный с каждой парой подключенных розеток типа SOCK_STREAM. Канал обычно используется для отправки срочных данных.

MFC поддерживает внедиапазоне данных, `CAsyncSocket` но пользователям класса не рекомендуется их использовать. Более простой способ заключается в создании второй розетки для передачи таких данных. Для получения дополнительной информации о внеполосных данных, см [Windows Розетки: Уведомления розетки](../../mfc/windows-sockets-socket-notifications.md).

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a>CAsyncSocket::OnReceive

Вызывается фреймворком, чтобы уведомить эту розетку о наличии `Receive` данных в буфере, которые можно получить, позвонив в функцию члена.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnReceive` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a>CAsyncSocket::OnSend

Вызывается по системе, чтобы уведомить гнездо, что `Send` теперь он может отправлять данные, вызывая функцию участника.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Параметры

*nОшибкаКод*<br/>
Последняя ошибка на розетке. Следующие коды ошибок `OnSend` применяются к функции участника:

- **0** Функция выполнена успешно.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a>CAsyncSocket::оператор

Присваивает объекту `CAsyncSocket` новое значение.

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Параметры

*Rsrc*<br/>
Ссылка на `CAsyncSocket` существующий объект.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы скопировать существующий `CAsyncSocket` объект на другой `CAsyncSocket` объект.

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a>CAsyncSocket::оператор SOCKET

Используйте этот оператор для получения ручки `CAsyncSocket` объекта SOCKET.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка объекта SOCKET; в противном случае, NULL.

### <a name="remarks"></a>Remarks

Ручку можно использовать для прямого вызова AA Windows.

## <a name="casyncsocketreceive"></a><a name="receive"></a>CAsyncSocket::Прием

Вызовите эту функцию участника для получения данных из розетки.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Буфер для входящих данных.

*nБуфЛен*<br/>
Длина *lpBuf* в байтах.

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_PEEK Peek на входящие данные. Данные копируется в буфер, но не удаляются из входного ввода.

- MSG_OOB процесс вне диапазона данных.

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `Receive` не происходит, возвращает количество полученных байтов. Если соединение было закрыто, оно возвращает 0. В противном случае значение SOCKET_ERROR возвращается, и определенный код ошибки может быть извлечен, позвонив [в GetLastError.](#getlasterror) К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAENOTCONN Розетка не подключена.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `Receive` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 0 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и `Receive` операция будет блокироваться.

- WSAEMSGSize Грамма данных была слишком большой, чтобы поместиться в указанный буфер и была усечена.

- WSAEINVAL Гнездо не был связан `Bind`с .

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

### <a name="remarks"></a>Remarks

Эта функция используется для подключенных разъемов потока или диаграмм данных и используется для чтения входящих данных.

Для розетки типа SOCK_STREAM возвращается как можно больше информации, которая доступна в настоящее время до размера поставляемого буфера. Если розетка была настроена для встроенного приема внедиапазонных данных (опция SO_OOBINLINE) и внеполосные данные непрочитаны, будут возвращены только внеполосные данные. Приложение может использовать `IOCtlSIOCATMARK` опцию или [OnOutOfBandData,](#onoutofbanddata) чтобы определить, есть ли еще вне диапазона данных еще предстоит прочитать.

Для разъемов datagram данные извлекаются из первой облепихированной грамма данных, вплоть до размера поставляемого буфера. Если грамма данных больше, чем поставляемый буфер, буфер заполняется первой частью диаграммы данных, избыточные данные теряются и `Receive` возвращает значение SOCKET_ERROR с набором кода ошибки в WSAEMSGSize. Если в розетке нет входящих данных, значение SOCKET_ERROR возвращается с набором кода ошибки wsAEWOULDBLOCK. Функция обратного вызова [OnReceive](#onreceive) может быть использована для определения того, когда поступает больше данных.

Если розетка типа SOCK_STREAM и удаленная сторона выключила соединение `Receive` грациозно, будет завершить сразу с 0 байтов получил. Если соединение было сдем, `Receive` сбой будет сбой с ошибкой WSAECONNRESET.

`Receive`должны быть вызваны только один раз для каждого времени [CAsyncSocket::OnReceive](#onreceive) вызывается.

### <a name="example"></a>Пример

  Смотрите пример [для CAsyncSocket::OnReceive](#onreceive).

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a>CAsyncSocket::ReceiveFrom

Позвоните этой функции участника, чтобы получить грамм данных и сохранить исходный адрес в структуре [SOCKADDR](/windows/win32/winsock/sockaddr-2) или в *rSocketAddress.*

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

*lpBuf*<br/>
Буфер для входящих данных.

*nБуфЛен*<br/>
Длина *lpBuf* в байтах.

*rSocketАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rSocketPort*<br/>
Ссылка на UINT, который хранит порт.

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) которая содержит исходный адрес по возвращении.

*lpSockAddrLen*<br/>
Указатель на длину исходного адреса в *lpSockAddr* в байтах.

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_PEEK Peek на входящие данные. Данные копируется в буфер, но не удаляются из входного ввода.

- MSG_OOB процесс вне диапазона данных.

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `ReceiveFrom` не происходит, возвращает количество полученных байтов. Если соединение было закрыто, оно возвращает 0. В противном случае значение SOCKET_ERROR возвращается, и определенный `GetLastError`код ошибки может быть извлечен путем вызова . К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- АРГУМЕНТ WSAEFAULT the *lpSockAddrLen* был недействительным: буфер *lpSockAddr* был слишком мал, чтобы вместить одноранговый адрес.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEINVAL Гнездо не был связан `Bind`с .

- WSAENOTCONN Розетка не подключена (только SOCK_STREAM).

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `ReceiveFrom` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 0 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и `ReceiveFrom` операция будет блокироваться.

- WSAEMSGSize Грамма данных была слишком большой, чтобы поместиться в указанный буфер и была усечена.

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

### <a name="remarks"></a>Remarks

Эта функция используется для чтения входящих данных на (возможно, подключенном) гнезде и захвата адреса, с которого были отправлены данные.

Для обработки адресов IPv6 используйте [CAsyncSocket::ReceiveFromEx](#receivefromex).

Для розетки типа SOCK_STREAM возвращается как можно больше информации, которая доступна в настоящее время до размера поставляемого буфера. Если розетка была настроена для встроенного приема внедиапазонных данных (опция SO_OOBINLINE) и внеполосные данные непрочитаны, будут возвращены только внеполосные данные. Приложение может использовать `IOCtlSIOCATMARK` опцию или `OnOutOfBandData` определить, нужно ли читать какие-либо дополнительные внеполосные данные. Параметры *lpSockAddr* и *lpSockAddrLen* игнорируются для SOCK_STREAM розеток.

Для разъемов datagram данные извлекаются из первой облепихированной грамма данных, вплоть до размера поставляемого буфера. Если грамма данных больше, чем поставляемый буфер, буфер заполняется первой частью `ReceiveFrom` сообщения, избыточные данные теряются и возвращает значение SOCKET_ERROR с набором кода ошибки в WSAEMSGSize.

Если *lpSockAddr* незеро, а розетка типа SOCK_DGRAM, сетевой адрес гнезда, который послал данные, скопируется в соответствующую структуру [SOCKADDR.](/windows/win32/winsock/sockaddr-2) Значение, на что указывает *lpSockAddrLen,* инициируется по размеру этой структуры и изменяется по возвращении, чтобы указать фактический размер сохраненного там адреса. Если в розетке нет входящих `ReceiveFrom` данных, вызов ждет прибытия данных, если розетка не блокируется. В этом случае значение SOCKET_ERROR возвращается с кодом ошибки, установленным на WSAEWOULDBLOCK. Обратный `OnReceive` вызов может быть использован для определения того, когда поступает больше данных.

Если розетка типа SOCK_STREAM и удаленная сторона выключила соединение `ReceiveFrom` грациозно, будет завершить сразу с 0 байтов получил.

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx

Позвоните этой функции участника, чтобы получить грамм данных и сохранить исходный адрес в структуре [SOCKADDR](/windows/win32/winsock/sockaddr-2) или в *rSocketAddress* (обрабатывает адреса IPv6).

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Буфер для входящих данных.

*nБуфЛен*<br/>
Длина *lpBuf* в байтах.

*rSocketАдрес*<br/>
Ссылка `CString` на объект, который получает IP-адрес пунктирного номера.

*rSocketPort*<br/>
Ссылка на UINT, который хранит порт.

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_PEEK Peek на входящие данные. Данные копируется в буфер, но не удаляются из входного ввода.

- MSG_OOB процесс вне диапазона данных.

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `ReceiveFromEx` не происходит, возвращает количество полученных байтов. Если соединение было закрыто, оно возвращает 0. В противном случае значение SOCKET_ERROR возвращается, и определенный `GetLastError`код ошибки может быть извлечен путем вызова . К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- АРГУМЕНТ WSAEFAULT the *lpSockAddrLen* был недействительным: буфер *lpSockAddr* был слишком мал, чтобы вместить одноранговый адрес.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEINVAL Гнездо не был связан `Bind`с .

- WSAENOTCONN Розетка не подключена (только SOCK_STREAM).

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `ReceiveFromEx` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 0 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и `ReceiveFromEx` операция будет блокироваться.

- WSAEMSGSize Грамма данных была слишком большой, чтобы поместиться в указанный буфер и была усечена.

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

### <a name="remarks"></a>Remarks

Эта функция используется для чтения входящих данных на (возможно, подключенном) гнезде и захвата адреса, с которого были отправлены данные.

Эта функция такая же, как [CAsyncSocket::ReceiveFrom,](#receivefrom) за исключением того, что он обрабатывает адреса IPv6, а также старые протоколы.

Для розетки типа SOCK_STREAM возвращается как можно больше информации, которая доступна в настоящее время до размера поставляемого буфера. Если розетка была настроена для встроенного приема внедиапазонных данных (опция SO_OOBINLINE) и внеполосные данные непрочитаны, будут возвращены только внеполосные данные. Приложение может использовать `IOCtlSIOCATMARK` опцию или `OnOutOfBandData` определить, нужно ли читать какие-либо дополнительные внеполосные данные. Параметры *lpSockAddr* и *lpSockAddrLen* игнорируются для SOCK_STREAM розеток.

Для разъемов datagram данные извлекаются из первой облепихированной грамма данных, вплоть до размера поставляемого буфера. Если грамма данных больше, чем поставляемый буфер, буфер заполняется первой частью `ReceiveFromEx` сообщения, избыточные данные теряются и возвращает значение SOCKET_ERROR с набором кода ошибки в WSAEMSGSize.

Если *lpSockAddr* незеро, а розетка типа SOCK_DGRAM, сетевой адрес гнезда, который послал данные, скопируется в соответствующую структуру [SOCKADDR.](/windows/win32/winsock/sockaddr-2) Значение, на что указывает *lpSockAddrLen,* инициируется по размеру этой структуры и изменяется по возвращении, чтобы указать фактический размер сохраненного там адреса. Если в розетке нет входящих `ReceiveFromEx` данных, вызов ждет прибытия данных, если розетка не блокируется. В этом случае значение SOCKET_ERROR возвращается с кодом ошибки, установленным на WSAEWOULDBLOCK. Обратный `OnReceive` вызов может быть использован для определения того, когда поступает больше данных.

Если розетка типа SOCK_STREAM и удаленная сторона выключила соединение `ReceiveFromEx` грациозно, будет завершить сразу с 0 байтов получил.

## <a name="casyncsocketsend"></a><a name="send"></a>CAsyncSocket::Отправить

Вызов эту функцию участника для отправки данных на подключенной розетке.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Буфер, содержащий данные, которые будут переданы.

*nБуфЛен*<br/>
Длина данных в *lpBuf* в байтах.

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_DONTROUTE указывает, что данные не должны подлежать реанимировке. Поставщик Windows Sockets может игнорировать этот флаг.

- MSG_OOB Отправить вне диапазона данных (только SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `Send` не происходит, возвращаетобщее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем число, указанное *nBufLen*.) В противном случае значение SOCKET_ERROR возвращается, и определенный код ошибки может быть извлечен, позвонив [в GetLastError.](#getlasterror) К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEACCES Запрошенный адрес является адресом трансляции, но соответствующий флаг не был установлен.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEFAULT Аргумент *lpBuf* не находится в действительной части пространства адреса пользователя.

- WSAENETRESET Соединение должно быть сброшено, потому что реализация Windows Sockets отбросила его.

- WSAENOBUFS Реализация Windows Sockets сообщает о буферном тупике.

- WSAENOTCONN Розетка не подключена.

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `Send` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 1 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и запрашиваемый операция будет блокировать.

- WSAEMSGSIZE Разъем типа SOCK_DGRAM, а грамма данных больше, чем максимальная, поддерживаемая реализацией Windows Sockets.

- WSAEINVAL Гнездо не был связан `Bind`с .

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

### <a name="remarks"></a>Remarks

`Send`используется для записи исходящих данных на подключенных разъемах потока или данных. Для разъемов datagram необходимо позаботиться о том, чтобы не превышать максимальный размер `iMaxUdpDg` IP-пакета базовых подсетей, который дается элементом в структуре [WSADATA,](/windows/win32/api/winsock2/ns-winsock2-wsadata) возвращенным `AfxSocketInit`. Если данные слишком долго, чтобы передаваться по базовому протоколу, ошибка `GetLastError`WSAEMSGSize возвращается через , и никакие данные не передаются.

Обратите внимание, что для разъема `Send` datagram успешное завершение аненеснезирует, что данные были успешно доставлены.

На `CAsyncSocket` объектах типа SOCK_STREAM количество написанных байтов может быть между 1 и запрошенной длиной, в зависимости от наличия буфера как на местных, так и на иностранных хостах.

### <a name="example"></a>Пример

  Смотрите пример [для CAsyncSocket::OnSend](#onsend).

## <a name="casyncsocketsendto"></a><a name="sendto"></a>CAsyncSocket::SendTo

Вызовите эту функцию участника для отправки данных в определенный пункт назначения.

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

*lpBuf*<br/>
Буфер, содержащий данные, которые будут переданы.

*nБуфЛен*<br/>
Длина данных в *lpBuf* в байтах.

*nHostPort*<br/>
Порт, идентифицирующий приложение розетки.

*lpszHostАдрес*<br/>
Сетевой адрес розетки, к которому подключен этот объект: название машины, такое как "ftp.microsoft.com" или пунктирный номер, такой как "128.56.22.8".

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_DONTROUTE указывает, что данные не должны подлежать реанимировке. Поставщик Windows Sockets может игнорировать этот флаг.

- MSG_OOB Отправить вне диапазона данных (только SOCK_STREAM).

*lpSockAddr*<br/>
Указатель на структуру [SOCKADDR,](/windows/win32/winsock/sockaddr-2) содержащую адрес целевой розетки.

*nSockAddrLen*<br/>
Длина адреса в *lpSockAddr* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `SendTo` не происходит, возвращаетобщее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем число, указанное *nBufLen*.) В противном случае значение SOCKET_ERROR возвращается, и определенный код ошибки может быть извлечен, позвонив [в GetLastError.](#getlasterror) К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEACCES Запрошенный адрес является адресом трансляции, но соответствующий флаг не был установлен.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- ПАРАМЕТРЫ WSAEFAULT *lpBuf* или *lpSockAddr* не являются частью пространства адреса пользователя, или аргумент *lpSockAddr* слишком мал (меньше, чем размер структуры [SOCKADDR).](/windows/win32/winsock/sockaddr-2)

- WSAEINVAL Имя хозяина является недействительным.

- WSAENETRESET Соединение должно быть сброшено, потому что реализация Windows Sockets отбросила его.

- WSAENOBUFS Реализация Windows Sockets сообщает о буферном тупике.

- WSAENOTCONN Розетка не подключена (только SOCK_STREAM).

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `SendTo` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 1 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и запрашиваемый операция будет блокировать.

- WSAEMSGSIZE Разъем типа SOCK_DGRAM, а грамма данных больше, чем максимальная, поддерживаемая реализацией Windows Sockets.

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

- WSAEADDRNOTAVAIL Указанный адрес недоступен из локальной машины.

- WSAEAFNOSUPPORT Адреса в указанном семейство не могут быть использованы с этой розеткой.

- WSAEDESTADDRRE- Адрес назначения не требуется.

- WSAENETUNREACH Сеть не может быть достигнута от этого узла в настоящее время.

### <a name="remarks"></a>Remarks

`SendTo`используется на разъемах Datagram или stream и используется для записи исходящих данных на розетке. Для разъемов datagram необходимо позаботиться о том, чтобы не превышать максимальный размер `iMaxUdpDg` IP-пакета базовых подсетей, который дается элементом в структуре [WSADATA,](/windows/win32/api/winsock2/ns-winsock2-wsadata) заполненным [AfxSocketInit.](../../mfc/reference/application-information-and-management.md#afxsocketinit) Если данные слишком долго передаются через базовый протокол, ошибка WSAEMSGSize возвращается, и данные не передаются.

Обратите внимание, что `SendTo` успешное завершение а. не указывает на успешное доставление данных.

`SendTo`используется только на SOCK_DGRAM гнезде для отправки грамма данных в определенный разъем, определенный параметром *lpSockAddr.*

Для отправки трансляции (только на SOCK_DGRAM) адрес в параметре *lpSockAddr* должен быть построен с помощью специального IP-адреса INADDR_BROADCAST (определяется в файле заголовка Windows Sockets WINSOCK. H) вместе с предполагаемым номером порта. Или, если параметр *lpszHostAddress* null, розетка настроена для трансляции. Как правило, нецелесообразно, чтобы диаграмма вещания превышала размер, при котором может происходить фрагментация, что означает, что часть данных Datagram (за исключением заголовков) не должна превышать 512 байт.

Для обработки адресов IPv6 используйте [CAsyncSocket::SendToEx](#sendtoex).

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a>CAsyncSocket::SendToEx

Вызовите эту функцию участника для отправки данных в определенный пункт назначения (обрабатывает адреса IPv6).

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Буфер, содержащий данные, которые будут переданы.

*nБуфЛен*<br/>
Длина данных в *lpBuf* в байтах.

*nHostPort*<br/>
Порт, идентифицирующий приложение розетки.

*lpszHostАдрес*<br/>
Сетевой адрес розетки, к которому подключен этот объект: название машины, такое как "ftp.microsoft.com" или пунктирный номер, такой как "128.56.22.8".

*nФлаги*<br/>
Определяет способ, в котором делается вызов. Семантика этой функции определяется параметрами розетки и параметром *nFlags.* Последнее построено путем объединения любого из следующих значений с оператором **C-OR:**

- MSG_DONTROUTE указывает, что данные не должны подлежать реанимировке. Поставщик Windows Sockets может игнорировать этот флаг.

- MSG_OOB Отправить вне диапазона данных (только SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

Если ошибки `SendToEx` не происходит, возвращаетобщее количество отправленных символов. (Обратите внимание, что это может быть меньше, чем число, указанное *nBufLen*.) В противном случае значение SOCKET_ERROR возвращается, и определенный код ошибки может быть извлечен, позвонив [в GetLastError.](#getlasterror) К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEACCES Запрошенный адрес является адресом трансляции, но соответствующий флаг не был установлен.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- ПАРАМЕТРЫ WSAEFAULT *lpBuf* или *lpSockAddr* не являются частью пространства адреса пользователя, или аргумент *lpSockAddr* слишком мал (меньше, чем размер структуры [SOCKADDR).](/windows/win32/winsock/sockaddr-2)

- WSAEINVAL Имя хозяина является недействительным.

- WSAENETRESET Соединение должно быть сброшено, потому что реализация Windows Sockets отбросила его.

- WSAENOBUFS Реализация Windows Sockets сообщает о буферном тупике.

- WSAENOTCONN Розетка не подключена (только SOCK_STREAM).

- WSAENOTSOCK Дескриптор не розетка.

- WSAEOPNOTSUPP MSG_OOB был указан, но розетка не типа SOCK_STREAM.

- WSAESHUTDOWN Гнездо было закрыто; это не возможно, `SendToEx` чтобы вызвать `ShutDown` на гнездо после был вызван с *nКак* установлен на 1 или 2.

- WSAEWOULDBLOCK Гнездо помечено как неблокирующая и запрашиваемый операция будет блокировать.

- WSAEMSGSIZE Разъем типа SOCK_DGRAM, а грамма данных больше, чем максимальная, поддерживаемая реализацией Windows Sockets.

- WSAECONNABORTED Виртуальная схема была прервана из-за тайм-аута или другого сбоя.

- WSAECONNRESET Виртуальная схема была сплаится удаленной стороной.

- WSAEADDRNOTAVAIL Указанный адрес недоступен из локальной машины.

- WSAEAFNOSUPPORT Адреса в указанном семейство не могут быть использованы с этой розеткой.

- WSAEDESTADDRRE- Адрес назначения не требуется.

- WSAENETUNREACH Сеть не может быть достигнута от этого узла в настоящее время.

### <a name="remarks"></a>Remarks

Этот метод такой же, как [CAsyncSocket::SendTo,](#sendto) за исключением того, что он обрабатывает адреса IPv6, а также старые протоколы.

`SendToEx`используется на разъемах Datagram или stream и используется для записи исходящих данных на розетке. Для разъемов datagram необходимо позаботиться о том, чтобы не превышать максимальный размер `iMaxUdpDg` IP-пакета базовых подсетей, который дается элементом в структуре [WSADATA,](/windows/win32/api/winsock2/ns-winsock2-wsadata) заполненным [AfxSocketInit.](../../mfc/reference/application-information-and-management.md#afxsocketinit) Если данные слишком долго передаются через базовый протокол, ошибка WSAEMSGSize возвращается, и данные не передаются.

Обратите внимание, что `SendToEx` успешное завершение а. не указывает на успешное доставление данных.

`SendToEx`используется только на SOCK_DGRAM гнезде для отправки грамма данных в определенный разъем, определенный параметром *lpSockAddr.*

Для отправки трансляции (только на SOCK_DGRAM) адрес в параметре *lpSockAddr* должен быть построен с помощью специального IP-адреса INADDR_BROADCAST (определяется в файле заголовка Windows Sockets WINSOCK. H) вместе с предполагаемым номером порта. Или, если параметр *lpszHostAddress* null, розетка настроена для трансляции. Как правило, нецелесообразно, чтобы диаграмма вещания превышала размер, при котором может происходить фрагментация, что означает, что часть данных Datagram (за исключением заголовков) не должна превышать 512 байт.

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a>CAsyncSocket::SetSockOpt

Вызов ими функции участника, чтобы установить опцию разъема.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Параметры

*nOptionName*<br/>
Опция розетки, для которой значение должно быть установлено.

*lpOptionValue*<br/>
Указатель на буфер, в котором поставляется значение для запрашиваемого параметра.

*nOptionLen*<br/>
Размер буфера *lpOptionValue* в байтах.

*nУровень*<br/>
Уровень, на котором определен опцион; единственными поддерживаемыми уровнями являются SOL_SOCKET и IPPROTO_TCP.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEFAULT *lpOptionValue* не входит в допустимую часть адресного пространства процесса.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAEINVAL *nLevel* не действителен, или информация в *lpOptionValue* не действительна.

- WSAENETRESET Connection приурочен к SO_KEEPALIVE.

- WSAENOPROTOOPT Опция неизвестна или не поддерживается. В частности, SO_BROADCAST не поддерживается на розетках типа SOCK_STREAM, в то время как SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER и SO_OOBINLINE не поддерживаются на розетках типа SOCK_DGRAM.

- Соединение WSAENOTCONN было сбросить когда SO_KEEPALIVE установлено.

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

`SetSockOpt`устанавливает текущее значение для опции розетки, связанной с розеткой любого типа, в любом состоянии. Хотя параметры могут существовать на нескольких уровнях протокола, эта спецификация определяет только параметры, которые существуют на самом верхнем уровне "розетки". Параметры влияют на операции розетки, например, поступают ли ускоренные данные в обычный поток данных, могут ли сообщения с трансляцией отправляться на розетку и так далее.

Есть два типа вариантов розетки: boolean варианты, которые позволяют или отключить функцию или поведение, и варианты, которые требуют несколько значение или структуру. Для включения опции Boolean *lpOptionValue* указывает на ненулевой ряд. Чтобы отключить опцию *lpOptionValue* указывает на ряд, равный нулю. *nOptionLen* должен быть `sizeof(BOOL)` равен вариантам Boolean. Для других *вариантов, lpOptionValue* указывает на множество или структуру, которая содержит желаемое значение для опциона, и *nOptionLen* является длина рядового или структуры.

SO_LINGER контролирует действие, предпринимаемое при неотправленной дате, когда в розетке стоят неотправленные данные, и `Close` функция вызывается для закрытия гнезда.

По умолчанию розетка не может быть связана (см. [Bind)](#bind)с локальным адресом, который уже используется. В некоторых случаях, однако, может быть целесообразным "повторноиспользовать" адрес таким образом. Поскольку каждое соединение однозначно идентифицируется по сочетанию локальных и удаленных адресов, нет никаких проблем с наличием двух розеток, привязанных к тому же локальному адресу, пока удаленные адреса отличаются.

Чтобы сообщить реализации Windows `Bind` Sockets, что вызов на гнездо не должно быть запрещено, потому что желаемый адрес уже используется другой розеткой, приложение должно установить SO_REUSEADDR разъем анокет перед выдачей `Bind` вызова. Обратите внимание, что опция интерпретируется только во время `Bind` вызова: поэтому нет необходимости (но безвредно) устанавливать опцию на розетку, которая `Bind` не должна быть привязана к существующему адресу, а установка или сброс опции после вызова не влияет на этот или любой другой разъем.

Приложение может запросить, чтобы реализация Windows Sockets позволила использовать пакеты "keep-alive" в соединениях протокола управления передачей (TCP), включив опцию SO_KEEPALIVE розетки. Реализация Windows Sockets не должна поддерживать использование keep-alives: если это так, то точная семантика специфична для реализации, но должна соответствовать разделу 4.2.3.6 RFC 1122: "Требования к интернет-хостам - слои связи". Если соединение отброшено в результате "держать-жизнь" код ошибки WSAENETRESET возвращается к любым вызовам в процессе на розетке, и любые последующие вызовы сбой с WSAENOTCONN.

Вариант TCP_NODELAY отскакивает от алгоритма Nagle. Алгоритм Nagle используется для уменьшения количества небольших пакетов, отправленных устомом путем буферизации неподтвержденных данных отправки до тех пор, пока не будет отправлен полноразмерный пакет. Однако для некоторых приложений этот алгоритм может препятствовать производительности, и TCP_NODELAY может быть использован для его выключения. Авторы приложений не должны устанавливать TCP_NODELAY, если только влияние этого не является хорошо понятным и желаемым, поскольку TCP_NODELAY настройки могут оказать существенное негативное влияние на производительность сети. TCP_NODELAY является единственным поддерживаемым вариантом розетки, который использует IPPROTO_TCP уровня; все другие варианты использования уровня SOL_SOCKET.

Некоторые реализации Windows Sockets предоставляют информацию об отладке вывода, если SO_DEBUG опция установлена приложением.

Следующие варианты `SetSockOpt`поддерживаются для . Тип определяет тип данных, адресованных *lpOptionValue.*

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Разрешить передачу сообщений на розетке.|
|SO_DEBUG|BOOL|Записать отладочную информацию.|
|SO_DONTLINGER|BOOL|Не блокируйте `Close` ожидание отправки неотправленных данных. Установка этой опции эквивалентна `l_onoff` настройке SO_LINGER с набором к нулю.|
|SO_DONTROUTE|BOOL|Не маршрут: отправить непосредственно в интерфейс.|
|SO_KEEPALIVE|BOOL|Отправить держать-жизни.|
|SO_LINGER|`struct LINGER`|Задерживайте на `Close` если неотправленные данные присутствуют.|
|SO_OOBINLINE|BOOL|Получайте внедиапазоне данных в обычном потоке данных.|
|SO_RCVBUF|**int**|Укажите размер буфера для получения.|
|SO_REUSEADDR|BOOL|Разрешить гнездо быть привязаны к адресу, который уже используется. [(См. Bind](#bind).)|
|So_sndbuf|**int**|Укажите размер буфера для отправки.|
|TCP_NODELAY|BOOL|Отключить алгоритм Nagle для отправки объединенных пакетов.|

Параметры Berkeley Software Distribution (BSD) не `SetSockOpt` поддерживаются:

|Значение|Тип|Значение|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Розетка слушает|
|SO_ERROR|**int**|Получить статус ошибки и ясно.|
|SO_RCVLOWAT|**int**|Получайте низкую отметку воды.|
|SO_RCVTIMEO|**int**|Получение тайм-аута|
|SO_SNDLOWAT|**int**|Отправить низкий знак воды.|
|SO_SNDTIMEO|**int**|Отправить тайм-аут.|
|SO_TYPE|**int**|Тип розетки.|
|IP_OPTIONS||Установите поле параметров в заголовке IP.|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a>CAsyncSocket::Shutdown

Вызов эту функцию участника, чтобы отключить отправки, получает или как на гнездо.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Параметры

*Nhow*<br/>
Флаг, описывающий, какие типы операций больше не будут разрешены, используя следующие перечисленные значения:

- **получает 0 евро**

- **отправляет No 1**

- **оба No 2**

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный код ошибки может быть извлечен, позвонив [getLastError](#getlasterror). К этой функции участника применяются следующие ошибки:

- WSANOTINITIALISED Успешный [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) должен произойти перед использованием этого API.

- WSAENETDOWN Реализация Windows Sockets обнаружила, что сетевая подсистема сбой.

- WSAEINVAL *nHow* не действителен.

- WSAEINPROGRESS Операция блокирования розеток Windows находится в процессе.

- WSAENOTCONN Розетка не подключена (только SOCK_STREAM).

- WSAENOTSOCK Дескриптор не розетка.

### <a name="remarks"></a>Remarks

`ShutDown`используется на всех типах розеток, чтобы отключить прием, передачу, или оба. Если *nHow* 0, последующие получает на гнезде будет запрещено. Это не влияет на нижние слои протокола.

Для Протокола контроля передачи (TCP) окно TCP не изменяется, и входящие данные будут приниматься (но не признаны) до тех пор, пока окно не будет исчерпано. Для Протокола Datagram пользователя (UDP) входящие данные принимаются и стоят в очереди. Ни в коем случае не будет создан пакет ошибок ICMP. Если *nHow* является 1, последующие отправки запрещены. Для розетки TCP будет отправлен FIN. Установка *nКак* 2 отстраняет как посылает и получает как описано выше.

Обратите `ShutDown` внимание, что не закрывает розетку, а ресурсы, прикрепленные `Close` к розетке, не будут освобождены до тех пор, пока не будет названо. Приложение не должно полагаться на возможность повторного использования гнезда после его выключения. В частности, реализация Windows Sockets не требуется для поддержки `Connect` использования на такой розетке.

### <a name="example"></a>Пример

  Смотрите пример [для CAsyncSocket::OnReceive](#onreceive).

## <a name="casyncsocketsocket"></a><a name="socket"></a>CASyncSocket::Socket

Выделяет ручку розетки.

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

*Levent*<br/>
Битовая маска, которая определяет сочетание сетевых событий, в которых приложение заинтересовано.

- `FD_READ`: Хотите получить уведомление о готовности к чтению.

- `FD_WRITE`: Хотите получить уведомление о готовности к написанию.

- `FD_OOB`: Хотите получать уведомления о поступлении внедиапазонных данных.

- `FD_ACCEPT`: Хотите получать уведомления о входящих соединениях.

- `FD_CONNECT`: Хотите получить уведомление о завершении подключения.

- `FD_CLOSE`: Хотите получить уведомление о закрытии розетки.

*nПротоколТип*<br/>
Протокол, который будет использоваться с розеткой, которая характерна для указанной семьи адреса.

*nАдресФормат*<br/>
Адрес наячки семьи.

### <a name="return-value"></a>Возвращаемое значение

Возвращается `TRUE` на `FALSE` успех, на неудачу.

### <a name="remarks"></a>Remarks

Этот метод выделяет ручку розетки. Он не вызывает [CAsyncSocket:: Привязать](#bind) к связыванию розетки с указанным адресом, поэтому вам нужно вызвать `Bind` более поздно для того чтобы связать гнездо к определенному адресу. Вы можете использовать [CAsyncSocket::SetSockOpt](#setsockopt) установить опцию розетки, прежде чем он связан.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
