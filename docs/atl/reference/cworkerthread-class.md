---
title: Класс CWorkerThread | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e87001ca341ae27cb173357f74e06e543f5eb262
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365524"
---
# <a name="cworkerthread-class"></a>Класс CWorkerThread
Этот класс создает рабочий поток или использует уже существующий, ожидает один или несколько маркеров объектов ядра и выполняет функцию указанного клиента, когда один из маркеров, получает сигнал.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Параметры  
 `ThreadTraits`  
 Класс, предоставляющий функции создания потока, такие как [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) или [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Участники  
  
### <a name="protected-structures"></a>Защищенные структуры  
  
|name|Описание|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|Конструктор рабочего потока.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Деструктор для рабочего потока.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|Вызовите этот метод, чтобы добавить дескриптор ожидающий объект списка, поддерживаемого рабочим потоком.|  
|[CWorkerThread::AddTimer](#addtimer)|Этот метод служит для добавления периодический таймер ожидания для списка, поддерживаемого рабочим потоком.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Вызовите этот метод, чтобы получить дескриптор потока рабочего потока.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Этот метод используется для получения идентификатора потока рабочего потока.|  
|[CWorkerThread::Initialize](#initialize)|Этот метод вызывается для инициализации рабочего потока.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Вызовите этот метод, чтобы удалить маркер из списка объектов ожидания.|  
|[CWorkerThread::Shutdown](#shutdown)|Вызовите этот метод, чтобы завершить работу рабочий поток.|  
  
## <a name="remarks"></a>Примечания  
  
### <a name="to-use-cworkerthread"></a>Чтобы использовать CWorkerThread  
  
1.  Создайте экземпляр этого класса.  
  
2.  Вызовите [CWorkerThread::Initialize](#initialize).  
  
3.  Вызовите [CWorkerThread::AddHandle](#addhandle) с дескриптором объекта ядра и указатель на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     - или  
  
     Вызовите [CWorkerThread::AddTimer](#addtimer) с указателем на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Реализуйте [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) для выполнения некоторых действий при получении сигнала дескриптор или таймера.  
  
5.  Чтобы удалить объект из списка объектов ожидания, вызовите [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  Чтобы завершить поток, вызовите [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="addhandle"></a>  CWorkerThread::AddHandle  
 Вызовите этот метод, чтобы добавить дескриптор ожидающий объект списка, поддерживаемого рабочим потоком.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Дескриптор ожидания объекта.  
  
 `pClient`  
 Указатель на [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) интерфейс объекта, которое будет вызываться, когда дескриптор получает сигнал.  
  
 `dwParam`  
 Параметр должен быть передан [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) при дескриптор получает сигнал.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызываться через `pClient` при дескриптора, `hObject`, которому отправляется сигнал.  
  
##  <a name="addtimer"></a>  CWorkerThread::AddTimer  
 Этот метод служит для добавления периодический таймер ожидания для списка, поддерживаемого рабочим потоком.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwInterval*  
 Указывает интервал таймера в миллисекундах.  
  
 `pClient`  
 Указатель на [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) интерфейс объекта, которое будет вызываться, когда дескриптор получает сигнал.  
  
 `dwParam`  
 Параметр должен быть передан [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) при дескриптор получает сигнал.  
  
 `phTimer`  
 [out] Адрес переменной ДЕСКРИПТОРА, в случае успешного выполнения принимает дескриптор только что созданный таймера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызываться через `pClient` при сигнал таймера.  
  
 Передает этот дескриптор таймера из `phTimer` для [CWorkerThread::RemoveHandle](#removehandle) закрытие таймером.  
  
##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread  
 Конструктор.  
  
```
CWorkerThread() throw();
```  
  
##  <a name="dtor"></a>  CWorkerThread:: ~ CWorkerThread  
 Деструктор  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CWorkerThread::Shutdown](#shutdown).  
  
##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle  
 Вызовите этот метод, чтобы получить дескриптор потока рабочего потока.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор потока или значение NULL, если рабочий поток не был инициализирован.  
  
##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId  
 Этот метод используется для получения идентификатора потока рабочего потока.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор потока или значение NULL, если рабочий поток не был инициализирован.  
  
##  <a name="initialize"></a>  CWorkerThread::Initialize  
 Этот метод вызывается для инициализации рабочего потока.  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pThread`  
 Существующий рабочий поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для инициализации объекта после создания или после вызова [CWorkerThread::Shutdown](#shutdown).  
  
 Для двух или более `CWorkerThread` объектов использовать в одном рабочем потоке, один из них без передачи аргументов затем передать указатель на этот объект для инициализации `Initialize` других методов. Объекты, инициализируется с использованием указателя необходимо завершить работу перед объект, используемый для их инициализации.  
  
 В разделе [CWorkerThread::Shutdown](#shutdown) сведения, как изменяется поведение этого метода при инициализации с помощью указателя на существующий объект.  
  
##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle  
 Вызовите этот метод, чтобы удалить маркер из списка объектов ожидания.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Дескриптор для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 При удалении дескриптора [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) будет вызываться для связанного объекта, который был передан в [AddHandle](#addhandle). Если этот вызов завершается неудачно, `CWorkerThread` вызовет Windows [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) функция с дескриптором.  
  
##  <a name="shutdown"></a>  CWorkerThread::Shutdown  
 Вызовите этот метод, чтобы завершить работу рабочий поток.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwWait`  
 Время (в миллисекундах) ожидания рабочего потока завершить работу. Значение по умолчанию ATL_WORKER_THREAD_WAIT 10 секунд. При необходимости можно определить собственное значение для этого символа перед включением файлов atlutil.h. 
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое, например, если значение времени ожидания `dwWait`, превышено.  
  
### <a name="remarks"></a>Примечания  
 Чтобы повторно использовать объект, вызовите [CWorkerThread::Initialize](#initialize) после вызова этого метода.  
  
 Обратите внимание, что вызов **завершение работы** на объект инициализируется с использованием указателя в другой `CWorkerThread` объект не действует и всегда возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Классы](../../atl/reference/atl-classes.md)   
 [Многопоточность: Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md)   
 [Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)
