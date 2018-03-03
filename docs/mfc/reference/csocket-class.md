---
title: "CSocket-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ae8a30697783b478e9ffdb1c247f52d7b9f2ac2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="csocket-class"></a>CSocket-класс
Является производным от `CAsyncSocket`, наследует его инкапсуляция Windows Sockets API и представляет более высокий уровень абстракции, чем `CAsyncSocket` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|Создает объект `CSocket`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSocket::Attach](#attach)|Присоединяет **СОКЕТА** дескриптор `CSocket` объекта.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Отменяет блокирующий вызов, который в данный момент выполняется.|  
|[CSocket::Create](#create)|Создание сокета.|  
|[CSocket::FromHandle](#fromhandle)|Возвращает указатель на `CSocket` объект, которому передан **СОКЕТА** обработки.|  
|[CSocket::IsBlocking](#isblocking)|Определяет, является ли блокирующий вызов выполняется.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|Вызывается для обработки ожидающих сообщений, при ожидании завершения блокирующий вызов.|  
  
## <a name="remarks"></a>Примечания  
 `CSocket`работает с классами `CSocketFile` и `CArchive` для управления отправки и получения данных.  
  
 Объект `CSocket` также предоставляет блокировки, что является необходимым для синхронной операции из `CArchive`. Блокировка функции, такие как `Receive`, `Send`, `ReceiveFrom`, `SendTo`, и `Accept` (все наследуемые от `CAsyncSocket`), не возвращают `WSAEWOULDBLOCK` ошибки в `CSocket`. Вместо этого эти функции дождитесь завершения операции. Кроме того, исходного вызова будет завершена с ошибкой, `WSAEINTR` Если `CancelBlockingCall` , называется блокирует одну из этих функций.  
  
 Для использования `CSocket` объекта, вызовите конструктор, затем вызовите `Create` для создания базового `SOCKET` обработки (типа `SOCKET`). Параметры по умолчанию `Create` создать сокет потока, но если вы не используете сокета с `CArchive` объекта, можно задать параметр, чтобы вместо этого создать сокет датаграммы, или выполнить привязку к конкретному порту создание сокета сервера. Подключение к сокету клиента с помощью `Connect` на стороне клиента и `Accept` на стороне сервера. Затем создайте `CSocketFile` и свяжите его `CSocket` объекта в `CSocketFile` конструктора. Создайте `CArchive` объект для отправки и один для получения данных (при необходимости), свяжите их с `CSocketFile` объекта в `CArchive` конструктора. После завершения связи уничтожить `CArchive`, `CSocketFile`, и `CSocket` объектов. `SOCKET` Тип данных, описанное в статье [Windows Sockets: фон](../../mfc/windows-sockets-background.md).  
  
 При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, где `CSocket::Receive` входит в цикл (по `PumpMessages(FD_READ)`) ожидание запрошенное количество байтов. Это, поскольку Windows sockets допускает только один вызов recv одного уведомления FD_READ, но `CSocketFile` и `CSocket` разрешить несколько вызовов recv на FD_READ. При появлении FD_READ нет данных для чтения, приложение зависает. Если вы никогда не получить другой FD_READ, приложение выходит из режима взаимодействия через сокет.  
  
 Эту проблему можно разрешить следующим образом. В `OnReceive` метод класса socket, вызов `CAsyncSocket::IOCtl(FIONREAD, ...)` перед вызовом метода `Serialize` метод класса сообщений при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных средний сети обычно менее 1096 байт). Если объем доступных данных меньше, чем требуется, дождитесь все данные будут приниматься и только затем запустить операцию чтения.  
  
 В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получения. Предполагается, что он объявляется в другом месте в коде.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  При использовании сокетов второстепенных потоков в приложении MFC статически скомпонованной MFC, необходимо вызвать метод `AfxSocketInit` в каждый поток, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
 Дополнительные сведения см. в разделе [сокеты Windows в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: как сокетов с архивами рабочих](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: последовательность операций](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: пример сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsock.h  
  
##  <a name="attach"></a>CSocket::Attach  
 Вызовите эту функцию-член для присоединения `hSocket` дескриптор `CSocket` объекта.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 **СОКЕТА** дескриптор хранится в объекте [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) члена данных.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 Вызовите эту функцию-член для отмены блокирующий вызов в настоящий момент.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция отменяет все незавершенные операции блокирования для этого сокета. Исходный блокирующий вызов как можно быстрее будет завершена с ошибкой, **WSAEINTR**.  
  
 В случае блокировки **Connect** операции, реализация Windows Sockets завершит блокирующий вызов как возможные, но он может оказаться невозможным ресурсов сокета для освобождаться до завершения соединения (и затем сброшен) или тайм-аут. Это, скорее всего, будет заметно только в том случае, если приложение немедленно пытается открыть новый сокет (если доступны не сокеты) или для подключения к тем же узлом.  
  
 Отмена любой операции, отличный от **Accept** можно оставить сокета в неопределенном состоянии. Если приложение отменяет операцию блокировки на сокете, только операции, приложение может зависеть от возможности для выполнения на сокете представляет собой вызов **закрыть**, несмотря на то, что другие операции могут работать в некоторых сокеты Windows в реализации. При желании максимальной переносимости приложения Будьте внимательны, чтобы не должны зависеть от операций после отмены.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="create"></a>CSocket::Create  
 Вызовите **создать** после создания объекта сокета Создание сокетов Windows и присоединение его функции-члена.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketPort`  
 Определенный порт для использования с сокета, или 0, если требуется MFC порт.  
  
 `nSocketType`  
 **SOCK_STREAM** или **SOCK_DGRAM**.  
  
 `lpszSocketAddress`  
 Указатель на строку, содержащую сетевой адрес подключенного сокета пунктирная число, например «128.56.22.8». Передача **NULL** строку для этого параметра указывает **CSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае можно извлечь 0 и код ошибки путем вызова `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 **Создание** вызывает **привязки** привязке сокета по указанному адресу. Поддерживаются следующие типы сокета:  
  
- **SOCK_STREAM** виртуализации, обеспечивает надежный, двустороннее-подключений байтовые потоки. Использует протокол управления передачей (TCP) для семейства адресов Интернета.  
  
- **SOCK_DGRAM** поддерживает датаграммы — без установления соединения, ненадежные буферы фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета. Чтобы использовать этот параметр, не должны использовать сокета с `CArchive` объекта.  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Имейте в виду, что если этот объект сокета идет области видимости, соединение закрывается. Не вызывайте **создать** для этого нового объекта сокета.  
  
 Дополнительные сведения о сокеты потока и датаграммы см. в статьях [Windows Sockets: фон](../../mfc/windows-sockets-background.md), [Windows Sockets: порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md), и [Windows Sockets: с помощью Сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="csocket"></a>CSocket::CSocket  
 Создает объект `CSocket`.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>Примечания  
 После создания экземпляра, необходимо вызвать **создать** функции-члена.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="fromhandle"></a>CSocket::FromHandle  
 Возвращает указатель на `CSocket` объект.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CSocket` объекта, или **NULL** при наличии не `CSocket` объект присоединен к `hSocket`.  
  
### <a name="remarks"></a>Примечания  
 Для заданного **СОКЕТА** обработки, если `CSocket` объект не присоединен к дескриптору, функция-член возвращает **NULL** и не создает временный объект.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isblocking"></a>CSocket::IsBlocking  
 Вызовите эту функцию-член для определения блокирующий вызов выполняется.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сокет блокировки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="onmessagepending"></a>CSocket::OnMessagePending  
 Переопределите эту функцию-член для поиска определенных сообщений из Windows и отреагировать на них в сокета.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Существует расширенная overridable.  
  
 Платформа вызывает `OnMessagePending` пока сокет является прокачки сообщений Windows, чтобы предоставить вам возможность обработки сообщений, представляющие интерес для приложения. Примеры использования `OnMessagePending`, см. в статье [Windows Sockets: наследование от классов сокета](../../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="see-also"></a>См. также  
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
