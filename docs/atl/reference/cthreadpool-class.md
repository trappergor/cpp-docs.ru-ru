---
title: "Класс CThreadPool | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
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
ms.openlocfilehash: 632514d03e7037ef42a1566462db5dec6f5cc1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cthreadpool-class"></a>Класс CThreadPool
Этот класс предоставляет пул рабочих потоков, обрабатывающих очередь рабочих элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>Параметры  
 *Работник*  
 Класс, соответствующий требованиям к [архетипа рабочей](../../atl/reference/worker-archetype.md) предоставить код, используемый для обработки рабочих элементов в очереди пула потоков.  
  
 `ThreadTraits`  
 Класс, предоставляющий функция, используемая для создания потоков в пуле.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|Конструктор для пула потоков.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|Деструктор для пула потоков.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Реализация `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|Этот метод вызывается для получения количества потоков в пуле.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Вызовите этот метод, чтобы получить дескриптор порта завершения ввода-ВЫВОДА в очередь рабочих элементов.|  
|[CThreadPool::GetSize](#getsize)|Этот метод вызывается для получения количества потоков в пуле.|  
|[CThreadPool::GetTimeout](#gettimeout)|Этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.|  
|[CThreadPool::Initialize](#initialize)|Этот метод вызывается для инициализации пула потоков.|  
|[CThreadPool::QueryInterface](#queryinterface)|Реализация **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](#queuerequest)|Этот метод в очередь рабочий элемент может быть обработано потоков в пуле.|  
|[CThreadPool::Release](#release)|Реализация `IUnknown::Release`.|  
|[CThreadPool::SetSize](#setsize)|Вызовите этот метод, чтобы задать количество потоков в пуле.|  
|[CThreadPool::SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.|  
|[CThreadPool::Shutdown](#shutdown)|Вызовите этот метод, чтобы завершить работу пула потоков.|  
  
## <a name="remarks"></a>Примечания  
 Создаются и уничтожаются при инициализации, размера или завершение работы пула потоков в пуле. Экземпляр класса *рабочей* будет создан в стеке каждый рабочий поток в пуле. Каждый экземпляр будет находиться в течение времени существования потока.  
  
 Сразу после создания потока *рабочей*:: `Initialize` будет вызван для объекта, связанного с этим потоком. Непосредственно перед уничтожением потока *рабочей*:: `Terminate` будет вызываться. Оба метода должны принимать **void\* ** аргумент. Значение этого аргумента передается в пул потоков через `pvWorkerParam` параметр [CThreadPool::Initialize](#initialize).  
  
 Если имеются доступные рабочие элементы в очереди и рабочие потоки работ, рабочий поток будет извлекать элемента из очереди и вызвать **Execute** метод *рабочей* объект для этого потока. Три элементы передаются в метод: элемент из очереди, же `pvWorkerParam` передается *рабочей*:: `Initialize` и *рабочей*:: `Terminate`и указатель на [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) структура, используемая для очередь порта завершения ввода-ВЫВОДА.  
  
 *Рабочей* класс объявляет тип элементов, которые будут ставиться в очередь пула потоков, предоставляя typedef, *рабочей*:: `RequestType`. Этот тип должен быть способен приведение к и из **ULONG_PTR**.  
  
 Пример *рабочей* класс [CNonStatelessWorker класса](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="addref"></a>CThreadPool::AddRef  
 Реализация `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
### <a name="remarks"></a>Примечания  
 Этот класс не реализует управление жизненным циклом с помощью подсчета ссылок.  
  
##  <a name="cthreadpool"></a>CThreadPool::CThreadPool  
 Конструктор для пула потоков.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует значение времени ожидания для [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10).  
  
##  <a name="dtor"></a>CThreadPool:: ~ CThreadPool  
 Деструктор для пула потоков.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 Этот метод вызывается для получения количества потоков в пуле.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество потоков в пуле.  
  
