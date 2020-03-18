---
title: Класс Кворкерсреад
ms.date: 11/04/2016
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
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: f1aa76514b98bbf12f8e516d3d54f68e8ef4dd7d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423144"
---
# <a name="cworkerthread-class"></a>Класс Кворкерсреад

Этот класс создает рабочий поток или использует существующий, ожидает один или несколько дескрипторов объектов ядра и выполняет указанную клиентскую функцию, когда один из дескрипторов получает сигнал.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Параметры

*среадтраитс*<br/>
Класс, предоставляющий функцию создания потока, например [кртсреадтраитс](../../atl/reference/crtthreadtraits-class.md) или [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).

## <a name="members"></a>Члены

### <a name="protected-structures"></a>Защищенные структуры

|Имя|Description|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кворкерсреад:: Кворкерсреад](#cworkerthread)|Конструктор для рабочего потока.|
|[Кворкерсреад:: ~ Кворкерсреад](#dtor)|Деструктор для рабочего потока.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кворкерсреад:: Аддхандле](#addhandle)|Вызовите этот метод, чтобы добавить обработчик ожидающего объекта в список, обслуживаемый рабочим потоком.|
|[Кворкерсреад:: Аддтимер](#addtimer)|Вызовите этот метод, чтобы добавить периодический таймер ожидания в список, обслуживаемый рабочим потоком.|
|[Кворкерсреад:: Жетсреадхандле](#getthreadhandle)|Вызовите этот метод, чтобы получить обработчик потока рабочего потока.|
|[Кворкерсреад:: Жетсреадид](#getthreadid)|Вызовите этот метод, чтобы получить идентификатор потока рабочего потока.|
|[Кворкерсреад:: Initialize](#initialize)|Вызовите этот метод, чтобы инициализировать рабочий поток.|
|[Кворкерсреад:: Ремовехандле](#removehandle)|Вызовите этот метод, чтобы удалить маркер из списка ожидающих объектов.|
|[Кворкерсреад:: Shutdown](#shutdown)|Вызовите этот метод, чтобы завершить работу рабочего потока.|

## <a name="remarks"></a>Remarks

### <a name="to-use-cworkerthread"></a>Использование Кворкерсреад

1. Создайте экземпляр этого класса.

1. Вызовите [кворкерсреад:: Initialize](#initialize).

1. Вызовите [кворкерсреад:: аддхандле](#addhandle) с маркером объекта ядра и указателем на реализацию [иворкерсреадклиент](../../atl/reference/iworkerthreadclient-interface.md).

   \- или -

   Вызовите [кворкерсреад:: аддтимер](#addtimer) с указателем на реализацию [иворкерсреадклиент](../../atl/reference/iworkerthreadclient-interface.md).

1. Реализуйте [иворкерсреадклиент:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) , чтобы выполнить какое-либо действие при сигнале дескриптора или таймера.

1. Чтобы удалить объект из списка ожидающих объектов, вызовите [кворкерсреад:: ремовехандле](#removehandle).

1. Чтобы завершить поток, вызовите [кворкерсреад:: Shutdown](#shutdown).

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil. h

##  <a name="addhandle"></a>Кворкерсреад:: Аддхандле

Вызовите этот метод, чтобы добавить обработчик ожидающего объекта в список, обслуживаемый рабочим потоком.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик для ожидающего объекта.

*пклиент*<br/>
Указатель на интерфейс [иворкерсреадклиент](../../atl/reference/iworkerthreadclient-interface.md) для объекта, вызываемого при сигнале дескриптора.

*двпарам*<br/>
Параметр, передаваемый в [иворкерсреадклиент:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) при сигнале дескриптора.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Remarks

[Иворкерсреадклиент:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызываться через *пклиент* при сигнале дескриптора *хобжект*.

##  <a name="addtimer"></a>Кворкерсреад:: Аддтимер

Вызовите этот метод, чтобы добавить периодический таймер ожидания в список, обслуживаемый рабочим потоком.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Параметры

*двинтервал*<br/>
Указывает период таймера в миллисекундах.

*пклиент*<br/>
Указатель на интерфейс [иворкерсреадклиент](../../atl/reference/iworkerthreadclient-interface.md) для объекта, вызываемого при сигнале дескриптора.

*двпарам*<br/>
Параметр, передаваемый в [иворкерсреадклиент:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) при сигнале дескриптора.

*фтимер*<br/>
заполняет Адрес переменной HANDLE, которая в случае успеха получает маркер вновь созданного таймера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Remarks

[Иворкерсреадклиент:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызываться через *пклиент* при сигнале таймера.

Передайте обработчик таймера из *фтимер* в [Кворкерсреад:: ремовехандле](#removehandle) , чтобы закрыть таймер.

##  <a name="cworkerthread"></a>Кворкерсреад:: Кворкерсреад

Конструктор.

```
CWorkerThread() throw();
```

##  <a name="dtor"></a>Кворкерсреад:: ~ Кворкерсреад

Деструктор

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Remarks

Вызывает [кворкерсреад:: Shutdown](#shutdown).

##  <a name="getthreadhandle"></a>Кворкерсреад:: Жетсреадхандле

Вызовите этот метод, чтобы получить обработчик потока рабочего потока.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает обработчик потока или значение NULL, если рабочий поток не был инициализирован.

##  <a name="getthreadid"></a>Кворкерсреад:: Жетсреадид

Вызовите этот метод, чтобы получить идентификатор потока рабочего потока.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор потока или значение NULL, если рабочий поток не был инициализирован.

##  <a name="initialize"></a>Кворкерсреад:: Initialize

Вызовите этот метод, чтобы инициализировать рабочий поток.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Параметры

*псреад*<br/>
Существующий рабочий поток.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Remarks

Этот метод следует вызывать для инициализации объекта после создания или после вызова [кворкерсреад:: Shutdown](#shutdown).

Чтобы два или более `CWorkerThread`ных объектов использовали один и тот же рабочий поток, инициализируйте один из них без передачи аргументов, а затем передайте указатель на этот объект в `Initialize` методы других. Инициализация объектов, инициализированных с помощью указателя, должна быть завершена до того, как объект использовался для их инициализации.

Сведения о том, как изменяется поведение метода при инициализации с помощью указателя на существующий объект, см. в разделе [кворкерсреад:: Shutdown](#shutdown) .

##  <a name="removehandle"></a>Кворкерсреад:: Ремовехандле

Вызовите этот метод, чтобы удалить маркер из списка ожидающих объектов.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Удаляемый маркер.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Remarks

При удалении маркера [иворкерсреадклиент:: CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) будет вызываться для связанного объекта, переданного в [аддхандле](#addhandle). Если этот вызов завершается неудачей, `CWorkerThread` вызывает функцию Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) для маркера.

##  <a name="shutdown"></a>Кворкерсреад:: Shutdown

Вызовите этот метод, чтобы завершить работу рабочего потока.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Параметры

*двваит*<br/>
Время ожидания (в миллисекундах) завершения работы рабочего потока. ATL_WORKER_THREAD_WAIT значение по умолчанию — 10 секунд. При необходимости можно определить собственное значение для этого символа, прежде чем включать файлов atlutil. h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое, например при превышении значения времени ожидания *двваит*.

### <a name="remarks"></a>Remarks

Чтобы повторно использовать объект, вызовите метод [кворкерсреад:: Initialize](#initialize) после вызова этого метода.

Обратите внимание, что вызов `Shutdown` для объекта, инициализированного указателем на другой объект `CWorkerThread`, не имеет результата и всегда возвращает S_OK.

## <a name="see-also"></a>См. также раздел

[дефаултсреадтраитс](atl-typedefs.md#defaultthreadtraits)<br/>
[Классы](../../atl/reference/atl-classes.md)<br/>
[Многопоточность. Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md)<br/>
[Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)
