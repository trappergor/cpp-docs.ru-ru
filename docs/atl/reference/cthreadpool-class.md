---
title: Класс CThreadPool
ms.date: 11/04/2016
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
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
ms.openlocfilehash: 7d363de0d787ecc5015093005b39a379acd82e71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277402"
---
# <a name="cthreadpool-class"></a>Класс CThreadPool

Этот класс предоставляет пул рабочих потоков, обрабатывающих очередь рабочих элементов.

## <a name="syntax"></a>Синтаксис

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>Параметры

*Рабочей роли*<br/>
Класс, соответствующий требованиям к [рабочий архетип](../../atl/reference/worker-archetype.md) предоставить код, используемый для обработки рабочих элементов в очередь в пуле потоков.

*ThreadTraits*<br/>
Класс, предоставляющий функция, используемая для создания потоков в пуле.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CThreadPool::CThreadPool](#cthreadpool)|Конструктор для пула потоков.|
|[CThreadPool:: ~ CThreadPool](#dtor)|Деструктор для пула потоков.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CThreadPool::AddRef](#addref)|Реализация `IUnknown::AddRef`.|
|[CThreadPool::GetNumThreads](#getnumthreads)|Вызовите этот метод, чтобы получить число потоков в пуле.|
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Вызовите этот метод, чтобы получить дескриптор порта завершения ввода-ВЫВОДА, используемого в очередь рабочих элементов.|
|[CThreadPool::GetSize](#getsize)|Вызовите этот метод, чтобы получить число потоков в пуле.|
|[CThreadPool::GetTimeout](#gettimeout)|Вызовите этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.|
|[CThreadPool::Initialize](#initialize)|Вызовите этот метод для инициализации пула потоков.|
|[CThreadPool::QueryInterface](#queryinterface)|Реализация `IUnknown::QueryInterface`.|
|[CThreadPool::QueueRequest](#queuerequest)|Этот метод в очередь рабочий элемент для обработки в поток в пуле.|
|[CThreadPool::Release](#release)|Реализация `IUnknown::Release`.|
|[CThreadPool::SetSize](#setsize)|Вызовите этот метод, чтобы задать количество потоков в пуле.|
|[CThreadPool::SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.|
|[CThreadPool::Shutdown](#shutdown)|Этот метод используется для завершения работы пула потоков.|

## <a name="remarks"></a>Примечания

Создаются и удаляются при инициализации, размера или завершение работы пула потоков в пуле. Экземпляр класса *рабочих* создается на стеке каждый рабочий поток в пуле. Каждый экземпляр будет располагаться в течение времени существования потока.

Сразу после создания потока *рабочих*::`Initialize` будет вызван для объекта, связанного с этим потоком. Непосредственно перед уничтожением потока *рабочих*::`Terminate` будет вызываться. Оба метода должны принимать **void** <strong>\*</strong> аргумент. Значение этого аргумента передается в пул потоков через *pvWorkerParam* параметр [CThreadPool::Initialize](#initialize).

Если имеются доступные рабочие элементы в очереди и рабочие потоки работ, рабочий поток извлечет элемента из очереди и вызов `Execute` метод *рабочих* объект для этого потока. Три элемента передаются методу: элемент из очереди, же `pvWorkerParam` передается *рабочих*:: `Initialize` и *рабочих*:: `Terminate`и указатель на [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) структура, используемая для очередь порта завершения ввода-ВЫВОДА.

*Рабочих* класс объявляет тип элементов, которые будут помещаться в очередь в пуле потоков, предоставляя typedef, *рабочих*:: `RequestType`. Этот тип должен поддерживать приведение к и из ULONG_PTR.

Пример *рабочих* класс является [класс CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="addref"></a>  CThreadPool::AddRef

Реализация `IUnknown::AddRef`.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение 1.

### <a name="remarks"></a>Примечания

Этот класс не реализует элементы управления временем существования, с помощью подсчета ссылок.

##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool

Конструктор для пула потоков.

```
CThreadPool() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует значение времени ожидания для ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT. По умолчанию составляет 36 секунд. При необходимости можно определить собственные положительное целочисленное значение для этого символа перед включением файлов atlutil.h.

##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool

Деструктор для пула потоков.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [CThreadPool::Shutdown](#shutdown).

##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads

Вызовите этот метод, чтобы получить число потоков в пуле.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество потоков в пуле.

##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle

Вызовите этот метод, чтобы получить дескриптор порта завершения ввода-ВЫВОДА, используемого в очередь рабочих элементов.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор очереди или значение NULL, если пул потоков не инициализирован.

##  <a name="getsize"></a>  CThreadPool::GetSize

Вызовите этот метод, чтобы получить число потоков в пуле.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>Параметры

*pnNumThreads*<br/>
[out] Адрес переменной, которая, в случае успешного выполнения получает количество потоков в пуле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="gettimeout"></a>  CThreadPool::GetTimeout

Вызовите этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>Параметры

*pdwMaxWait*<br/>
[out] Адрес переменной, которая, в случае успешного выполнения Получает максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Это значение времени ожидания используется [CThreadPool::Shutdown](#shutdown) Если другое значение не поддерживается для этого метода.

##  <a name="initialize"></a>  CThreadPool::Initialize

Вызовите этот метод для инициализации пула потоков.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>Параметры

*pvWorkerParam*<br/>
Параметр рабочей роли будет передан в объект рабочего потока `Initialize`, `Execute`, и `Terminate` методы.

*nNumThreads*<br/>
Запрашиваемое количество потоков в пуле.

Если *nNumThreads* является отрицательным, его абсолютное значение будет умножена на число процессоров в компьютере для получения общего числа потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножена на число процессоров в компьютере для получения общего числа потоков.  Значение по умолчанию — 2 потоков на процессор. При необходимости можно определить собственные положительное целочисленное значение для этого символа перед включением файлов atlutil.h.

*dwStackSize*<br/>
Размер стека для каждого потока в пуле.

*hCompletion*<br/>
Дескриптор объекта, который необходимо связать с портом завершения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="queryinterface"></a>  CThreadPool::QueryInterface

Реализация `IUnknown::QueryInterface`.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>Примечания

Объекты этого класса может успешно запросить `IUnknown` и [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) интерфейсов.

##  <a name="queuerequest"></a>  CThreadPool::QueueRequest

Этот метод в очередь рабочий элемент для обработки в поток в пуле.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>Параметры

*Запрос*<br/>
Запрос будет поставлен в очередь.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод добавляет рабочий элемент в очередь. Потоков в пуле, чтобы выбрать архивируемые элементы из очереди в порядке, в котором они будут получены.

##  <a name="release"></a>  CThreadPool::Release

Реализация `IUnknown::Release`.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение 1.

### <a name="remarks"></a>Примечания

Этот класс не реализует элементы управления временем существования, с помощью подсчета ссылок.

##  <a name="setsize"></a>  CThreadPool::SetSize

Вызовите этот метод, чтобы задать количество потоков в пуле.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>Параметры

*nNumThreads*<br/>
Запрашиваемое количество потоков в пуле.

Если *nNumThreads* является отрицательным, его абсолютное значение будет умножена на число процессоров в компьютере для получения общего числа потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножена на число процессоров в компьютере для получения общего числа потоков. Значение по умолчанию — 2 потоков на процессор. При необходимости можно определить собственные положительное целочисленное значение для этого символа перед включением файлов atlutil.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Если количество указанных потоков меньше, чем количество потоков в пуле, объект помещает сообщения о завершении работы для очереди равным подберет ожидающий поток. Когда ожидающий поток получает сообщение из очереди, он уведомляет пула потоков и завершает процедуру потока. Этот процесс повторяется, пока количество потоков в пуле достигает заданного числа или ни один поток не завершился в течение периода, указанного [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). В этом случае метод возвращает значение HRESULT, соответствующее WAIT_TIMEOUT и сообщения о завершении работы ожидающие отменяется.

##  <a name="settimeout"></a>  CThreadPool::SetTimeout

Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Время ожидания при инициализации ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT. По умолчанию составляет 36 секунд. При необходимости можно определить собственные положительное целочисленное значение для этого символа перед включением файлов atlutil.h.

Обратите внимание, что *dwMaxWait* — время, для пула будет ожидать один поток для завершения работы. Максимальное время, которое может выполняться для удаления нескольких потоков из пула может быть немного меньше, чем *dwMaxWait* умноженное на количество потоков.

##  <a name="shutdown"></a>  CThreadPool::Shutdown

Этот метод используется для завершения работы пула потоков.

```
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы. Если 0 или значение не указано, этот метод будет использовать время ожидания, заданное [CThreadPool::SetTimeout](#settimeout).

### <a name="remarks"></a>Примечания

Этот метод отправляет запрос на завершение работы для всех потоков в пуле. Если время ожидания истекает, этот метод будет вызывать [TerminateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-terminatethread) в любом потоке, не завершил работу. Этот метод вызывается автоматически из деструктора класса.

## <a name="see-also"></a>См. также

[Интерфейс IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Классы](../../atl/reference/atl-classes.md)