##  <a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 Вызовите этот метод, чтобы получить дескриптор порта завершения ввода-ВЫВОДА в очередь рабочих элементов.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор очереди или значение NULL, если пул потоков не был инициализирован.  
  
##  <a name="getsize"></a>CThreadPool::GetSize  
 Этот метод вызывается для получения количества потоков в пуле.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pnNumThreads`  
 [out] Адрес переменной, в случае успешного выполнения получает количество потоков в пуле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="gettimeout"></a>CThreadPool::GetTimeout  
 Этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pdwMaxWait`  
 [out] Адрес переменной, в случае успешного выполнения Получает максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Это время ожидания используется [CThreadPool::Shutdown](#shutdown) Если никакое другое значение передается этому методу.  
  
##  <a name="initialize"></a>CThreadPool::Initialize  
 Этот метод вызывается для инициализации пула потоков.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pvWorkerParam`  
 Параметр работника будет передан объект рабочего потока `Initialize`, **Execute**, и `Terminate` методы.  
  
 `nNumThreads`  
 Запрошенное число потоков в пуле.  
  
 Если `nNumThreads` является отрицательным, абсолютное значение будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
 Если `nNumThreads` равен нулю, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
 `dwStackSize`  
 Размер стека для каждого потока в пуле.  
  
 *hCompletion*  
 Дескриптор объекта, чтобы связать с портом завершения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="queryinterface"></a>CThreadPool::QueryInterface  
 Реализация **IUnknown::QueryInterface**.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объекты этого класса можно успешно запрашивать **IUnknown** и [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) интерфейсов.  
  
##  <a name="queuerequest"></a>CThreadPool::QueueRequest  
 Этот метод в очередь рабочий элемент может быть обработано потоков в пуле.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `request`  
 Запрос в очередь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет рабочий элемент в очередь. Потоки в пуле выбрать элементы из очереди в порядке их получения.  
  
##  <a name="release"></a>CThreadPool::Release  
 Реализация `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
### <a name="remarks"></a>Примечания  
 Этот класс не реализует управление жизненным циклом с помощью подсчета ссылок.  
  
##  <a name="setsize"></a>CThreadPool::SetSize  
 Вызовите этот метод, чтобы задать количество потоков в пуле.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nNumThreads`  
 Запрошенное число потоков в пуле.  
  
 Если `nNumThreads` является отрицательным, абсолютное значение будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
 Если `nNumThreads` равен нулю, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Если количество указанных потоков меньше числа потоков в настоящее время в пуле, объект помещает в очередь, чтобы подобрать ожидающий поток сообщения о завершении работы. Когда ожидающий поток получает сообщение из очереди, она уведомляет пула потоков и завершает процедуру потока. Этот процесс повторяется, пока количество потоков в пуле достигает заданного числа или ни один поток не завершился в течение периода, указанного в [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). В этом случае метод возвратит значение HRESULT, соответствующее для **WAIT_TIMEOUT** и сообщения о завершении работы ожидающие отменяется.  
  
##  <a name="settimeout"></a>CThreadPool::SetTimeout  
 Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwMaxWait`  
 Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Время ожидания устанавливается равным [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10) в конструкторе.  
  
 Обратите внимание, что `dwMaxWait` — это время ожидания для одного потока, завершение работы пула. Максимальное время, которое может принимать для удаления нескольких потоков из пула может быть немного меньше, чем `dwMaxWait` умноженное на количество потоков.  
  
##  <a name="shutdown"></a>CThreadPool::Shutdown  
 Вызовите этот метод, чтобы завершить работу пула потоков.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwMaxWait`  
 Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока. Если 0 или значение не задано, этот метод будет использовать время ожидания задается [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет запрос на завершение работы для всех потоков в пуле. По истечении времени ожидания, этот метод будет вызывать [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) в любом потоке, который не был завершен. Этот метод вызывается автоматически из деструктора класса.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Классы](../../atl/reference/atl-classes.md)

