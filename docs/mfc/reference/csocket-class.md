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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426555"
---
# <a name="csocket-class"></a>Класс CSocket

Является производным от `CAsyncSocket`, наследует его инкапсуляцию API-интерфейса сокетов Windows и представляет более высокий уровень абстракции, чем объект `CAsyncSocket`.

## <a name="syntax"></a>Синтаксис

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CSocket:: CSocket](#csocket)|Формирует объект `CSocket`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CSocket:: Attach](#attach)|Присоединяет маркер СОКЕТа к объекту `CSocket`.|
|[CSocket:: Канцелблоккингкалл](#cancelblockingcall)|Отменяет выполняющийся в данный момент блокирующий вызов.|
|[CSocket:: Create](#create)|Создает сокет.|
|[CSocket:: FromHandle](#fromhandle)|Возвращает указатель на `CSocket` объект по заданному маркеру СОКЕТа.|
|[CSocket:: Block](#isblocking)|Определяет, выполняется ли блокирующий вызов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[CSocket:: Онмессажепендинг](#onmessagepending)|Вызывается для обработки ожидающих сообщений при ожидании завершения блокирующего вызова.|

## <a name="remarks"></a>Remarks

`CSocket` работает с классами `CSocketFile` и `CArchive` для управления отправкой и получением данных.

Объект `CSocket` также предоставляет блокировку, которая необходима для синхронной работы `CArchive`. Блокирующие функции, такие как `Receive`, `Send`, `ReceiveFrom`, `SendTo`и `Accept` (все наследуются от `CAsyncSocket`), не возвращают `WSAEWOULDBLOCK` ошибку в `CSocket`. Вместо этого эти функции ожидают завершения операции. Кроме того, исходный вызов завершится ошибкой ВСАЕИНТР, если вызывается `CancelBlockingCall`, когда одна из этих функций блокируется.

Чтобы использовать объект `CSocket`, вызовите конструктор, а затем вызовите метод `Create`, чтобы создать базовый маркер СОКЕТа (сокет типа). Параметры по умолчанию `Create` создают сокет потока, но если сокет не используется с объектом `CArchive`, можно указать параметр для создания сокета датаграммы или выполнить привязку к конкретному порту для создания сокета сервера. Подключитесь к сокету клиента с помощью `Connect` на стороне клиента и `Accept` на стороне сервера. Затем создайте объект `CSocketFile` и свяжите его с `CSocket`ным объектом в конструкторе `CSocketFile`. Затем создайте объект `CArchive` для отправки данных, а другой — для получения (при необходимости), а затем свяжите их с объектом `CSocketFile` в конструкторе `CArchive`. После завершения обмена данными удалите `CArchive`, `CSocketFile`и `CSocket` объекты. Тип данных СОКЕТа описан в статье [Windows Sockets: Background](../../mfc/windows-sockets-background.md).

При использовании `CArchive` с `CSocketFile` и `CSocket`может возникнуть ситуация, когда `CSocket::Receive` входит в цикл (`PumpMessages(FD_READ)`), ожидая запрошенный объем в байтах. Это обусловлено тем, что сокеты Windows допускают только один вызов recv для FD_READ уведомления, но `CSocketFile` и `CSocket` разрешают несколько вызовов recv per FD_READ. Если при отсутствии данных для чтения появляется FD_READ, приложение зависает. Если вы никогда не получаете другой FD_READ, приложение перестает взаимодействовать через сокет.

Эту проблему можно устранить следующим образом. В методе `OnReceive` класса Socket вызовите метод `CAsyncSocket::IOCtl(FIONREAD, ...)` перед вызовом метода `Serialize` класса Message, если ожидаемые данные, считываемые из сокета, превышают размер одного пакета TCP (максимальная единица передачи, обычно по крайней мере 1096 байт). Если размер доступных данных меньше, чем требуется, дождитесь получения всех данных и запустите операцию чтения только после этого.

В следующем примере `m_dwExpected` — приблизительное число байтов, которое пользователь должен получить. Предполагается, что вы объявили его в любом расположении в коде.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  При использовании сокетов MFC во вторичных потоках в статическом связанном приложении MFC необходимо вызвать `AfxSocketInit` в каждом потоке, использующем сокеты для инициализации библиотек сокетов. По умолчанию `AfxSocketInit` вызывается только в основном потоке.

Дополнительные сведения см. в статьях [сокеты Windows в MFC](../../mfc/windows-sockets-in-mfc.md), [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [сокеты Windows: как работают сокеты с архивами](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [сокеты Windows: последовательность операций](../../mfc/windows-sockets-sequence-of-operations.md), [сокеты Windows: пример сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Требования

**Заголовок:** афкссокк. h

##  <a name="attach"></a>CSocket:: Attach

Вызовите эту функцию-член, чтобы присоединить `hSocket`ный обработчик к объекту `CSocket`.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*хсоккет*<br/>
Содержит маркер для сокета.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно.

### <a name="remarks"></a>Remarks

Маркер СОКЕТа хранится в элементе данных [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) объекта.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>CSocket:: Канцелблоккингкалл

Вызовите эту функцию-член для отмены блокирующего вызова, выполняемого в данный момент.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Remarks

Эта функция отменяет все невыполненные операции блокировки для этого сокета. Исходный вызов блокировки будет завершаться как можно скорее с ошибкой ВСАЕИНТР.

В случае блокировки `Connect`ной операции реализация Windows Sockets будет завершать блокирующий вызов как можно скорее, однако ресурсы сокета могут быть освобождены до тех пор, пока подключение не будет завершено (а затем не будет сброшено) или истекло время ожидания. Это может быть заметным, только если приложение сразу же пытается открыть новый сокет (если нет доступных сокетов) или подключиться к тому же узлу.

Отмена любой операции, кроме `Accept`, может привести к неопределенному состоянию сокета. Если приложение отменяет операцию блокировки на сокете, единственной операцией, которую приложение может зависеть от выполнения на сокете, является вызов `Close`, хотя другие операции могут работать с некоторыми реализациями сокетов Windows. Если вы хотите обеспечить максимальную переносимость приложения, необходимо соблюдать осторожность, чтобы не зависеть от выполнения операций после отмены.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="create"></a>CSocket:: Create

Вызовите функцию **создания** члена после создания объекта сокета, чтобы создать сокет Windows и присоединить его.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Параметры

*нсоккетпорт*<br/>
Определенный порт, используемый с сокетом, или значение 0, если необходимо выбрать порт в MFC.

*нсоккеттипе*<br/>
SOCK_STREAM или SOCK_DGRAM.

*лпсзсоккетаддресс*<br/>
Указатель на строку, содержащую сетевой адрес подключенного сокета, разделенный цифрой, например "128.56.22.8". Передача значения NULL для этого параметра указывает на то, что экземпляр `CSocket` должен прослушивать активность клиентов во всех сетевых интерфейсах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0, и можно получить конкретный код ошибки, вызвав `GetLastError`.

### <a name="remarks"></a>Remarks

затем `Create` вызывает `Bind`, чтобы привязать сокет к указанному адресу. Поддерживаются следующие типы сокетов:

- SOCK_STREAM предоставляет последовательные, надежные, двусторонние байтовые потоки, основанные на подключениях. Использует протокол TCP для семейства Интернет-адресов.

- SOCK_DGRAM поддерживает датаграммы без установления соединения, ненадежные буферы фиксированной (обычно небольшой) максимальной длины. Использует протокол UDP для семейства Интернет-адресов. Чтобы использовать этот параметр, не следует использовать сокет с объектом `CArchive`.

    > [!NOTE]
    >  Функция-член `Accept` принимает ссылку на новый пустой объект `CSocket` в качестве параметра. Этот объект необходимо создать перед вызовом `Accept`. Помните, что если объект сокета выходит за пределы области действия, соединение закрывается. Не вызывайте `Create` для этого нового объекта сокета.

Дополнительные сведения о потоковых и многопортовых сокетах см. в статьях [Windows Sockets: фоновый режим](../../mfc/windows-sockets-background.md), [сокеты Windows: порты и адреса сокетов](../../mfc/windows-sockets-ports-and-socket-addresses.md), а также [сокеты Windows. Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="csocket"></a>CSocket:: CSocket

Формирует объект `CSocket`.

```
CSocket();
```

### <a name="remarks"></a>Remarks

После создания необходимо вызвать функцию члена `Create`.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="fromhandle"></a>CSocket:: FromHandle

Возвращает указатель на объект `CSocket`.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*хсоккет*<br/>
Содержит маркер для сокета.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CSocket` или значение NULL, если к *хсоккет*не присоединен `CSocket` объект.

### <a name="remarks"></a>Remarks

При наличии маркера СОКЕТа, если объект `CSocket` не присоединен к этому обработчику, функция-член возвращает значение NULL и не создает временный объект.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isblocking"></a>CSocket:: Block

Вызовите эту функцию-член, чтобы определить, выполняется ли блокирующий вызов.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сокет блокируется; в противном случае — 0.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="onmessagepending"></a>CSocket:: Онмессажепендинг

Переопределите эту функцию члена, чтобы искать определенные сообщения в Windows и реагировать на них в сокете.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение было обработано; в противном случае — 0.

### <a name="remarks"></a>Remarks

Это расширенный переопределяемый объект.

Платформа вызывает `OnMessagePending`, пока сокет перебирает сообщения Windows, чтобы дать вам возможность работать с сообщениями, представляющими интерес для вашего приложения. Примеры использования `OnMessagePending`см. в статье [сокеты Windows: наследование от классов сокетов](../../mfc/windows-sockets-deriving-from-socket-classes.md).

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>См. также раздел

[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
