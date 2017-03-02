---
title: "CWinThread-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinThread
dev_langs:
- C++
helpviewer_keywords:
- worker threads
- threading [MFC], safety
- CWinThread class
- threading [MFC], creating threads
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
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
ms.openlocfilehash: 866e847f9c1d73d6f9882e50b1274fbad9e21a39
ms.lasthandoff: 02/24/2017

---
# <a name="cwinthread-class"></a>CWinThread-класс
Класс, представляющий поток исполнения в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Создает объект `CWinThread`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функцию CWinThread::CreateThread](#createthread)|Начинает выполнение `CWinThread` объекта.|  
|[CWinThread::ExitInstance](#exitinstance)|Переопределение для очистки при завершении работы потока.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Извлекает указатель на главном окне для потока.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Возвращает приоритет текущего потока.|  
|[CWinThread::InitInstance](#initinstance)|Переопределение, чтобы выполнить инициализацию экземпляра для потока.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Проверяет наличие специальных сообщений.|  
|[CWinThread::OnIdle](#onidle)|Переопределение, чтобы выполнить обработку времени простоя для конкретного потока.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Отправляет сообщение в другой `CWinThread` объекта.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Фильтры сообщений перед их отправкой в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенных сообщений, прежде чем они достигнут приложения.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, создаваемые потока сообщений и обработчиков команд.|  
|[CWinThread::PumpMessage](#pumpmessage)|Содержит цикл обработки сообщений потока.|  
|[CWinThread::ResumeThread](#resumethread)|Число приостановок потока уменьшает.|  
|[CWinThread::Run](#run)|Функции управления для потоков в цикл обработки сообщений. Переопределение позволяет настроить цикл обработки сообщений по умолчанию.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Задает приоритет текущего потока.|  
|[CWinThread::SuspendThread](#suspendthread)|Число приостановок шагом a потока.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinThread::operator ДЕСКРИПТОРА](#operator_handle)|Получает дескриптор `CWinThread` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Указывает, следует ли уничтожаемый объект в завершение потока.|  
|[CWinThread::m_hThread](#m_hthread)|Дескриптор текущего потока.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Идентификатор текущего потока.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера, когда сервер OLE является активным на месте.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Содержит указатель на главное окно приложения.|  
  
## <a name="remarks"></a>Примечания  
 Основной поток выполнения обычно предоставляется объект, производный от `CWinApp`; `CWinApp` является производным от `CWinThread`. Дополнительные `CWinThread` объектов разрешить несколько потоков в данном приложении.  
  
 Существует два основных типа потоков, `CWinThread` поддерживает: рабочие потоки и потоки пользовательского интерфейса. Рабочие потоки имеет не обработки сообщений: например, поток, который выполняет вычисления фона в приложение электронной таблицы. Потоки пользовательского интерфейса имеет обработки сообщений и обработки сообщений, получаемых из системы. [CWinApp](../../mfc/reference/cwinapp-class.md) и производные от него классы являются примерами из потоков пользовательского интерфейса. Другие потоки пользовательского интерфейса может также быть прямым производным от `CWinThread`.  
  
 Объекты класса `CWinThread` обычно существуют на протяжении потока. Если вы хотите изменить это поведение, установите [m_bAutoDelete](#m_bautodelete) для **FALSE**.  
  
 `CWinThread` Необходимое для создания кода и MFC полностью потокобезопасного класса. Управляются локальными данными потока, используемым платформой для сохранения информации о потоках `CWinThread` объектов. Из-за этого зависимость от `CWinThread` для обработки локальных данных потока, должны быть созданы любого потока, которое использует MFC с MFC. Например, в потоке, созданном с помощью функции времени выполнения [_beginthread _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) нельзя использовать интерфейсы API MFC.  
  
 Чтобы создать поток, вызовите [AfxBeginThread](application-information-and-management.md#afxbeginthread). Существует две формы, в зависимости от того, требуется ли поток рабочего процесса или пользовательского интерфейса. Поток пользовательского интерфейса следует передать `AfxBeginThread` указатель `CRuntimeClass` из своей `CWinThread`-производного класса. Если вы хотите создать рабочий поток, передать `AfxBeginThread` указатель на функцию управления и параметр для функции управления. Для рабочих потоков и потоков пользовательского интерфейса можно указать необязательные параметры, изменяющие приоритета, размер стека, флаги создания и атрибуты безопасности. `AfxBeginThread`Возвращает указатель на новый `CWinThread` объекта.  
  
 Вместо вызова метода `AfxBeginThread`, можно создать `CWinThread`-производного объекта, а затем вызовите метод `CreateThread`. Этот метод для создания двух этапов полезно, если вы хотите повторно использовать `CWinThread` объекта между последовательными создания и прерывания потока выполнения.  
  
 Дополнительные сведения о `CWinThread`, см. в статьях [многопоточность с помощью C++ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md), [Многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md), и [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecreatethreada--cwinthreadcreatethread"></a><a name="createthread"></a>Функцию CWinThread::CreateThread  
 Создает поток для выполнения в адресном пространстве вызывающего процесса.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCreateFlags`  
 Указывает дополнительный флаг, который управляет созданием потока. Этот флаг может содержать одно из двух значений:  
  
- **CREATE_SUSPENDED** запуска потока с одного счетчик приостановок. Используйте **CREATE_SUSPENDED** чтобы инициализировать любые данные, член `CWinThread` объект, такой как [m_bAutoDelete](#m_bautodelete) или любым членам производного класса, перед началом потока. После завершения своей инициализации использовать [CWinThread::ResumeThread](#resumethread) для запуска выполнения потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.  
  
- **0** запустить поток сразу же после создания.  
  
 `nStackSize`  
 Указывает размер в байтах стека для нового потока. Если **0**, размер стека по умолчанию для того же размера, что и основной поток процесса.  
  
 `lpSecurityAttrs`  
 Указывает [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая задает атрибуты безопасности для потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `AfxBeginThread` создать объект потока или выполнить ее за один шаг. Используйте `CreateThread` , если вы хотите повторно использовать объект thread между последовательными создания и завершения выполнения потока.  
  
##  <a name="a-namecwinthreada--cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread  
 Создает объект `CWinThread`.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы начать выполнение потока, вызовите [CreateThread](#createthread) функции-члена. Обычно создается потоков путем вызова [AfxBeginThread](http://msdn.microsoft.com/library/e9e8684d-24f7-4599-8fdf-1f4f560a753b), который будет вызывать этот конструктор и `CreateThread`.  
  
##  <a name="a-nameexitinstancea--cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::ExitInstance  
 Вызывается платформой из переопределенного редко [запуска](#run) функции-члена для выхода из этого экземпляра потока, или если в вызове [InitInstance](#initinstance) завершается ошибкой.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код выхода потока; 0 указывает без ошибок, а значения больше 0 указывает на ошибку. Это значение можно получить, вызвав [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член из любого места но в **запуска** функции-члена. Эта функция-член используется только в потоках пользовательского интерфейса.  
  
 Реализация по умолчанию эта функция удаляет `CWinThread` объекта, если [m_bAutoDelete](#m_bautodelete) — **TRUE**. Переопределите эту функцию, если вы хотите выполнить дополнительную очистку при завершении потока. Реализация `ExitInstance` после выполнения кода вызова версии базового класса.  
  
##  <a name="a-namegetmainwnda--cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd  
 Если приложение является OLE-сервер, эта функция вызывается для извлечения указателя активное окно основного приложения, а не непосредственно ссылается `m_pMainWnd` член объекта приложения.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает указатель на один из двух типов windows. Если поток является частью OLE-сервер и имеется объект, являющийся активным на месте внутри контейнера active, эта функция возвращает [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) данные-член `CWinThread` объекта.  
  
 Если нет, является активным на месте в контейнере объекта или приложения не является OLE-сервер, эта функция возвращает [m_pMainWnd](#m_pmainwnd) элемент данных объекта потока.  
  
### <a name="remarks"></a>Примечания  
 Для потока пользовательского интерфейса, это эквивалентно непосредственно ссылается `m_pActiveWnd` член объекта приложения.  
  
 Если приложение не является OLE-сервер, то при вызове этой функции является эквивалентом непосредственно ссылается `m_pMainWnd` член объекта приложения.  
  
 Переопределите эту функцию для изменения поведения по умолчанию.  
  
##  <a name="a-namegetthreadprioritya--cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 Возвращает текущий уровень приоритета потока для данного потока.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень приоритета потока внутри класса приоритета. Возвращаемое значение будет иметь одно из следующих действий в списке с высоким приоритетом до самого низкого:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Дополнительные сведения о эти приоритеты в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitinstancea--cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`должен переопределяться для инициализации каждого нового экземпляра потока пользовательского интерфейса.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, необходимо переопределить `InitInstance` для выполнения задач, которые необходимо выполнить при создании потока.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса. Инициализации рабочих потоков, передаваемый функции управления [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="a-nameisidlemessagea--cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 Переопределить эту функцию, чтобы сохранить **OnIdle** вызов после создания определенных сообщений.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указывает на текущее обрабатываемое сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `OnIdle` должен быть вызван после обработки сообщения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не вызывает **OnIdle** после избыточных мыши сообщения и сообщения, создаваемые мигает стрелки.  
  
 Если приложение создано короткий таймер, **OnIdle** будет вызываться часто, причиной проблем производительности. Для повышения производительности для таких приложений, переопределить `IsIdleMessage` в приложении `CWinApp`-производный класс для проверки `WM_TIMER` сообщения следующим образом:  
  
 [!code-cpp[NVC_MFCDocView&#189;](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Обработка `WM_TIMER` таким образом повышает производительность приложений, использующих короткий таймеров.  
  
##  <a name="a-namembautodeletea--cwinthreadmbautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 Указывает, является ли `CWinThread` объекта будет автоматически удален при завершении потока.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bAutoDelete` Член данных — это открытая переменная типа **BOOL**.  
  
 Значение `m_bAutoDelete` не влияет на способ закрытия базовый дескриптор потока. Дескриптор потока всегда закрывается, когда `CWinThread` объект уничтожается.  
  
##  <a name="a-namemhthreada--cwinthreadmhthread"></a><a name="m_hthread"></a>CWinThread::m_hThread  
 Дескриптор потока, присоединенные к этому `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hThread` Член данных — это открытая переменная типа `HANDLE`. Допустимо только если основной поток в настоящее время существует.  
  
##  <a name="a-namemnthreadida--cwinthreadmnthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 Идентификатор потока, присоединенные к этому `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Примечания  
 **M_nThreadID** член данных — это открытая переменная типа `DWORD`. Допустимо только если основной поток в настоящее время существует.  
  
### <a name="example"></a>Пример  
  В примере показано [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="a-namempactivewnda--cwinthreadmpactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 Используйте этот элемент данных для хранения указатель на объект активного окна вашего потока.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation автоматически завершать потока, когда окно ссылается `m_pActiveWnd` закрывается. Если этот поток является основной поток приложения, приложение также прекращается. Если этот член данных — **NULL**, окно активного приложения `CWinApp` объекта наследоваться. `m_pActiveWnd`— это открытая переменная типа **CWnd\***.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. Значение этого элемента данных в рабочем потоке, наследуется от родительского потока.  
  
##  <a name="a-namempmainwnda--cwinthreadmpmainwnd"></a><a name="m_pmainwnd"></a>CWinThread::m_pMainWnd  
 Используйте этот элемент данных для хранения указатель на объект главного окна вашего потока.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation автоматически завершать потока, когда окно ссылается `m_pMainWnd` закрывается. Если этот поток является основной поток приложения, приложение также прекращается. Если этот член данных — **NULL**, главное окно приложения `CWinApp` объекта будет использоваться для определения времени завершения потока. `m_pMainWnd`— это открытая переменная типа **CWnd\***.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. Значение этого элемента данных в рабочем потоке, наследуется от родительского потока.  
  
##  <a name="a-nameonidlea--cwinthreadonidle"></a><a name="onidle"></a>CWinThread::OnIdle  
 Переопределите эту функцию-член для выполнения обработки времени простоя.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Значение счетчика увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений потока пуст. Этот счетчик обнуляется каждый раз при обработке нового сообщения. Можно использовать `lCount` параметр, чтобы определить относительный интервал времени, поток простаивает без обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение для получения более обработки времени простоя; 0, если требуется больше времени простоя обработки.  
  
### <a name="remarks"></a>Примечания  
 `OnIdle`вызывается в цикле обработки сообщений по умолчанию при пустом очереди сообщений потока. Используйте переопределения для вызова свой опыт простоя обработчика задач.  
  
 `OnIdle`Возвращает 0 для указания, что без дополнительной обработки времени простоя не требуется. `lCount` Параметр увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений является пустым и сбрасывается на 0 каждый раз при обработке нового сообщения. Можно вызвать другой простоя подпрограмм на основе этого количества.  
  
 Реализация по умолчанию эта функция-член освобождает временные объекты и неиспользуемые динамических библиотек из памяти.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
 Поскольку приложение не удается обработать сообщения до `OnIdle` возвращает, не выполняют продолжительных задач в этой функции.  
  
##  <a name="a-nameoperatorhandlea--cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::operator ДЕСКРИПТОРА  
 Получает дескриптор `CWinThread` объекта.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха дескриптор объекта потока; в противном случае — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 С помощью маркера напрямую вызывать API-интерфейсов Windows.  
  
##  <a name="a-namepostthreadmessagea--cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 Вызван для учета определенное пользователем сообщение в другой `CWinThread` объекта.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 Идентификатор определяемого пользователем сообщения.  
  
 `wParam`  
 Первый параметр сообщения.  
  
 `lParam`  
 Второй параметр сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Отправленное сообщение сопоставлен обработчик соответствующее сообщение макросом карты сообщение `ON_THREAD_MESSAGE`.  
  
> [!NOTE]
>  При вызове Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) функции в приложении MFC сообщений MFC, обработчики не вызываются. Дополнительные сведения см. в статье базы знаний «PRB: MFC сообщение обработчик не вызывается с PostThreadMessage()» (Q142415).  
  
##  <a name="a-namepretranslatemessagea--cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 Переопределить эту функцию для фильтрации окна сообщений перед их отправкой в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указывает [структурой MSG](../../mfc/reference/msg-structure1.md) содержащий сообщение для обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано полностью в `PreTranslateMessage` и не должна обрабатываться Дополнительно. Нуль, если сообщения должны обрабатываться обычным способом.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
##  <a name="a-nameprocessmessagefiltera--cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 Функция-ловушка framework вызывает эту функцию-член для фильтрации и отвечать на определенные сообщения Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `code`  
 Указывает код обработчика. Эта функция-член использует код для определения способа обработки`lpMsg.`  
  
 `lpMsg`  
 Указатель на Windows [структурой MSG](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-ловушка обрабатывает события перед отправкой сообщения обычного приложения обработки.  
  
 Если переопределить это дополнительная функция, необходимо вызвать версию базового класса для поддержания framework подключить обработки.  
  
##  <a name="a-nameprocesswndprocexceptiona--cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 Платформа вызывает эту функцию-член, всякий раз, когда обработчик не перехватывает исключение, создаваемое в одном из вашего потока сообщений или обработчиков команд.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Указывает необработанное исключение.  
  
 `pMsg`  
 Указывает [структурой MSG](../../mfc/reference/msg-structure1.md) со сведениями о windows сообщения, которое вызвало платформа для создания исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 – 1, если `WM_CREATE` сгенерировано исключение; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать функции-члена напрямую.  
  
 Реализация по умолчанию эта функция-член обрабатывает только те исключения, вызываемые из следующих сообщений:  
  
|Команда|Действие|  
|-------------|------------|  
|`WM_CREATE`|Сбой.|  
|`WM_PAINT`|Проверьте затронутые окна, предотвращая другой `WM_PAINT` Создание сообщения.|  
  
 Переопределите эту функцию-член для предоставления глобального обработки исключений. Вызовите базовую функциональность, только в том случае, если вы хотите отобразить поведение по умолчанию.  
  
 Эта функция-член используется только в потоках, которые содержит цикл обработки сообщений.  
  
##  <a name="a-namepumpmessagea--cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage  
 Содержит цикл обработки сообщений потока.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Примечания  
 `PumpMessage`содержит цикл обработки сообщений потока. **PumpMessage** вызывается `CWinThread` для переноса потока сообщений. Можно вызвать `PumpMessage` непосредственно заставить сообщения должны обрабатываться или может переопределить `PumpMessage` для изменения поведения по умолчанию.  
  
 Вызов `PumpMessage` напрямую и переопределение поведения по умолчанию рекомендуется только опытным пользователям.  
  
##  <a name="a-nameresumethreada--cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread::ResumeThread  
 Чтобы возобновить выполнение потока, который был приостановлен, [SuspendThread](#suspendthread) функции-члена или в потоке, созданном с **CREATE_SUSPENDED** флаг.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count в случае успешного выполнения; `0xFFFFFFFF` в противном случае. Если возвращаемое значение равно нулю, то текущий поток не было приостановлено. Если возвращаемое значение&1;, поток был приостановлен, но теперь перезапускается. Возвращаемое значение, превышающее означает один поток приостанавливается.  
  
### <a name="remarks"></a>Примечания  
 Счетчик приостановки текущего потока уменьшается на единицу. Если уменьшить счетчик приостановок, равное нулю, поток возобновляет выполнение; в противном случае поток приостанавливается.  
  
##  <a name="a-nameruna--cwinthreadrun"></a><a name="run"></a>CWinThread::Run  
 Обеспечивает цикла сообщений по умолчанию для потоков пользовательского интерфейса.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `int` Значение, возвращенное методом потока. Это значение можно получить, вызвав [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Примечания  
 **Запустите** получает и отправляет сообщения Windows, пока приложение не получит [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) сообщений. Если очередь сообщений потока в настоящее время не содержит сообщений, **запуска** вызовов `OnIdle` для выполнения обработки времени простоя. Входящие сообщения попадают в [PreTranslateMessage](#pretranslatemessage) функции-члена для специальной обработки, а затем в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) для перевода стандартную клавиатуру. Наконец [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) вызывается функция Windows.  
  
 **Запустите** переопределяется редко, но его можно переопределить для реализации особого поведения.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
##  <a name="a-namesetthreadprioritya--cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 Эта функция задает уровень приоритета текущего потока, внутри своего класса приоритета.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Параметры  
 `nPriority`  
 Задает новый уровень приоритета потока внутри класса приоритета. Этот параметр должен иметь одно из следующих значений, перечисленных с высоким приоритетом до самого низкого:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Дополнительные сведения о эти приоритеты в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Может вызываться только после [CreateThread](#createthread) успешно возвращает.  
  
##  <a name="a-namesuspendthreada--cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::SuspendThread  
 Увеличивает текущий счетчик приостановок потока.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count в случае успешного выполнения; `0xFFFFFFFF` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если любой поток имеет счетчик приостановок выше нуля, этот поток не выполняется. Поток можно возобновить путем вызова [ResumeThread](#resumethread) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)

