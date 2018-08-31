---
title: Класс CWorkerThread | Документация Майкрософт
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
ms.openlocfilehash: 78d846db4080c780bfa72fca52b7c9f6868edc2f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195347"
---
# <a name="cworkerthread-class"></a>Класс CWorkerThread
Этот класс создает рабочий поток или используется существующая рабочая область, ожидает один или несколько дескрипторов объектов ядра и выполняет функцию указанного клиента, когда один из маркеров, получает сигнал.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Параметры  
 *ThreadTraits*  
 Класс, предоставляющий функции создания потока, такие как [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) или [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Участники  
  
### <a name="protected-structures"></a>Защищенных структур  
  
|name|Описание|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|Конструктор для рабочего потока.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Деструктор для рабочего потока.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|Вызовите этот метод, чтобы добавить маркер этот объект в данный список рабочим потоком.|  
|[CWorkerThread::AddTimer](#addtimer)|Вызовите этот метод, чтобы добавить этот таймер в данный список рабочим потоком.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Вызовите этот метод, чтобы получить дескриптор потока рабочего потока.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Этот метод используется для получения идентификатора потока рабочего потока.|  
|[CWorkerThread::Initialize](#initialize)|Вызовите этот метод для инициализации рабочего потока.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Вызовите этот метод, чтобы удалить маркер из списка объектов ожидания.|  
|[CWorkerThread::Shutdown](#shutdown)|Вызовите этот метод, чтобы завершить работу рабочего потока.|  
  
## <a name="remarks"></a>Примечания  
  
### <a name="to-use-cworkerthread"></a>Чтобы использовать CWorkerThread  
  
1.  Создайте экземпляр этого класса.  
  
2.  Вызовите [CWorkerThread::Initialize](#initialize).  
  
3.  Вызовите [CWorkerThread::AddHandle](#addhandle) с дескриптором объекта ядра и указатель на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     - или  
  
     Вызовите [CWorkerThread::AddTimer](#addtimer) с указателем на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Реализуйте [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) предпринимать определенные действия при получении сигнала дескриптором или таймера.  
  
5.  Чтобы удалить объект из списка объектов ожидания, вызовите [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  Чтобы завершить поток, вызовите [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="addhandle"></a>  CWorkerThread::AddHandle  
 Вызовите этот метод, чтобы добавить маркер этот объект в данный список рабочим потоком.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hObject*  
 Дескриптор ожидающий объект.  
  
 *pClient*  
 Указатель на [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) интерфейс объекта, который должен вызываться при дескриптор получает сигнал.  
  
 *dwParam*  
 Параметр передается [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) когда дескриптор получает сигнал.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызывать с помощью *pClient* при дескриптор, *hObject*, переводится в сигнальное состояние.  
  
##  <a name="addtimer"></a>  CWorkerThread::AddTimer  
 Вызовите этот метод, чтобы добавить этот таймер в данный список рабочим потоком.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwInterval*  
 Указывает период таймера в миллисекундах.  
  
 *pClient*  
 Указатель на [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) интерфейс объекта, который должен вызываться при дескриптор получает сигнал.  
  
 *dwParam*  
 Параметр передается [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) когда дескриптор получает сигнал.  
  
 *phTimer*  
 [out] Адрес переменной ДЕСКРИПТОРА, в случае успешного выполнения принимает дескриптор только что созданный таймера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызывать с помощью *pClient* при получении сигнала таймера.  
  
 Передайте дескриптор таймера из *phTimer* для [CWorkerThread::RemoveHandle](#removehandle) закрыть таймера.  
  
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
 Вызовите этот метод для инициализации рабочего потока.  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pThread*  
 Существующий рабочий поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для инициализации объекта, после создания или после вызова [CWorkerThread::Shutdown](#shutdown).  
  
 Использовать два или несколько `CWorkerThread` объекты использовать один и тот же рабочий поток, один из них без передачи аргументов последующей передаче указателя на этот объект для инициализации `Initialize` другие методы. Следует выключить инициализирован с помощью указателя мыши на объекты, прежде чем объект, используемый для их инициализации.  
  
 См. в разделе [CWorkerThread::Shutdown](#shutdown) сведения, как изменяется поведение этого метода при инициализации, используя указатель на существующий объект.  
  
##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle  
 Вызовите этот метод, чтобы удалить маркер из списка объектов ожидания.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hObject*  
 Handle для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 При удалении дескриптор [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) будет вызываться для связанного объекта, который был передан [AddHandle](#addhandle). Если этот вызов завершается неудачно, `CWorkerThread` будет вызывать Windows [CloseHandle](https://msdn.microsoft.com/library/windows/desktop/ms724211) функции с дескриптором.  
  
##  <a name="shutdown"></a>  CWorkerThread::Shutdown  
 Вызовите этот метод, чтобы завершить работу рабочего потока.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwWait*  
 Время в миллисекундах для ожидания рабочий поток для завершения работы. ATL_WORKER_THREAD_WAIT по умолчанию 10 секунд. При необходимости можно определить собственное значение для этого символа перед включением файлов atlutil.h. 
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успеха или ошибку HRESULT в случае сбоя, например, если значение времени ожидания, *dwWait*, превышено.  
  
### <a name="remarks"></a>Примечания  
 Чтобы повторно использовать объект, вызовите [CWorkerThread::Initialize](#initialize) после вызова этого метода.  
  
 Обратите внимание, что при вызове `Shutdown` объекта инициализируется указатель на другую `CWorkerThread` объекта не влияет и всегда возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Классы](../../atl/reference/atl-classes.md)   
 [Многопоточность: Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md)   
 [Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)
