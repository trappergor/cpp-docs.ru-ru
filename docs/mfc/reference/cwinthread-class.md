---
title: Класс CWinThread
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: f2e95dd3ba8be31633590e37d95dedc8749ebdd8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367421"
---
# <a name="cwinthread-class"></a>Класс CWinThread

Класс, представляющий поток исполнения в приложении.

## <a name="syntax"></a>Синтаксис

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|Формирует объект `CWinThread`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinThread::CreateThread](#createthread)|Начинается выполнение `CWinThread` объекта.|
|[CWinThread::ExitInstance](#exitinstance)|Переопределение для очистки при завершении потока.|
|[CWinThread::GetMainWnd](#getmainwnd)|Извлекает указатель на основное окно для потока.|
|[CWinThread::GetThreadPriority](#getthreadpriority)|Получает приоритет текущего потока.|
|[CWinThread::InitInstance](#initinstance)|Переопределение для выполнения инициализации экземпляра потока.|
|[CWinThread::IsIdleMessage](#isidlemessage)|Проверка специальных сообщений.|
|[CWinThread::Onidle](#onidle)|Переопределение для выполнения обработки простоя потока.|
|[CWinThread::PostThreadMessage](#postthreadmessage)|Сообщение на другой `CWinThread` объект.|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Фильтры сообщений, прежде чем они будут отправлены на функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage.](/windows/win32/api/winuser/nf-winuser-dispatchmessage)|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенные сообщения, прежде чем они достигнут приложения.|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, брошенные обработчиками сообщений и команд.|
|[CWinThread::PumpMessage](#pumpmessage)|Содержит цикл сообщения потока.|
|[CWinThread::ResumeThread](#resumethread)|Декретирует количество приоружей потока.|
|[CWinThread::Run](#run)|Функция управления потоками с помощью насоса с помощью мессенджера. Переопределение для настройки цикла сообщений по умолчанию.|
|[CWinThread::SetThreadPriority](#setthreadpriority)|Устанавливает приоритет текущего потока.|
|[CWinThread::SuspendThread](#suspendthread)|Приращения потока приостанавливают отсчет.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CWinThread::operator HANDLE](#operator_handle)|Извлекает ручку `CWinThread` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Определяет, следует ли уничтожать объект при прекращении потока.|
|[CWinThread::m_hThread](#m_hthread)|Обработка текущего потока.|
|[CWinThread::m_nThreadID](#m_nthreadid)|Идентификатор текущего потока.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Указатель на основное окно контейнерного приложения, когда сервер OLE находится на месте.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Держит указатель на основное окно приложения.|

## <a name="remarks"></a>Remarks

Основная нить выполнения обычно обеспечивается объектом, полученным из; `CWinApp` `CWinApp` происходит от `CWinThread`. Дополнительные `CWinThread` объекты позволяют несколько потоков в данном приложении.

Существует два общих типа `CWinThread` потоков, поддерживающих: рабочие потоки и потоки пользовательского интерфейса. Рабочие потоки не имеют насоса сообщений: например, поток, выполняемый фоновые вычисления в приложении электронной таблицы. Потоки интерфейса пользователя имеют насос сообщений и обрабатывают сообщения, полученные из системы. [CWinApp](../../mfc/reference/cwinapp-class.md) и классы, полученные из него являются примерами пользовательских интерфейсных потоков. Другие потоки пользователь-интерфейс также могут `CWinThread`быть получены непосредственно из .

Объекты `CWinThread` класса обычно существуют в течение всего потока. Если вы хотите изменить это поведение, установите [m_bAutoDelete](#m_bautodelete) FALSE.

Класс `CWinThread` необходим, чтобы сделать ваш код и MFC полностью безопасности потока. Данные о локальном потоке, используемые платформой `CWinThread` для поддержания информации, конкретной потока, управляются объектами. Из-за этой `CWinThread` зависимости от обработки данных локального потока любой поток, который использует MFC, должен быть создан MFC. Например, поток, созданный функцией времени [выполнения, _beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) не могут использовать aI-аПЫ MFC.

Чтобы создать поток, позвоните [в AfxBeginThread](application-information-and-management.md#afxbeginthread). Существует две формы, в зависимости от того, хотите ли вы рабочего или пользовательского интерфейса потока. Если требуется поток пользовательского интерфейса, перейдите к `AfxBeginThread` указателю на `CRuntimeClass` ваш `CWinThread`класс, полученный из-производных. Если требуется создать рабочий поток, перейдите указателю `AfxBeginThread` на функцию управления и параметр к функции управления. Как для рабочих потоков, так и для потоков пользовательского интерфейса можно указать дополнительные параметры, которые изменяют приоритет, размер стека, флаги создания и атрибуты безопасности. `AfxBeginThread`вернет указатель на `CWinThread` ваш новый объект.

Вместо вызова, `AfxBeginThread`вы можете `CWinThread`построить объект, `CreateThread`полученный в результате, а затем вызвать . Этот двухступенчатый метод построения полезен, если требуется повторное использование `CWinThread` объекта между последовательным созданием и прекращением выполнения потоков.

Для получения `CWinThread`дополнительной информации о , см. [статьи Многопоточность с СЗ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Многопоточность: Создание пользователь-интерфейс темы](../../parallel/multithreading-creating-user-interface-threads.md), [Многопоточность: Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md), и [многопоточность: Как использовать классы синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a>CWinThread::CreateThread

Создает поток для выполнения в пределах адресного пространства процесса вызова.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Параметры

*dwCreateFlags*<br/>
Определяет дополнительный флаг, который контролирует создание потока. Этот флаг может содержать одно из двух значений:

- CREATE_SUSPENDED Начать поток с подсчетом приопром 1. Используйте CREATE_SUSPENDED, если вы хотите инициализировать любые данные члена `CWinThread` объекта, такие как [m_bAutoDelete](#m_bautodelete) или любые члены вашего производного класса, до начала работы потока. Как только ваша инициализация будет завершена, используйте [CWinThread::ResumeThread,](#resumethread) чтобы запустить работу потока. Поток не будет `CWinThread::ResumeThread` выполняться до тех пор, пока не будет вызван.

- **0** Запустите поток сразу после создания.

*nStackРазмер*<br/>
Упоняет размер байтов стека для нового потока. Если **0,** размер стека по умолчанию по умолчанию до того же размера, что и основной поток процесса.

*lpSecurityAttrs*<br/>
Указывает на [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) структуру, которая определяет атрибуты безопасности для потока.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если поток создан успешно; в противном случае 0.

### <a name="remarks"></a>Remarks

Используйте `AfxBeginThread` для создания объекта потока и выполнения его в один шаг. Используйте, `CreateThread` если требуется повторное использование объекта потока между последовательным созданием и прекращением выполнения потоков.

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread

Формирует объект `CWinThread`.

```
CWinThread();
```

### <a name="remarks"></a>Remarks

Чтобы начать выполнение потока, позвоните в функцию члена [CreateThread.](#createthread) Обычно вы создаете потоки, позвонив [в AfxBeginThread,](application-information-and-management.md#afxbeginthread)который назовет этот конструктор и `CreateThread`.

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::ExitInstance

Вызывается инфраструктурой из редко переоверченной функции участника [Run](#run) для выхода из этого экземпляра потока или при сбой вызова [InitInstance.](#initinstance)

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Код выхода потока; 0 указывает на отсутствие ошибок, а значения, превышающее 0, указывают на ошибку. Это значение можно получить, позвонив [в GetExitCodeThread.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)

### <a name="remarks"></a>Remarks

Не звоните в эту функцию `Run` участника из любого места, кроме как в функции участника. Эта функция члена используется только в потоках пользовательского интерфейса.

Реализация этой функции по `CWinThread` умолчанию удаляет объект, если [m_bAutoDelete](#m_bautodelete) является правдой. Переопределить эту функцию, если вы хотите выполнить дополнительную очистку, когда поток завершается. Реализация `ExitInstance` должна вызвать версию базового класса после выполнения кода.

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd

Если ваше приложение является сервером OLE, позвоните по этой функции, чтобы получить указатель `m_pMainWnd` на активное основное окно приложения вместо того, чтобы напрямую ссылаться на члена объекта приложения.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает указатель к одному из двух типов окон. Если поток является частью сервера OLE и имеет объект, который находится в месте, активный внутри активного контейнера, эта функция возвращает [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) членданных `CWinThread` данных объекта.

Если в контейнере нет объекта, который находится в месте, или ваше приложение не является сервером OLE, эта функция возвращает [m_pMainWnd](#m_pmainwnd) члену данных объекта потока потока.

### <a name="remarks"></a>Remarks

Для потоков пользователь-интерфейс это эквивалентно непосредственному `m_pActiveWnd` отсылке к члену объекта приложения.

Если ваше приложение не является сервером OLE, то вызов `m_pMainWnd` этой функции эквивалентен непосредственному обращению к члену объекта приложения.

Переизбь эту функцию для изменения поведения по умолчанию.

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThreadPriority

Получает текущий уровень приоритета потока этого потока.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий уровень приоритета потока в своем приоритетном классе. Возвратное значение будет одним из следующих, перечисленных от наивысшего приоритета до самого низкого:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Для получения дополнительной информации об этих приоритетах см. [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в SDK Windows.

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance

`InitInstance`должны быть переопределены для инициализации каждого нового экземпляра потока пользовательского интерфейса.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация является успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Как правило, `InitInstance` переопределение для выполнения задач, которые должны быть завершены при первом создании потока.

Эта функция члена используется только в потоках пользовательского интерфейса. Выполните инициализацию рабочих потоков в функции управления, передаваемых [AfxBeginThread.](application-information-and-management.md#afxbeginthread)

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsIdleMessage

Переопределить эту функцию, чтобы не `OnIdle` вызываться после генерируемых определенных сообщений.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указывает на текущее сообщение, обрабатываемый.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `OnIdle` если следует вызвать после обработки сообщения; в противном случае 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию `OnIdle` не вызывает после избыточных сообщений и сообщений мыши, генерируемых мигающими carets.

Если приложение создало короткий `OnIdle` таймер, будет вызываться часто, вызывая проблемы с производительностью. Чтобы повысить производительность такого приложения, переопределить `IsIdleMessage` `CWinApp`в классе приложения, чтобы проверить WM_TIMER сообщения следующим образом:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Обработка WM_TIMER таким образом, повысит производительность приложений, которые используют короткие таймеры.

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete

Определяется, следует `CWinThread` ли автоматически удалять объект при завершении потока.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Remarks

Член `m_bAutoDelete` данных является общедоступной переменной типа BOOL.

Значение `m_bAutoDelete` не влияет на то, как закрывается основная ручка потока, но влияет на время закрытия ручки. Ручка потока всегда закрывается при уничтожении `CWinThread` объекта.

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a>CWinThread::m_hThread

Ручка к потоку, `CWinThread`прикрепленному к этому.

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Remarks

Член `m_hThread` данных является общедоступной переменной типа HANDLE. Он действителен только в том случае, если основной объект потока ядра в настоящее время существует, а ручка еще не закрыта.

Деструктор CWinThread вызывает CloseHandle на. `m_hThread` Если [m_bAutoDelete](#m_bautodelete) является правдой при завершении потока, объект CWinThread будет уничтожен, что делает недействительными любые указатели на объект CWinThread и переменные его членов. Возможно, члену `m_hThread` потребуется проверить значение выхода потока или дождаться сигнала. Чтобы сохранить объект CWinThread `m_hThread` и его член во время `m_bAutoDelete` выполнения потока и после его завершения, установите false, прежде чем разрешить выполнение потока для продолжения. В противном случае поток может прекратиться, уничтожить объект CWinThread и закрыть ручку, прежде чем пытаться использовать ее. Если вы используете этот метод, вы несете ответственность за удаление объекта CWinThread.

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID

Идентификатор нити, прикрепленный к этому. `CWinThread`

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Remarks

Член `m_nThreadID` данных является общедоступной переменной типа DWORD. Он действителен только в том случае, если основной объект потока ядра в настоящее время существует.
Также смотрите замечания о [m_hThread](#m_hthread) жизни.

### <a name="example"></a>Пример

  Смотрите пример [AfxGetThread](application-information-and-management.md#afxgetthread).

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd

Используйте этот член данных для хранения указателя на активный объект окна вашего потока.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Remarks

Библиотека класса Фонда Майкрософт автоматически прекратит работу потока `m_pActiveWnd` при закрытии окна, о котором идет речь. Если этот поток является основным потоком для приложения, приложение также будет прекращено. Если этот участник данных является NULL, активное окно для `CWinApp` объекта приложения будет унаследовано. `m_pActiveWnd`является публичной переменной типа. `CWnd*`

Как правило, при переопределением `InitInstance`параметра вы устанавливаете эту переменную. В потоке рабочего значение этого члена данных наследуется из родительского потока.

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a>CWinThread::m_pMainWnd

Используйте этот член данных для хранения указателя на основной объект окна потока.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Remarks

Библиотека класса Фонда Майкрософт автоматически прекратит работу потока `m_pMainWnd` при закрытии окна, о котором идет речь. Если этот поток является основным потоком для приложения, приложение также будет прекращено. Если этот член данных является NULL, основное окно для `CWinApp` объекта приложения будет использоваться для определения того, когда следует завершить поток. `m_pMainWnd`является публичной переменной типа. `CWnd*`

Как правило, при переопределением `InitInstance`параметра вы устанавливаете эту переменную. В потоке рабочего значение этого члена данных наследуется из родительского потока.

## <a name="cwinthreadonidle"></a><a name="onidle"></a>CWinThread::Onidle

Переизбь эту функцию участника для выполнения обработки простоя.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Счетчик, приращенный `OnIdle` каждый раз, вызывается, когда очередь сообщений потока пуста. Этот отсчет сбросить до 0 каждый раз, когда обрабатывается новое сообщение. Параметр *lCount* можно использовать для определения относительного времени просеиваемого потока без обработки сообщения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, чтобы получить больше времени простоя обработки; 0, если не требуется больше времени простоя обработки.

### <a name="remarks"></a>Remarks

`OnIdle`вызывается в цикле сообщения по умолчанию, когда очередь сообщения потока пуста. Используйте переопределение, чтобы вызвать свои собственные фоновые задачи обработчика простоя.

`OnIdle`должны вернуть 0, чтобы указать, что дополнительное время обработки простоя не требуется. Параметр *lCount* приращен каждый раз, `OnIdle` когда очередь сообщений пуста и сбросывается до 0 каждый раз, когда обрабатывается новое сообщение. Вы можете вызвать различные процедуры простоя на основе этого подсчета.

Реализация этой функции-члена по умолчанию освобождает временные объекты и неиспользованные библиотеки динамических ссылок из памяти.

Эта функция члена используется только в потоках пользовательского интерфейса.

Поскольку приложение не `OnIdle` может обрабатывать сообщения до возвращения, не выполняйте длительные задачи в этой функции.

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::operator HANDLE

Извлекает ручку `CWinThread` объекта.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, ручка объекта потока; в противном случае, NULL.

### <a name="remarks"></a>Remarks

Используйте ручку для прямого вызова AIS Windows.

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::PostThreadMessage

Вызывается для размещения сообщения с `CWinThread` определенным пользователем другому объекту.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*Сообщение*<br/>
Идентификатор сообщения, определяемого пользователем.

*wParam*<br/>
Параметры первого сообщения.

*lParam*<br/>
Второй параметр сообщения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Размещенное сообщение отображается на соответствующем обработчике сообщений макро-ON_THREAD_MESSAGE карты сообщений.

> [!NOTE]
> При вызове [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)сообщение помещается в очередь сообщений потока. Однако, поскольку сообщения, размещенные таким образом, не связаны с окном, MFC не будет отправлять их обработчикам сообщений или команд. Для обработки этих сообщений `PreTranslateMessage()` переопределить функцию вашего класса, полученного из CWinApp, и обрабатывать сообщения вручную.

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage

Переопределить эту функцию для фильтрации сообщений окон до их отправки на функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage.](/windows/win32/api/winuser/nf-winuser-dispatchmessage)

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указывает на [структуру MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было `PreTranslateMessage` полностью обработано и не должно обрабатываться дальше. Ноль, если сообщение должно быть обработано в обычном режиме.

### <a name="remarks"></a>Remarks

Эта функция члена используется только в потоках пользовательского интерфейса.

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter

Функция крючка платформы вызывает эту функцию участника для фильтрации и реагирования на определенные сообщения Windows.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*Код*<br/>
Определяет код крючка. Эта функция члена использует код для определения того, как обрабатывать *lpMsg.*

*lpMsg*<br/>
Указатель на [структуру Windows MSG.](/windows/win32/api/winuser/ns-winuser-msg)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение обработано; в противном случае 0.

### <a name="remarks"></a>Remarks

Функция крючка обрабатывает события перед их отправкой на обычную обработку сообщений приложения.

Если вы переопределяете эту расширенную функцию, обязательно позвоните в версию базового класса для поддержания обработки крючка.

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::ProcessWndProcException

Платформа вызывает эту функцию элемента всякий раз, когда обработчик не улавливают исключение, брошенное в одном из сообщений потока или обработчиков команд.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*E*<br/>
Указывает на необработанное исключение.

*pMsg*<br/>
Указывает на [структуру MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую информацию о сообщении windows, из-за которой фреймворк может выбросить исключение.

### <a name="return-value"></a>Возвращаемое значение

-1, если создается WM_CREATE исключение; в противном случае 0.

### <a name="remarks"></a>Remarks

Не вызывайте эту функцию участника напрямую.

Реализация этой функции по умолчанию обрабатывает только исключения, генерируемые из следующих сообщений:

|Get-Help|Действие|
|-------------|------------|
|WM_CREATE|Неудача.|
|Wm_paint|Проверка пострадавшего окна, что предотвратит генерирование другого WM_PAINT сообщения.|

Переизобить эту функцию участника, чтобы обеспечить глобальную обработку исключений. Вызовите базовую функциональность только в том случае, если вы хотите отобразить поведение по умолчанию.

Эта функция члена используется только в потоках, которые имеют насос сообщения.

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage

Содержит цикл сообщения потока.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Remarks

`PumpMessage`содержит цикл сообщения потока. `PumpMessage`называется `CWinThread` для перекачки сообщений потока. Вы можете `PumpMessage` вызвать непосредственно, чтобы заставить сообщения `PumpMessage` быть обработаны, или вы можете переопределить изменить свое поведение по умолчанию.

Вызов `PumpMessage` непосредственно и переопределение его поведения по умолчанию рекомендуется только для продвинутых пользователей.

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread::ResumeThread

Вызывается для возобновления выполнения потока, приостановленного функцией участника [SuspendThread,](#suspendthread) или потока, созданного с CREATE_SUSPENDED флагом.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая приостановка потока считается удачной; `0xFFFFFFFF` в противном случае. Если значение возврата равен нулю, текущий поток не был приостановлен. Если значение возврата одно, поток был приостановлен, но теперь перезапущен. Любое значение возврата, превышающее одно, означает, что поток остается приостановленным.

### <a name="remarks"></a>Remarks

Количество приостановите текущего потока уменьшается на один. Если количество приостановки сводится к нулю, поток возобновляет выполнение; в противном случае поток остается приостановленным.

## <a name="cwinthreadrun"></a><a name="run"></a>CWinThread::Run

Обеспечивает цикл сообщения по умолчанию для потоков пользовательского интерфейса.

```
virtual int Run();
```

### <a name="return-value"></a>Возвращаемое значение

Значение **int,** которое возвращается потоком. Это значение можно получить, позвонив [в GetExitCodeThread.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)

### <a name="remarks"></a>Remarks

`Run`приобретает и отправляет сообщения Windows до тех пор, пока приложение не получит [WM_QUIT](/windows/win32/winmsg/wm-quit) сообщение. Если очередь сообщений потока в настоящее время не содержит сообщений, `Run` вызовы `OnIdle` для выполнения обработки простоя. Входящие сообщения переходят в функцию участника [PreTranslateMessage](#pretranslatemessage) для специальной обработки, а затем в функцию Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) для стандартного перевода клавиатуры. Наконец, вызывается функция [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows.

`Run`редко переопределяется, но вы можете переопределить его для реализации специального поведения.

Эта функция члена используется только в потоках пользовательского интерфейса.

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::SetThreadPriority

Эта функция устанавливает уровень приоритета текущего потока в своем приоритетном классе.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Параметры

*nПриоритет*<br/>
Определяет новый уровень приоритета потока в своем приоритетном классе. Этот параметр должен быть одним из следующих значений, перечисленных от наивысшего приоритета до самого низкого:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Для получения дополнительной информации об этих приоритетах см. [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Он может быть вызван только после того, как [CreateThread](#createthread) успешно возвращается.

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::SuspendThread

Приращения отсчета приостановки текущего потока.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая приостановка потока считается удачной; `0xFFFFFFFF` в противном случае.

### <a name="remarks"></a>Remarks

Если какой-либо поток имеет количество приостановки выше нуля, этот поток не выполняется. Поток можно возобновить, позвонив в функцию участника [ResumeThread.](#resumethread)

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
