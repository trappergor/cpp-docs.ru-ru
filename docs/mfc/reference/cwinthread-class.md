---
title: Класс CWinThread | Документация Майкрософт
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
ms.openlocfilehash: 784425246c3be99acde2942633ce5190807c59b4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689562"
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
|[CWinThread::CWinThread](#cwinthread)|Создает объект `CWinThread`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функцию CWinThread::CreateThread](#createthread)|Начинает выполнение `CWinThread` объекта.|  
|[CWinThread::ExitInstance](#exitinstance)|Переопределение для очистки при завершении потока.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Извлекает указатель на главное окно для потока.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Получает приоритет текущего потока.|  
|[CWinThread::InitInstance](#initinstance)|Переопределение для инициализации экземпляра потока.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Проверяет наличие специальных сообщений.|  
|[CWinThread::OnIdle](#onidle)|Переопределение для выполнения обработки времени простоя определенного потока.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Отправляет сообщение в другой `CWinThread` объекта.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Фильтрует сообщения перед их отправкой в функции Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенных сообщений, прежде чем они достигнут приложения.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, порождаемые потока сообщений и обработчиков команд.|  
|[CWinThread::PumpMessage](#pumpmessage)|содержит цикл обработки сообщений потока.|  
|[CWinThread::ResumeThread](#resumethread)|Счетчик приостановок уменьшающийся потока.|  
|[CWinThread::Run](#run)|Управление функции для потоков с помощью механизма обработки сообщений. Переопределите, чтобы настроить цикл обработки сообщений по умолчанию.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Задает приоритет текущего потока.|  
|[CWinThread::SuspendThread](#suspendthread)|Счетчик приостановок с шагом a потока.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinThread::operator ДЕСКРИПТОР](#operator_handle)|Извлекает дескриптор `CWinThread` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Указывает, следует ли уничтожать объект, находящийся в завершение потока.|  
|[CWinThread::m_hThread](#m_hthread)|Дескриптор текущего потока.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Идентификатор текущего потока.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера при OLE-сервер активен на месте.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Содержит указатель на главное окно приложения.|  
  
## <a name="remarks"></a>Примечания  
 Основной поток выполнения обычно предоставляется объект, производный от `CWinApp`; `CWinApp` является производным от `CWinThread`. Дополнительные `CWinThread` объекты обеспечивают несколько потоков в данном приложении.  
  
 Существуют два основных типа потоков, `CWinThread` поддерживает: рабочие потоки и потоки пользовательского интерфейса. Рабочие потоки имеет не обработки сообщений: например, поток, который выполняет вычисления фона в приложение электронных таблиц. Потоки пользовательского интерфейса содержит цикл обработки сообщений и обрабатывать сообщения, полученные из системы. [CWinApp](../../mfc/reference/cwinapp-class.md) и классы, производные от него являются примерами из потоков пользовательского интерфейса. Другие потоки пользовательского интерфейса может также быть прямым производным от `CWinThread`.  
  
 Объекты класса `CWinThread` обычно существуют во время потока. Если вы хотите изменить это поведение, задайте [m_bAutoDelete](#m_bautodelete) значение false.  
  
 `CWinThread` Класса необходим сделать код и MFC полностью потокобезопасными. Управляет локальными данными потока, используемая платформой для сохранения данных определенного потока `CWinThread` объектов. Из-за этого зависимость от `CWinThread` любого потока, которое использует MFC для обработки локальными данными потока, должны создаваться с MFC. Например, в потоке, созданном с помощью функции времени выполнения [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) нельзя использовать любые интерфейсы API MFC.  
  
 Чтобы создать поток, вызовите [AfxBeginThread](application-information-and-management.md#afxbeginthread). Существует две формы, в зависимости от того, нужно ли поток рабочего процесса или пользовательского интерфейса. Если требуется, чтобы поток пользовательского интерфейса, передать `AfxBeginThread` указатель на `CRuntimeClass` из вашей `CWinThread`-производного класса. Если вы хотите создать рабочий поток, передать `AfxBeginThread` указатель на функцию управления, а параметр функции управления. Для рабочих потоков и потоков пользовательского интерфейса можно указать необязательные параметры, которые изменяют приоритета, размер стека, флаги создания и атрибуты безопасности. `AfxBeginThread` Возвращает указатель на новый `CWinThread` объекта.  
  
 Вместо вызова метода `AfxBeginThread`, можно создать `CWinThread`-производного объекта, а затем вызовите метод `CreateThread`. Этот метод конструкции двухэтапное полезен, если вы хотите повторно использовать `CWinThread` объекта между последовательными создания и прерывания потока выполнения.  
  
 Дополнительные сведения о `CWinThread`, см. в статьях [многопоточность с помощью C++ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md), [Многопоточность: Создание рабочей роли Потоки](../../parallel/multithreading-creating-worker-threads.md), и [многопоточности: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
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
 Задает дополнительный флажок, контролирующий создание потока. Этот флаг может содержать одно из двух значений:  
  
- CREATE_SUSPENDED запускает поток со счетчик приостановок одного. Используйте CREATE_SUSPENDED, если вы хотите инициализировать данные члена объекта `CWinThread` объект, например [m_bAutoDelete](#m_bautodelete) или любого члена производного класса, до запуска потока. После завершения инициализации использовать [CWinThread::ResumeThread](#resumethread) для запуска потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.  
  
- **0** запустить поток сразу после создания.  
  
 *nStackSize*  
 Указывает размер в байтах стека для нового потока. Если **0**, размер стека по умолчанию в соответствии с размером, что и основной поток процесса.  
  
 *lpSecurityAttrs*  
 Указывает на [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) структура, задающая атрибуты безопасности для потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `AfxBeginThread` создать объект потока, или выполнить ее за один шаг. Используйте `CreateThread` Если вы хотите повторно использовать объект потока между последовательными создания и завершения выполнения потока.  
  
##  <a name="cwinthread"></a>  CWinThread::CWinThread  
 Создает объект `CWinThread`.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы начать выполнение потока, вызовите [CreateThread](#createthread) функция-член. Обычно создается потоков, вызвав [AfxBeginThread](application-information-and-management.md#afxbeginthread), который будет вызывать этот конструктор и `CreateThread`.  
  
##  <a name="exitinstance"></a>  CWinThread::ExitInstance  
 Вызывается платформой из в редко переопределенный [запуска](#run) функцию-член для выхода из этого экземпляра потока, или если в вызове [InitInstance](#initinstance) завершается ошибкой.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код выхода потока; 0 указывает без ошибок, а значения больше 0 указывает на ошибку. Это значение можно получить, вызвав [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член из любого места но в `Run` функция-член. Эта функция-член используется только в потоки пользовательского интерфейса.  
  
 Реализация по умолчанию эта функция удаляет `CWinThread` Если [m_bAutoDelete](#m_bautodelete) имеет значение TRUE. Переопределите эту функцию, если вы хотите выполнять дополнительная Очистка, когда ваш поток завершается. Реализация `ExitInstance` должны вызывать версии базового класса, после выполнения кода.  
  
##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd  
 Если приложение является OLE-сервер, вызовите эту функцию для получения указатель active главное окно приложения, а не непосредственно ссылается на `m_pMainWnd` члена объекта приложения.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает указатель на один из двух видов windows. Если поток является частью OLE-сервер и объект, который активен на месте внутри контейнера active, эта функция возвращает [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) данными-членом `CWinThread` объекта.  
  
 Если отсутствует объект, который активен на месте в контейнере или приложение не является OLE-сервер, эта функция возвращает [m_pMainWnd](#m_pmainwnd) элемент данных объекта потока.  
  
### <a name="remarks"></a>Примечания  
 Для потоков пользовательского интерфейса, это эквивалентно непосредственно ссылается на `m_pActiveWnd` членом объекта приложения.  
  
 Если приложение не является OLE-сервер, то вызов этой функции эквивалентно непосредственно ссылается на `m_pMainWnd` членом объекта приложения.  
  
 Переопределите эту функцию для изменения поведения по умолчанию.  
  
##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority  
 Получает текущий уровень приоритета потока данного потока.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень приоритета потока из соответствующего класса приоритета. Возвращаемое значение будет иметь одно из следующих значений, перечисленных от наиболее важных до самого низкого:  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- НАИНИЗШИЙ  
  
- THREAD_PRIORITY_IDLE  
  
 Дополнительные сведения о эти приоритеты, см. в разделе [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в пакете Windows SDK.  
  
##  <a name="initinstance"></a>  CWinThread::InitInstance  
 `InitInstance` должен переопределяться для инициализации каждого нового экземпляра потока пользовательского интерфейса.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, можно переопределить `InitInstance` для выполнения задач, которые необходимо выполнить при создании потока.  
  
 Эта функция-член используется только в потоки пользовательского интерфейса. Выполнить инициализацию рабочих потоков в функцию управления, передаваемый [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage  
 Переопределите эту функцию, чтобы сохранить `OnIdle` вызов после создания специальных сообщений.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pMsg*  
 Указывает на текущее обрабатываемое сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение `OnIdle` должна вызываться после обработки сообщения; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не вызывает `OnIdle` после избыточных мыши сообщения и сообщения, создаваемые мигает крышки.  
  
 Если приложение уже создано короткий таймера, `OnIdle` будет вызываться часто причиной проблем производительности. Для повышения производительности такого приложения в Переопределите `IsIdleMessage` в приложения `CWinApp`-производный класс на наличие сообщения WM_TIMER следующим образом:  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Обработка WM_TIMER таким образом, улучшит производительность приложений, использующих короткий таймеры.  
  
##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete  
 Указывает, является ли `CWinThread` объекта будет автоматически удален при завершении потока.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bAutoDelete` Данные-член — это открытая переменная типа BOOL.  
  
 Значение `m_bAutoDelete` не влияет на способ закрытия базовый дескриптор потока. Дескриптор потока всегда закрывается, когда `CWinThread` уничтожении объекта.  
  
##  <a name="m_hthread"></a>  CWinThread::m_hThread  
 Дескриптор потока, прикрепленный к этому `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hThread` Данные-член — это открытая переменная типа ДЕСКРИПТОРА. Он допустим только если базовый поток в настоящее время существует.  
  
##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID  
 Идентификатор потока, прикрепленный к этому `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_nThreadID` Данные-член — это открытая переменная типа DWORD. Он допустим только если базовый поток в настоящее время существует.  
  
### <a name="example"></a>Пример  
  См. в примере [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd  
 Используйте этот элемент данных для хранения указатель на объект в поток активного окна.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки Microsoft Foundation Class будет автоматически завершена потока, когда окно ссылается `m_pActiveWnd` закрыт. Если этот поток является основным потоком для приложения, приложения также будут завершены. Если этот элемент данных имеет значение NULL, активное окно для приложения `CWinApp` объекта будут унаследованы. `m_pActiveWnd` — это открытая переменная типа `CWnd*`.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. В рабочем потоке значение этого члена данных наследуется от родительского потока.  
  
##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd  
 Этот элемент данных можно используйте для хранения указателя на объект основного окна ваш поток.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки Microsoft Foundation Class будет автоматически завершена потока, когда окно ссылается `m_pMainWnd` закрыт. Если этот поток является основным потоком для приложения, приложения также будут завершены. Если этот элемент данных имеет значение NULL, главное окно приложения `CWinApp` объекта будет использоваться, чтобы определить, когда на завершение потока. `m_pMainWnd` — это открытая переменная типа `CWnd*`.  
  
 Как правило, задать переменную-член при переопределении `InitInstance`. В рабочем потоке значение этого члена данных наследуется от родительского потока.  
  
##  <a name="onidle"></a>  CWinThread::OnIdle  
 Переопределите эта функция-член для выполнения обработки времени простоя.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Параметры  
 *lCount*  
 Значение счетчика увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений потока пуст. Этот счетчик обнуляется каждый раз при обработке нового сообщения. Можно использовать *lCount* параметр, чтобы определить относительный продолжительность времени, поток бездействует без обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, чтобы получать более обработки время простоя; 0, если потребуется больше времени простоя обработки.  
  
### <a name="remarks"></a>Примечания  
 `OnIdle` функция вызывается в цикл обработки сообщений по умолчанию, когда очередь сообщений потока пуста. Используйте переопределение для вызова свой опыт простоя обработчика задач.  
  
 `OnIdle` должен возвращать 0, чтобы указать, что нет дополнительное время обработки бездействующих является обязательным. *LCount* параметр увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений является пустым и обнуляется каждый раз при обработке нового сообщения. Можно вызвать в разных простоя подпрограммы, исходя из этого числа.  
  
 Реализация по умолчанию эта функция-член освобождает временные объекты и неиспользуемые динамических библиотек из памяти.  
  
 Эта функция-член используется только в потоки пользовательского интерфейса.  
  
 Поскольку приложение не может обработать сообщения до `OnIdle` возвращает, не выполняйте упрощения продолжительных задач в этой функции.  
  
##  <a name="operator_handle"></a>  CWinThread::operator ДЕСКРИПТОР  
 Извлекает дескриптор `CWinThread` объекта.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения дескриптор объекта потока; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Используйте дескриптор напрямую вызывать интерфейсы API Windows.  
  
##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage  
 Вызывается для публикации определяемые пользователем сообщения на другой `CWinThread` объекта.  
  
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
 Отправленное сообщение макросом карты сообщение ON_THREAD_MESSAGE сопоставляется обработчик соответствующее сообщение.  
  
> [!NOTE]
>  При вызове Windows [PostThreadMessage](https://msdn.microsoft.com/library/windows/desktop/ms644946) функции одного приложения MFC, MFC сообщение обработчики не вызываются. Дополнительные сведения см. в статье базы знаний, «PRB: MFC сообщение обработчик не вызывается с PostThreadMessage()» (Q142415).  
  
##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage  
 Переопределите эту функцию для фильтрации сообщений окон до их передачи функциям Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pMsg*  
 Указывает на [структурой MSG](../../mfc/reference/msg-structure1.md) содержащий сообщение для обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение был полностью обработан в `PreTranslateMessage` и не должны обрабатываться Дополнительно. Нуль, если сообщения должны обрабатываться обычным образом.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется только в потоки пользовательского интерфейса.  
  
##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter  
 Функция-ловушка framework вызывает эта функция-член для фильтрации и реагировать на них некоторых сообщений Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *Код*  
 Указывает код обработчика. Эта функция-член использует код для определения способа обработки *lpMsg.*  
  
 *lpMsg*  
 Указатель на Windows [структурой MSG](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-ловушка обрабатывает события перед их отправкой в обычное сообщение приложения обработки.  
  
 Если переопределить это дополнительная возможность, необходимо вызвать версии базового класса для обеспечения платформы подключить обработки.  
  
##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException  
 Эта функция-член вызывается платформой, каждый раз, когда обработчик не перехватывает исключение, создаваемое в одном из сообщений в поток или обработчиков команд.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Указывает необработанное исключение.  
  
 *pMsg*  
 Указывает на [структурой MSG](../../mfc/reference/msg-structure1.md) информацией о сообщения windows, которое вызвало платформа для создания исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 значение -1, если создается исключение WM_CREATE; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте напрямую этой функцией-членом.  
  
 Реализация по умолчанию эта функция-член обрабатывает только те исключения, вызываемые из следующих сообщений:  
  
|Команда|Действие|  
|-------------|------------|  
|WM_CREATE|Сбой.|  
|WM_PAINT|Проверьте Затронутое окно, предотвращая создание еще одно сообщение WM_PAINT.|  
  
 Переопределите эта функция-член для предоставления глобальной обработки исключений. Вызовите базовую функциональность, только в том случае, если вы хотите отобразить поведение по умолчанию.  
  
 Эта функция-член используется только в потоки, которые имеют цикл обработки сообщений.  
  
##  <a name="pumpmessage"></a>  CWinThread::PumpMessage  
 содержит цикл обработки сообщений потока.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Примечания  
 `PumpMessage` содержит цикл обработки сообщений потока. `PumpMessage` вызывается `CWinThread` к отображению потока сообщений. Можно вызвать `PumpMessage` напрямую заставить сообщения должны обрабатываться, или можно переопределить `PumpMessage` изменить его поведение по умолчанию.  
  
 Вызов `PumpMessage` напрямую и переопределение поведения по умолчанию рекомендуется только опытным пользователям.  
  
##  <a name="resumethread"></a>  CWinThread::ResumeThread  
 Вызывается, чтобы возобновить выполнение потока, состояние приостановки [SuspendThread](#suspendthread) функция-член или потоке, созданном с использованием флага CREATE_SUSPENDED.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count, если выполнение прошло успешно; `0xFFFFFFFF` в противном случае. Если возвращаемое значение равно нулю, текущий поток не был приостановлен. Если возвращаемое значение 1, поток был приостановлен, но теперь перезапускается. Возвращаемое значение, превышающее один означает, что поток будет приостановлена.  
  
### <a name="remarks"></a>Примечания  
 Счетчик приостановок текущего потока уменьшается на единицу. Если счетчик приостановок уменьшается до нуля, поток возобновляет выполнение; в противном случае поток будет приостановлена.  
  
##  <a name="run"></a>  CWinThread::Run  
 Предоставляет цикл обработки сообщений по умолчанию для потоков пользовательского интерфейса.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Int** значение, возвращаемое в потоке. Это значение можно получить, вызвав [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).  
  
### <a name="remarks"></a>Примечания  
 `Run` Получает и отправляет сообщения, Windows, пока приложение не получит [WM_QUIT](/windows/desktop/winmsg/wm-quit) сообщения. Если очередь сообщений потока содержит сообщения не `Run` вызовы `OnIdle` для выполнения обработки времени простоя. Входящие сообщения перейти к [PreTranslateMessage](#pretranslatemessage) функция-член для специальной обработки, а затем в функцию Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) для перевода на стандартной клавиатуре. Наконец [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) вызове функции Windows.  
  
 `Run` редко переопределяется, но его можно переопределить для реализации особое поведение.  
  
 Эта функция-член используется только в потоки пользовательского интерфейса.  
  
##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority  
 Эта функция задает уровень приоритета текущего потока из соответствующего класса приоритета.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Параметры  
 *nPriority*  
 Задает новый уровень приоритета потока из соответствующего класса приоритета. Этот параметр должен иметь одно из следующих значений, перечисленных от наиболее важных до самого низкого:  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- НАИНИЗШИЙ  
  
- THREAD_PRIORITY_IDLE  
  
 Дополнительные сведения о эти приоритеты, см. в разделе [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Он может быть вызван только после [CreateThread](#createthread) успешно возвращает.  
  
##  <a name="suspendthread"></a>  CWinThread::SuspendThread  
 Увеличивает текущий счетчик приостановок анализируемого потока.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток предыдущей приостановить count, если выполнение прошло успешно; `0xFFFFFFFF` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если любой поток имеет счетчик приостановок выше нуля, этот поток не выполняется. Поток может быть возобновлено при вызове [ResumeThread](#resumethread) функция-член.  
  
## <a name="see-also"></a>См. также  
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWinApp](../../mfc/reference/cwinapp-class.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
