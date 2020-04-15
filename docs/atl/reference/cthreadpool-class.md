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
ms.openlocfilehash: 0b970915aa07fe2d1af2b3a07345d5b19826be69
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330567"
---
# <a name="cthreadpool-class"></a>Класс CThreadPool

Этот класс предоставляет пул рабочих потоков, обрабатываемых очередью рабочих элементов.

## <a name="syntax"></a>Синтаксис

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>Параметры

*Работник*<br/>
Класс, соответствующий [архетипу рабочего,](../../atl/reference/worker-archetype.md) обеспечивающий код, используемый для обработки рабочих элементов, всабранных в очередь в пуле потоков.

*ThreadTraits*<br/>
Класс, обеспечивающий функцию, используемую для создания потоков в пуле.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CThreadpool::CThreadpool](#cthreadpool)|Конструктор для пула потоков.|
|[CThreadPool::CThreadpool](#dtor)|Деструктор для пула потоков.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CThreadpool:AddRef](#addref)|Реализация метода `IUnknown::AddRef`.|
|[CThreadPool::GetNumThreads](#getnumthreads)|Вызовите этот метод, чтобы получить количество потоков в пуле.|
|[CThreadPool::GetQueue](#getqueuehandle)|Вызовите этот метод, чтобы получить ручку порта завершения IO используется для очереди рабочих элементов.|
|[CThreadPool::GetSize](#getsize)|Вызовите этот метод, чтобы получить количество потоков в пуле.|
|[CThreadPool::GetTimeout](#gettimeout)|Вызовите этот метод, чтобы получить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.|
|[CThreadPool::Инициализация](#initialize)|Вызовите этот метод, чтобы инициализировать пул потоков.|
|[CThreadPool::Кви-интерфейс](#queryinterface)|Реализация метода `IUnknown::QueryInterface`.|
|[CThreadPool:: ОчередьЗапрос](#queuerequest)|Вызовите этот метод в очередь рабочего элемента, который будет обрабатываться потоком в пуле.|
|[CThreadPool::Release](#release)|Реализация метода `IUnknown::Release`.|
|[CThreadPool::SetSize](#setsize)|Вызовите этот метод, чтобы установить количество потоков в пуле.|
|[CThreadPool::SetTimeout](#settimeout)|Вызовите этот метод, чтобы установить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.|
|[CThreadPool::Закрытие](#shutdown)|Вызовите этот метод, чтобы закрыть пул потоков.|

## <a name="remarks"></a>Remarks

Потоки в бассейне создаются и разрушаются, когда пул инициализирован, перестраиваются или выключаются. Экземпляр *рабочего* класса будет создан в стеке каждого рабочего потока в пуле. Каждый экземпляр будет жить в течение всего срока службы потока.

Сразу же после создания *потока, Рабочий*::`Initialize` будет вызван на объект, связанный с этим потоком. Непосредственно перед разрушением *Worker*нити,`Terminate` Работник :: будет называться. Оба метода должны принять **недействительный** <strong>\*</strong> аргумент. Значение этого аргумента передается в пул потоков через параметр *pvWorkerParam* [CThreadPool::Initialize](#initialize).

При наличии рабочих элементов в очереди и рабочих потоков, доступных для работы, рабочий поток вытащит элемент из очереди и вызовет `Execute` метод объекта *"Рабочий"* для этого потока. Затем три элемента передаются методу: элемент из `pvWorkerParam` очереди, `Initialize` тот же `Terminate`передан *Работнику*:: и *Worker*:: , и указатель на структуру [OVERLAPPED,](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) используемую для очереди порта завершения IO.

Класс *"Рабочий"* объявляет тип элементов, которые будут стоять в очереди в `RequestType`пуле потоков, предоставляя typedef, *Worker::*. Этот тип должен быть способен быть брошены в и из ULONG_PTR.

Примером класса *«Рабочий»* является [класс CNonStatelessWorker.](../../atl/reference/cnonstatelessworker-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="cthreadpooladdref"></a><a name="addref"></a>CThreadpool:AddRef

Реализация метода `IUnknown::AddRef`.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

### <a name="remarks"></a>Remarks

Этот класс не выполняет управление пожизненным сроком с помощью подсчета ссылок.

## <a name="cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>CThreadpool::CThreadpool

Конструктор для пула потоков.

```
CThreadPool() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует значение тайм-аута для ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT. Время по умолчанию составляет 36 секунд. При необходимости вы можете определить свое положительное значение для этого символа, прежде чем включить atlutil.h.

## <a name="cthreadpoolcthreadpool"></a><a name="dtor"></a>CThreadPool::CThreadpool

Деструктор для пула потоков.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>Remarks

Вызовы [CThreadpool::Закрытие](#shutdown).

## <a name="cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>CThreadPool::GetNumThreads

Вызовите этот метод, чтобы получить количество потоков в пуле.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество потоков в пуле.

## <a name="cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>CThreadPool::GetQueue

Вызовите этот метод, чтобы получить ручку порта завершения IO используется для очереди рабочих элементов.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку очереди или NULL, если пул потока не был инициализирован.

## <a name="cthreadpoolgetsize"></a><a name="getsize"></a>CThreadPool::GetSize

Вызовите этот метод, чтобы получить количество потоков в пуле.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>Параметры

*pnNumThreads*<br/>
(ваут) Адрес переменной, которая, по успеху, получает количество потоков в пуле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cthreadpoolgettimeout"></a><a name="gettimeout"></a>CThreadPool::GetTimeout

Вызовите этот метод, чтобы получить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>Параметры

*pdwMaxWait*<br/>
(ваут) Адрес переменной, которая, по успеху, получает максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Это значение тайм-аута используется [CThreadPool::Shutdown,](#shutdown) если этому методу не поставляется другое значение.

## <a name="cthreadpoolinitialize"></a><a name="initialize"></a>CThreadPool::Инициализация

Вызовите этот метод, чтобы инициализировать пул потоков.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>Параметры

*pvWorkerParam*<br/>
Параметр рабочего, который должен быть `Initialize`передан `Execute`объекту рабочего потока и `Terminate` методам.

*nNumThreads*<br/>
Запрошенное количество потоков в пуле.

Если *nNumThreads* отрицательный, его абсолютное значение будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков.  По умолчанию 2 потока на процессор. При необходимости вы можете определить свое положительное значение для этого символа, прежде чем включить atlutil.h.

*dwStackSize*<br/>
Размер стека для каждого потока в пуле.

*hЗавершение*<br/>
Ручка объекта, связываемого с портом завершения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cthreadpoolqueryinterface"></a><a name="queryinterface"></a>CThreadPool::Кви-интерфейс

Реализация метода `IUnknown::QueryInterface`.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>Remarks

Объекты этого класса могут быть `IUnknown` успешно запрошены для интерфейсов [IThreadPoolConfig.](../../atl/reference/ithreadpoolconfig-interface.md)

## <a name="cthreadpoolqueuerequest"></a><a name="queuerequest"></a>CThreadPool:: ОчередьЗапрос

Вызовите этот метод в очередь рабочего элемента, который будет обрабатываться потоком в пуле.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>Параметры

*Запрос*<br/>
Запрос на очереди.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Этот метод добавляет рабочий элемент в очередь. Потоки в пуле отбирают элементы из очереди в порядке, в котором они получены.

## <a name="cthreadpoolrelease"></a><a name="release"></a>CThreadPool::Release

Реализация метода `IUnknown::Release`.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

### <a name="remarks"></a>Remarks

Этот класс не выполняет управление пожизненным сроком с помощью подсчета ссылок.

## <a name="cthreadpoolsetsize"></a><a name="setsize"></a>CThreadPool::SetSize

Вызовите этот метод, чтобы установить количество потоков в пуле.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>Параметры

*nNumThreads*<br/>
Запрошенное количество потоков в пуле.

Если *nNumThreads* отрицательный, его абсолютное значение будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков. По умолчанию 2 потока на процессор. При необходимости вы можете определить свое положительное значение для этого символа, прежде чем включить atlutil.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Если указанное число потоков меньше числа потоков, наданных в настоящее время в пуле, объект помещает сообщение о завершении работы в очереди, подхватив поток ожидания. Когда ожидающий поток снимает сообщение с очереди, он уведомляет пул потока и выходит из процедуры потока. Этот процесс повторяется до тех пор, пока количество потоков в пуле не достигнет указанного числа или пока ни один поток не выйдет в течение периода, указанного [GetTimeout](#gettimeout)/ [SetTimeout.](#settimeout) В этой ситуации метод возвращает HRESULT, соответствующий WAIT_TIMEOUT, и ожидавное сообщение о завершении работы будет отменено.

## <a name="cthreadpoolsettimeout"></a><a name="settimeout"></a>CThreadPool::SetTimeout

Вызовите этот метод, чтобы установить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Тайм-аут инициализирован до ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT. Время по умолчанию составляет 36 секунд. При необходимости вы можете определить свое положительное значение для этого символа, прежде чем включить atlutil.h.

Обратите внимание, что *dwMaxWait* это время, когда пул будет ждать одного потока, чтобы закрыть. Максимальное время, которое может быть принято для удаления нескольких потоков из пула может быть немного меньше, чем *dwMaxWait* умножается на количество потоков.

## <a name="cthreadpoolshutdown"></a><a name="shutdown"></a>CThreadPool::Закрытие

Вызовите этот метод, чтобы закрыть пул потоков.

```
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить. Если значение 0 или нет, этот метод будет использовать тайм-аут, установленный [CThreadPool::SetTimeout](#settimeout).

### <a name="remarks"></a>Remarks

Этот метод размещает запрос на выключение для всех потоков в пуле. Если тайм-аут истекает, этот метод вызовет [TerminateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-terminatethread) на любом потоке, который не вышел. Этот метод автоматически вызывается из деструктора класса.

## <a name="see-also"></a>См. также раздел

[Интерфейс IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Классы](../../atl/reference/atl-classes.md)
