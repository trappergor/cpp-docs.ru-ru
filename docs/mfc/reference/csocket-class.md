---
title: Класс CSocket
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: a861e557b7368d13d615aaf796faded93c72b040
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323964"
---
# <a name="csocket-class"></a>Класс CSocket

Является производным от `CAsyncSocket`, наследует его инкапсуляцию API сокетов Windows и представляет более высокий уровень абстракции, чем `CAsyncSocket` объекта.

## <a name="syntax"></a>Синтаксис

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|Создает объект `CSocket`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSocket::Attach](#attach)|Прикрепляет дескриптор СОКЕТА `CSocket` объекта.|
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Отменяет блокирующий вызов, который в данный момент.|
|[CSocket::Create](#create)|Создает сокет.|
|[CSocket::FromHandle](#fromhandle)|Возвращает указатель на `CSocket` объект, которому передан дескриптор СОКЕТА.|
|[CSocket::IsBlocking](#isblocking)|Определяет, является ли блокирующий вызов в процессе выполнения.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CSocket::OnMessagePending](#onmessagepending)|Вызывается для обработки сообщений, ожидающих во время ожидания для блокирующего вызова для завершения.|

## <a name="remarks"></a>Примечания

`CSocket` работает с классами `CSocketFile` и `CArchive` для управления отправкой и получением данных.

Объект `CSocket` также предоставляет блокировки, что является необходимым для синхронной операции из `CArchive`. Блокировка функций, таких как `Receive`, `Send`, `ReceiveFrom`, `SendTo`, и `Accept` (все наследуемые от `CAsyncSocket`), не возвращают `WSAEWOULDBLOCK` ошибка в `CSocket`. Вместо этого эти функции дождитесь завершения операции. Кроме того, исходный вызов будет завершена с ошибкой, WSAEINTR Если `CancelBlockingCall` называется блокирует одну из этих функций.

Чтобы использовать `CSocket` объекта, вызовите конструктор, затем вызовите `Create` создать базовый дескриптор СОКЕТА (тип СОКЕТА). Параметры по умолчанию `Create` создание сокета потока, но если вы не используете сокет с `CArchive` объекта, можно задать параметр, чтобы вместо этого создать сокет датаграммы, или выполнить привязку к конкретному порту для создания сокета сервера. Подключитесь к сокета клиента с помощью `Connect` на стороне клиента и `Accept` на стороне сервера. Затем создайте `CSocketFile` объекта и связать ее с `CSocket` объекта в `CSocketFile` конструктор. Создайте `CArchive` объект для отправки и один для получения данных (при необходимости), свяжите их с `CSocketFile` объекта в `CArchive` конструктор. После завершения связи уничтожить `CArchive`, `CSocketFile`, и `CSocket` объектов. Тип данных СОКЕТА описан в статье [сокеты Windows: фон](../../mfc/windows-sockets-background.md).

При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, где `CSocket::Receive` входит в цикл (с `PumpMessages(FD_READ)`) ожидание запрашиваемое количество байтов. Это Windows sockets допускает только один вызов recv одного уведомления FD_READ, но `CSocketFile` и `CSocket` разрешить несколько вызовов получаемого сообщения в FD_READ. Если вы получаете FD_READ при отсутствии данных для чтения, приложение перестает отвечать на запросы. Если вы никогда не получить другой FD_READ, приложение перестает взаимодействуют через сокет.

Эту проблему можно решить следующим образом. В `OnReceive` метод класса socket, вызов `CAsyncSocket::IOCtl(FIONREAD, ...)` перед вызовом метода `Serialize` метод класса сообщения при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных среды сети обычно менее 1096 байт). Если размер доступных данных меньше, чем требуется, дождитесь все данные будут приниматься и только после запуска операции чтения.

В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получить. Предполагается, что она объявлена в другом месте в коде.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  С помощью сокетов MFC в второстепенных потоков в приложении MFC статически скомпонованной необходимо вызвать метод `AfxSocketInit` в каждом потоке, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.

Дополнительные сведения см. в разделе [Windows Sockets в MFC](../../mfc/windows-sockets-in-mfc.md), [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [сокеты Windows: Работа сокетов с архивами](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [сокеты Windows: Последовательность операций](../../mfc/windows-sockets-sequence-of-operations.md), [сокеты Windows: Пример сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

##  <a name="attach"></a>  CSocket::Attach

Вызовите эту функцию-член для присоединения `hSocket` дескриптор `CSocket` объекта.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит дескриптор для сокета.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно.

### <a name="remarks"></a>Примечания

Дескриптор СОКЕТА сохраняется в объекте [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) данные-член.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall

Вызовите для отмены блокирующий вызов в настоящее время эта функция-член.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Примечания

Эта функция отменяет любые незавершенной операции блокировки для этого сокета. Исходный блокирующий вызов будет как можно скорее завершена с ошибкой, WSAEINTR.

В случае блокировки `Connect` операции, реализация Windows Sockets завершит блокирующий вызов как возможность, но он может оказаться невозможным для ресурсов сокета к освобождению, пока подключение завершена (и затем сброшен) или Истекло время ожидания. Это скорее всего, будет заметно только в том случае, если приложение попытается открыть новый сокет (если доступны не сокеты), или для подключения к тем же узлом.

Отмена любой операции, отличные от `Accept` можно оставить сокет в неопределенном состоянии. Если приложение отменяет блокирующей операции на сокете, единственной операцией, приложение может зависеть от возможности для выполнения на сокете представляет собой вызов `Close`, несмотря на то, что другие операции могут работать в некоторых реализациях сокеты Windows. При желании максимальный уровень мобильности для вашего приложения, будьте внимательны и не зависят от того, выполнение операций после отмены.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="create"></a>  CSocket::Create

Вызовите **создать** функция-член после построения объект сокета, чтобы создать сокет Windows и подключить его.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Параметры

*nSocketPort*<br/>
Определенный порт для использования с сокет, или 0, если вы хотите, чтобы MFC порт.

*nSocketType*<br/>
SOCK_STREAM или SOCK_DGRAM.

*lpszSocketAddress*<br/>
Указатель на строку, содержащую сетевой адрес подключенного сокета, пунктирная числа, например «128.56.22.8». Передача NULL строка этот параметр указывает `CSocket` экземпляр должен контролировать действия клиентов на всех сетевых интерфейсов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и конкретный код ошибки путем вызова `GetLastError`.

### <a name="remarks"></a>Примечания

`Create` затем вызывает `Bind` для привязывает сокет к указанному адресу. Поддерживаются следующие типы сокета:

- SOCK_STREAM предоставляет виртуализации, надежный, двустороннего подключения, байтовые потоки. Использует протокол управления передачей (TCP) для семейства адресов Интернета.

- SOCK_DGRAM поддерживает датаграммы — без установления соединения, ненадежные буферы фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета. Чтобы использовать этот параметр, не должны использовать сокет с `CArchive` объекта.

    > [!NOTE]
    >  `Accept` Функция-член принимает ссылку на новую, пустую `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода `Accept`. Имейте в виду, что если этот объект сокета идет области, соединение закрывается. Не вызывайте `Create` для этого нового объекта сокета.

Дополнительные сведения о stream и датаграмм сокетов, см. в статьях [сокеты Windows: Фон](../../mfc/windows-sockets-background.md), [сокеты Windows: Порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md), и [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="csocket"></a>  CSocket::CSocket

Создает объект `CSocket`.

```
CSocket();
```

### <a name="remarks"></a>Примечания

После создания, необходимо вызвать `Create` функция-член.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="fromhandle"></a>  CSocket::FromHandle

Возвращает указатель на `CSocket` объект.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит дескриптор для сокета.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CSocket` объекта, или значение NULL, если не `CSocket` объект присоединен к *hSocket*.

### <a name="remarks"></a>Примечания

Когда дескриптор СОКЕТА, если `CSocket` объект не присоединен к дескриптору, функция-член возвращает значение NULL и не создает временный объект.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isblocking"></a>  CSocket::IsBlocking

Вызовите для определения, блокирующий вызов выполняется ли эта функция-член.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сокет блокируясь; в противном случае 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="onmessagepending"></a>  CSocket::OnMessagePending

Переопределите эта функция-член для поиска определенного сообщения из Windows и отреагировать на них в сокета.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение было обработано. в противном случае 0.

### <a name="remarks"></a>Примечания

Существует расширенная переопределяемый.

Платформа вызывает `OnMessagePending` пока сокет является цикл обработки сообщений Windows для предоставления вам возможности работать с сообщениями интерес для приложения. Примеры использования `OnMessagePending`, см. в статье [сокеты Windows: Наследование от классов сокета](../../mfc/windows-sockets-deriving-from-socket-classes.md).

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>См. также

[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
