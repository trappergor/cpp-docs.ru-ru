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
- WinSock CSocket class
- CSocket class
- SOCKET handle
- sockets classes
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 451ea100dbf02e365204fe4fdf1c380e855d8231
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="csocket-class"></a>CSocket-класс
Является производным от `CAsyncSocket`, наследует его инкапсуляция Windows Sockets API и представляет более высокий уровень абстракции, чем `CAsyncSocket` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|Создает объект `CSocket`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocket::Attach](#attach)|Присоединяет **СОКЕТА** дескриптор `CSocket` объекта.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Отменяет блокирующий вызов, который в данный момент выполняется.|  
|[CSocket::Create](#create)|Создание сокета.|  
|[CSocket::FromHandle](#fromhandle)|Возвращает указатель на `CSocket` объекта, учитывая **СОКЕТА** обработки.|  
|[CSocket::IsBlocking](#isblocking)|Определяет, выполняется ли блокирующий вызов.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|Вызывается для обработки ожидающих сообщений при ожидании завершения блокирующий вызов.|  
  
## <a name="remarks"></a>Примечания  
 `CSocket`работает с классами `CSocketFile` и `CArchive` для управления отправки и получения данных.  
  
 Объект `CSocket` также предоставляет блокировки, что является необходимым для синхронной операции из `CArchive`. Блокирование функции, такие как `Receive`, `Send`, `ReceiveFrom`, `SendTo`, и `Accept` (все унаследованные от `CAsyncSocket`), не возвращают `WSAEWOULDBLOCK` ошибки в `CSocket`. Вместо этого эти функции дождитесь завершения операции. Кроме того, исходный вызов завершится с ошибкой `WSAEINTR` Если `CancelBlockingCall` , называется блокирует одну из этих функций.  
  
 Для использования `CSocket` объекта, вызовите конструктор, затем вызовите `Create` для создания базового `SOCKET` обработки (типа `SOCKET`). Параметры по умолчанию `Create` создания сокета потока, но если вы не используете сокета с `CArchive` объект, можно задать параметр, чтобы вместо создания сокета датаграмм, или выполнить привязку к конкретному порту для создания сокета сервера. Подключения сокета клиента с помощью `Connect` на стороне клиента и `Accept` на стороне сервера. Затем создайте `CSocketFile` и свяжите его `CSocket` объекта в `CSocketFile` конструктора. Создайте `CArchive` объект для отправки и один для получения данных (при необходимости), затем связываются с `CSocketFile` объекта в `CArchive` конструктора. При связи уничтожить `CArchive`, `CSocketFile`, и `CSocket` объектов. `SOCKET` Тип данных, описанные в статье [Windows Sockets: фон](../../mfc/windows-sockets-background.md).  
  
 При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, когда `CSocket::Receive` входит в цикл (по `PumpMessages(FD_READ)`) ожидает запрошенное количество байтов. Это, поскольку Windows sockets допускает только один вызов recv FD_READ уведомления, но `CSocketFile` и `CSocket` разрешить несколько вызовов recv на FD_READ. Если вы получите FD_READ, когда нет данных для чтения, приложение зависает. Если вы никогда не получить другой FD_READ, приложение перестает взаимодействуют через сокет.  
  
 Эту проблему можно устранить следующим образом. В `OnReceive` метод класса socket, вызов `CAsyncSocket::IOCtl(FIONREAD, ...)` перед вызовом метода `Serialize` метод класса сообщения при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных среднего сети, обычно менее 1096 байт). Если объем доступных данных меньше, чем требуется, дождаться получения данных для получения и только затем запустить операцию чтения.  
  
 В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получения. Предполагается, что он объявляется в другом месте в коде.  
  
 [!code-cpp[NVC_MFCSocketThread&#4;](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  При использовании сокеты MFC в дополнительных потоках в приложении MFC статически скомпонованной, необходимо вызвать `AfxSocketInit` каждого потока, которая использует сокеты инициализировать библиотеку сокетов. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
 Дополнительные сведения см. в разделе [сокеты Windows в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: как сокетов с архивами рабочих](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: последовательность операций](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: пример из сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsock.h  
  
##  <a name="attach"></a>CSocket::Attach  
 Вызов этой функции-члена для присоединения `hSocket` дескриптор `CSocket` объекта.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Параметры  
 `hSocket`  
 Содержит дескриптор сокета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 **СОКЕТА** дескриптор хранятся в объекте [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) данные-член.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSocketThread&#1;](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread&#2;](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread&#3;](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 Вызовите для отмены блокирующий вызов в настоящее время эта функция-член.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция отменяет все невыполненные операции блокирования для этого сокета. Блокировки исходного вызова как можно быстрее завершится с ошибкой **WSAEINTR**.  
  
 В случае блокировки **подключение** операции, реализация Windows Sockets завершит блокирующий вызов как возможные, но возможно не для ресурсов сокета должна освобождаться до подключения завершена (и затем сброса) или тайм-аут. Это скорее всего, будет заметно только в том случае, если приложение немедленно попытается открыть новый сокет (если доступны не сокеты) или для подключения к тем же узлом.  
  
 Не отменяя любой операции **Accept** можно оставить сокета в неопределенном состоянии. Если приложение отменяет блокирующая операция на сокете, только операции, приложение может зависеть от возможность выполнения на сокете представляет собой вызов **закрыть**, несмотря на то, что другие операции могут работать на несколько реализаций Windows Sockets. При желании максимальной переносимости приложения Будьте внимательны, чтобы не зависят от выполнения операций после отмены.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="create"></a>CSocket::Create  
 Вызов **создать** после создания объекта сокета для создания Windows socket и присоединить его функции-члена.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nSocketPort`  
 Определенный порт для использования с сокет, или 0, если требуется MFC порт.  
  
 `nSocketType`  
 **Неблокируемый** или **SOCK_DGRAM**.  
  
 `lpszSocketAddress`  
 Указатель на строку, содержащую сетевой адрес подключенного сокета, пунктирная номер, например «128.56.22.8». Передача **NULL** строка этот параметр указывает **CSocket** экземпляр должен контролировать действия клиента во всех сетевых интерфейсах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0 и код ошибки может быть получено путем вызова `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 **Создание** затем вызывает **привязки** для привязки сокет по указанному адресу. Поддерживаются следующие типы сокета:  
  
- **Неблокируемый** виртуализации, предоставляет надежный, двустороннее-подключений байтовые потоки. Использует протокол TCP (Transmission Control) для семейства адресов Интернета.  
  
- **SOCK_DGRAM** поддерживает датаграммы — без установления соединения, ненадежное буферы фиксированной (обычно малой) максимальной длиной. Использует протокол UDP (User Datagram) для семейства адресов Интернета. Чтобы использовать этот параметр, не следует использовать сокет с `CArchive` объекта.  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Имейте в виду, что если этот объект сокета идет области, соединение закрывается. Не следует вызывать **создать** для этого нового объекта сокета.  
  
 Дополнительные сведения о сокеты потока и датаграммы см. в статьях [Windows Sockets: фон](../../mfc/windows-sockets-background.md), [Windows Sockets: порты и адреса сокета](../../mfc/windows-sockets-ports-and-socket-addresses.md), и [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
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
 Указатель на `CSocket` объекта, или **NULL** при наличии не `CSocket` объект присоединяется к `hSocket`.  
  
### <a name="remarks"></a>Примечания  
 При наличии **СОКЕТА** обработки, если `CSocket` объект не присоединен к дескриптору, функция-член возвращает **NULL** и не создает временный объект.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isblocking"></a>CSocket::IsBlocking  
 Вызовите эту функцию-член для определения, если блокирующий вызов не выполняется.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сокет блокировки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="onmessagepending"></a>CSocket::OnMessagePending  
 Переопределите эту функцию-член для поиска конкретного сообщения из Windows и отвечать на них в гнезда.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Существует расширенная переопределяемыми.  
  
 Платформа вызывает функцию `OnMessagePending` хотя сокет обработка сообщений Windows для предоставления вам возможности работать с сообщениями, представляющие интерес для приложения. Примеры того, как использовать `OnMessagePending`, см. в статье [Windows Sockets: наследование от классов сокета](../../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="see-also"></a>См. также  
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)

