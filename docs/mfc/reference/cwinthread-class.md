---
title: CWinThread-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 115b351ccbaf9c8c5cbccb0004d04c53e54351ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123068"
---
# <a name="cwinthread-class"></a>CWinThread-класс
Класс, представляющий поток исполнения в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Создает объект `CWinThread`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Функцию CWinThread::CreateThread](#createthread)|Начинает выполнение `CWinThread` объекта.|  
|[CWinThread::ExitInstance](#exitinstance)|Переопределение для очистки после завершения вашего потока.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Извлекает указатель на главное окно для потока.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Возвращает приоритет текущего потока.|  
|[CWinThread::InitInstance](#initinstance)|Переопределите, чтобы выполнить инициализацию экземпляра для потока.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Проверяет наличие специальных сообщений.|  
|[CWinThread::OnIdle](#onidle)|Переопределите, чтобы выполнить обработку времени простоя для конкретного потока.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Отправляет сообщение в другой `CWinThread` объекта.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Фильтрует сообщения перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенных сообщений, прежде чем они достигнут приложения.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, вызванные потока сообщений и обработчики команд.|  
|[CWinThread::PumpMessage](#pumpmessage)|Содержит цикл обработки сообщений потока.|  
|[CWinThread::ResumeThread](#resumethread)|Число приостановок уменьшает потока.|  
|[CWinThread::Run](#run)|Функции управления для потоков с цикл обработки сообщений. Переопределите, чтобы настроить цикл обработки сообщений по умолчанию.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Задает приоритет текущего потока.|  
|[CWinThread::SuspendThread](#suspendthread)|Число приостановок с шагом a потока.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinThread::operator ДЕСКРИПТОРА](#operator_handle)|Извлекает дескриптор `CWinThread` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Указывает необходимость уничтожения объектов на завершение потока.|  
|[CWinThread::m_hThread](#m_hthread)|Дескриптор текущего потока.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Идентификатор текущего потока.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера при активен OLE-сервер на месте.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Содержит указатель на главное окно приложения.|  
  
## <a name="remarks"></a>Примечания  
 Основной поток выполнения обычно предоставляется с помощью объекта, производного от `CWinApp`; `CWinApp` является производным от `CWinThread`. Дополнительные `CWinThread` объекты позволяют несколько потоков внутри данного приложения.  
  
 Существует два основных типа потоков, `CWinThread` поддерживает: рабочих потоков и потоков пользовательского интерфейса. Рабочие потоки имеет не обработки сообщений: например, поток, который выполняет вычисление фона в приложениях электронных таблиц. Потоки пользовательского интерфейса содержит цикл обработки сообщений и обработки сообщений, получаемых из системы. [CWinApp](../../mfc/reference/cwinapp-class.md) и классы, производные от него являются примерами потоков пользовательского интерфейса. Другие потоки пользовательского интерфейса могут также быть прямым производным от `CWinThread`.  
  
 Объекты класса `CWinThread` обычно существует до конца потока. Если вы хотите изменить это поведение, задайте [m_bAutoDelete](#m_bautodelete) значение FALSE.  
  
 `CWinThread` Необходимое для создания кода и MFC полностью потокобезопасного класса. Управляет локальными данными потока используется платформой для сохранения сведений о потоках `CWinThread` объектов. Из-за этой зависимости между `CWinThread` для обработки данных, локальных для потока, должна быть создана любого потока, которое использует MFC с MFC. Например, в потоке, созданном с помощью функции времени выполнения [_beginthread и _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) нельзя использовать интерфейсы API MFC.  
  
 Чтобы создать поток, вызовите [AfxBeginThread](application-information-and-management.md#afxbeginthread). Существует две формы, в зависимости от того, нужно ли поток рабочего процесса или пользовательского интерфейса. Если требуется, чтобы поток пользовательского интерфейса, передать `AfxBeginThread` указатель на `CRuntimeClass` из вашей `CWinThread`-производного класса. Если вы хотите создать рабочий поток, передать `AfxBeginThread` указатель на функцию управления и параметр для функции управления. Для рабочих потоков и потоков пользовательского интерфейса можно указать необязательные параметры, изменяющие приоритет, размер стека, флаги создания и атрибуты безопасности. `AfxBeginThread` Возвращает указатель на новый `CWinThread` объекта.  
  
 Вместо вызова метода `AfxBeginThread`, можно создать `CWinThread`-производного объекта, а затем вызовите метод `CreateThread`. Этот метод создания двухэтапное полезно, если требуется повторно использовать `CWinThread` объекта между последовательными создания и завершения выполнения потока.  
  
 Дополнительные сведения о `CWinThread`, см. в статьях [многопоточность с помощью C++ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md), [Многопоточность: создание рабочих Потоки](../../parallel/multithreading-creating-worker-threads.md), и [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="createthread"></a>  Функцию CWinThread::CreateThread  
 Создает поток для выполнения в адресном пространстве вызывающего процесса.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *dwCreateFlags*  
 Указывает дополнительный флаг, которое контролирует создание потока. Этот флаг может содержать одно из двух значений:  
  
- CREATE_SUSPENDED запуска потока с одного счетчик приостановок. Используйте CREATE_SUSPENDED, если необходимо инициализировать все данные-член `CWinThread` объект, такой как [m_bAutoDelete](#m_bautodelete) или любым членам производного класса, перед началом потока. После инициализации вашей используйте [CWinThread::ResumeThread](#resumethread) для запуска выполнения потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.  
  
- **0** запустить поток сразу после создания.  
  
 *nStackSize*  
 Указывает размер в байтах стека для нового потока. Если **0**, размер стека по умолчанию используется тот же размер, что и основной поток процесса.  
  
 *lpSecurityAttrs*  
 Указывает на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая задает атрибуты безопасности для потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `AfxBeginThread` создать объект потока или выполнить ее за один шаг. Используйте `CreateThread` , если требуется повторно использовать объект потока между последовательными создания и завершения выполнения потока.  
  
##  <a name="cwinthread"></a>  CWinThread::CWinThread  
 Создает объект `CWinThread`.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы начать выполнение потока, вызовите [CreateThread](#createthread) функции-члена. Потоки будут обычно создается путем вызова [AfxBeginThread](application-information-and-management.md#afxbeginthread), который вызывает этот конструктор и `CreateThread`.  
  
##  <a name="exitinstance"></a>  CWinThread::ExitInstance  
 Вызывается платформой от переопределенного редко [запуска](#run) функции-члена для выхода из этого экземпляра потока, или если вызов [InitInstance](#initinstance) завершается ошибкой.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код завершения потока; 0 указывает без ошибок, а значения больше 0 указывает на ошибку. Это значение можно получить путем вызова [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член в любом месте но в `Run` функции-члена. Эта функция-член используется только в потоках пользовательского интерфейса.  
  
 Реализация по умолчанию эта функция удаляет `CWinThread` объекта, если [m_bAutoDelete](#m_bautodelete) имеет значение TRUE. Переопределите эту функцию, если необходимо выполнить дополнительные очистки при прекращении потока. Реализация `ExitInstance` после выполнения кода вызова версии базового класса.  
  
##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd  
 Если приложение является OLE-сервер, эта функция вызывается для получения указатель active главного окна приложения, а не непосредственно ссылается на `m_pMainWnd` член объекта приложения.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает указатель на один из двух типов windows. Если поток является частью OLE-сервер и содержит объект, который активен на месте в пределах контейнера active, эта функция возвращает [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) данными-членом `CWinThread` объекта.  
  
 Если нет объекта, который активен на месте в контейнере или приложения не является OLE-сервер, эта функция возвращает [m_pMainWnd](#m_pmainwnd) элемент данных объекта потока.  
  
### <a name="remarks"></a>Примечания  
 Для потока пользовательского интерфейса, это эквивалентно непосредственно ссылается на `m_pActiveWnd` членом объекта приложения.  
  
 Если приложение не является сервером OLE, то при вызове этой функции является эквивалентом непосредственно ссылается на `m_pMainWnd` членом объекта приложения.  
  
 Переопределите эту функцию для изменения поведения по умолчанию.  
  
##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority  
 Возвращает текущий уровень приоритета потока для данного потока.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень приоритета потока внутри класса приоритета. Возвращаемое значение будет иметь одно из следующих значений в списке с высоким приоритетом до самого низкого:  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- ВСЕХ  
  
- THREAD_PRIORITY_IDLE  
  
 Дополнительные сведения об эти приоритеты см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в Windows SDK.  
  
##  <a name="initinstance"></a>  CWinThread::InitInstance  
 `InitInstance` должен быть переопределен для инициализации каждого нового экземпляра потока пользовательского интерфейса.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, можно переопределить `InitInstance` для выполнения задач, которые необходимо выполнить при создании потока.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса. Выполнить инициализацию рабочих потоков в функцию управления передан [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage  
 Переопределить эту функцию, чтобы сохранить `OnIdle` вызова после создания специальных сообщений.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pMsg*  
 Указывает текущее сообщение обрабатывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `OnIdle` следует вызывать после обработки сообщения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не вызывает `OnIdle` после избыточных мыши сообщения и сообщения, созданные мигает стрелки.  
  
 Если приложение уже создано короткий таймер `OnIdle` будет вызываться часто причиной проблем производительности. Для повышения производительности таких приложений, переопределить `IsIdleMessage` в приложении `CWinApp`-производный класс для проверки сообщений WM_TIMER следующим образом:  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Обработка WM_TIMER таким образом улучшит производительность приложений, использующих короткий таймеров.  
  
##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete  
 Указывает, является ли `CWinThread` объекта должны автоматически удаляться при завершении потока.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bAutoDelete` Член данных — это открытая переменная типа BOOL.  
  
 Значение `m_bAutoDelete` не влияет на способ закрытия базовый дескриптор потока. Дескриптор потока всегда закрывается, когда `CWinThread` объект удаляется.  
  
##  <a name="m_hthread"></a>  CWinThread::m_hThread  
 Дескриптор потока, прикрепленный к этому `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hThread` Член данных — это открытая переменная типа ДЕСКРИПТОРА. Он допустим, только если основной поток в настоящее время существует.  
  
##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID  
 Идентификатор потока, прикрепленный к этому `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_nThreadID` Член данных — это открытая переменная типа DWORD. Он допустим, только если основной поток в настоящее время существует.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd  
 Используйте этот элемент данных для хранения указателя на объект вашего потока активного окна.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation будет прекращен автоматически потока, когда окно ссылается `m_pActiveWnd` закрыт. Если этот поток является основного потока приложения, приложение также прекращается. Если этот элемент данных имеет значение NULL, окна для приложения `CWinApp` объекта будут унаследованы. `m_pActiveWnd` — это открытая переменная типа `CWnd*`.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. Значение этого элемента данных в рабочем потоке, наследуется от родительского потока.  
  
##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd  
 Используйте этот элемент данных для хранения указателя на объект основного окна вашего потока.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation будет прекращен автоматически потока, когда окно ссылается `m_pMainWnd` закрыт. Если этот поток является основного потока приложения, приложение также прекращается. Если этот элемент данных имеет значение NULL, главного окна приложения `CWinApp` объект будет использоваться для определения времени завершения потока. `m_pMainWnd` — это открытая переменная типа `CWnd*`.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. Значение этого элемента данных в рабочем потоке, наследуется от родительского потока.  
  
##  <a name="onidle"></a>  CWinThread::OnIdle  
 Переопределите эту функцию-член для выполнения обработки времени простоя.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Параметры  
 *lCount*  
 Счетчик увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений потока пуст. Этот счетчик обнуляется каждый раз при обработке нового сообщения. Можно использовать *lCount* параметра, чтобы определить относительный интервал времени, поток находился в ждущем режиме без обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, для получения более обработки время простоя; 0, если требуется больше простоя время обработки.  
  
### <a name="remarks"></a>Примечания  
 `OnIdle` вызывается в цикле обработки сообщений по умолчанию при потока сообщений очередь пуста. Используйте переопределения для вызова свой опыт простоя обработчика задачи.  
  
 `OnIdle` должен возвращать 0, чтобы указать на нет дополнительное время обработки простоя. *LCount* параметр увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений является пустым и обнуляется каждый раз при обработке нового сообщения. Можно вызвать в разные процедуры простоя, на основе этого количества.  
  
 Реализация по умолчанию эта функция-член освобождает временные объекты и неиспользуемые динамических библиотек из памяти.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
 Поскольку приложение не может обрабатывать сообщения до `OnIdle` возвращает, не выполняйте продолжительных задач в этой функции.  
  
##  <a name="operator_handle"></a>  CWinThread::operator ДЕСКРИПТОРА  
 Извлекает дескриптор `CWinThread` объекта.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения, дескриптор объекта потока. в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 С помощью маркера для прямого вызова API-интерфейсов Windows.  
  
##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage  
 Вызван для публикации определяемые пользователем сообщения на другой `CWinThread` объекта.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 *message*  
 Идентификатор определяемого пользователем сообщения.  
  
 *wParam*  
 Первый параметр сообщения.  
  
 *lParam*  
 Второй параметр сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Отправленное сообщение сопоставляется обработчик сообщений на правильную ON_THREAD_MESSAGE макрос карты сообщений.  
  
> [!NOTE]
>  При вызове Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) функции в приложении MFC сообщений MFC, обработчиками не вызываются. Дополнительные сведения см. в статье базы знаний «PRB: MFC сообщение обработчик не вызывается с PostThreadMessage()» (Q142415).  
  
##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage  
 Переопределить эту функцию для фильтрации сообщений окна перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pMsg*  
 Указывает на [структура MSG](../../mfc/reference/msg-structure1.md) , содержащее сообщение для обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано полностью в `PreTranslateMessage` и не должны обрабатываться Дополнительно. Нуль, если сообщения должны обрабатываться обычным способом.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter  
 Функция-ловушка framework вызывает эту функцию-член для фильтрации и реагировать на некоторые сообщения Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *Код*  
 Указывает код обработчика. Эта функция-член использует код, чтобы определить способ обработки *lpMsg.*  
  
 *lpMsg*  
 Указатель на Windows [структура MSG](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-ловушка обрабатывает события перед их отправкой в обычное сообщение приложения обработки.  
  
 Если переопределить это дополнительная возможность, необходимо вызвать версии базового класса для обеспечения framework подключить обработки.  
  
##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException  
 Эта функция-член вызывается платформой, каждый раз, когда обработчик не перехватывает исключение, создаваемое в одном из вашего потока сообщений или обработчики команд.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Указывает необработанное исключение.  
  
 *pMsg*  
 Указывает на [структура MSG](../../mfc/reference/msg-structure1.md) содержащий сведения о windows сообщения, которое вызвало платформа для создания исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 значение -1, если создается исключение WM_CREATE; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член напрямую.  
  
 Реализация по умолчанию эта функция-член обрабатывает только те исключения, вызываемые из следующих сообщений:  
  
|Команда|Действие|  
|-------------|------------|  
|WM_CREATE|Сбой.|  
|WM_PAINT|Проверьте Затронутое окно, предотвращая создание другого сообщения WM_PAINT.|  
  
 Переопределите эту функцию-член для предоставления глобальных обработки свои исключения. Вызовите базовую функциональность, только в том случае, если нужно отобразить поведение по умолчанию.  
  
 Эта функция-член используется только в потоки, которые содержит цикл обработки сообщений.  
  
##  <a name="pumpmessage"></a>  CWinThread::PumpMessage  
 Содержит цикл обработки сообщений потока.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Примечания  
 `PumpMessage` содержит цикл обработки сообщений потока. `PumpMessage` вызывается методом `CWinThread` для приема-передачи потока сообщений. Можно вызвать `PumpMessage` непосредственно для принудительного сообщения должны обрабатываться или переопределить `PumpMessage` для изменения поведения по умолчанию.  
  
 Вызов `PumpMessage` напрямую и переопределение поведения по умолчанию рекомендуется только опытным пользователям.  
  
##  <a name="resumethread"></a>  CWinThread::ResumeThread  
 Вызывается, чтобы возобновить выполнение потока, который был приостановлен, [SuspendThread](#suspendthread) функции-члена или в потоке, созданном с помощью флага CREATE_SUSPENDED.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count в случае успешного выполнения; `0xFFFFFFFF` в противном случае. Если возвращаемое значение равно нулю, что текущий поток не было приостановлено. Если возвращаемое значение 1, поток был приостановлен, но теперь перезапускается. Возвращаемое значение, превышающее означает один поток остается в приостановленном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Счетчик приостановки текущего потока уменьшается на единицу. Если счетчик приостановок уменьшается до нуля, что поток возобновляет выполнение; в противном случае поток остается в приостановленном состоянии.  
  
##  <a name="run"></a>  CWinThread::Run  
 Обеспечивает цикла сообщений по умолчанию для потоков пользовательского интерфейса.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Int** значение, возвращаемое из потока. Это значение можно получить путем вызова [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Примечания  
 `Run` Получает и отправляет сообщения Windows, пока приложение не получит [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) сообщения. Если очередь сообщений потока в настоящее время не содержит сообщений, `Run` вызовы `OnIdle` для выполнения обработки времени простоя. Входящие сообщения попадают в [PreTranslateMessage](#pretranslatemessage) функции-члена для специальной обработки, а затем для функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) для перевода на стандартной клавиатуре. Наконец [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функция Windows.  
  
 `Run` переопределяется редко, но его можно переопределить для реализации особое поведение.  
  
 Эта функция-член используется только в потоках пользовательского интерфейса.  
  
##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority  
 Эта функция задает уровень приоритета текущего потока, внутри класса приоритета.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Параметры  
 *nPriority*  
 Указывает новый уровень приоритета потока внутри класса приоритета. Этот параметр должен иметь одно из следующих значений, перечисленных с высоким приоритетом до самого низкого:  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- ВСЕХ  
  
- THREAD_PRIORITY_IDLE  
  
 Дополнительные сведения об эти приоритеты см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Он может быть вызван только после [CreateThread](#createthread) успешно возвращает.  
  
##  <a name="suspendthread"></a>  CWinThread::SuspendThread  
 Увеличивает значение текущего счетчика приостановок потока.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count в случае успешного выполнения; `0xFFFFFFFF` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если любой поток имеет счетчик приостановок выше нуля, то не будет выполняться. Поток может быть возобновлено при вызове [ResumeThread](#resumethread) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
