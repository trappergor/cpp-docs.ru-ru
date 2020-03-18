---
title: Класс event
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 3d645cc09c61402059e9a86679c10ee703ee8031
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443741"
---
# <a name="event-class"></a>Класс event

Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class event;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Деструктор события ~](#dtor)|Уничтожает событие.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[reset](#reset)|Сбрасывает событие в несигнальное состояние.|
|[set](#set)|Сигнализирует о событии.|
|[ожидания](#wait)|Ожидает сигнала события.|
|[wait_for_multiple](#wait_for_multiple)|Ожидает получения сигнала для нескольких событий.|

### <a name="public-constants"></a>Открытые константы

|Имя|Description|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|Значение, указывающее, что время ожидания никогда не должно истечь.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`event`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h

**Пространство имен:** concurrency

## <a name="ctor"></a>журнале

Конструирует новое событие.

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>Remarks

## <a name="dtor"></a>событие ~

Уничтожает событие.

```cpp
~event();
```

### <a name="remarks"></a>Remarks

Ожидается, что потоки, ожидающие события, не будут выполняться при выполнении деструктора. Разрешение уничтожения события при наличии ожидающих его результатов потоков приводит к неопределенному поведению.

## <a name="reset"></a>перезапуск

Сбрасывает событие в несигнальное состояние.

```cpp
void reset();
```

## <a name="set"></a>параметр

Сигнализирует о событии.

```cpp
void set();
```

### <a name="remarks"></a>Remarks

Подача сигнала о событии может привести к тому, что произвольное число контекстов будет ожидать, когда событие станет готово к запуску.

## <a name="timeout_infinite"></a>timeout_infinite

Значение, указывающее, что время ожидания никогда не должно истечь.

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a>ожидания

Ожидает сигнала события.

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Указывает число миллисекунд до истечения времени ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает, что время ожидания отсутствует.

### <a name="return-value"></a>Возвращаемое значение

Если ожидание было удовлетворено, возвращается значение `0`; в противном случае значение `COOPERATIVE_WAIT_TIMEOUT`, чтобы указать, что время ожидания истекло без оповещения о событии.

> [!IMPORTANT]
> В приложении универсальная платформа Windows (UWP) не вызывайте `wait` в потоке ASTA, так как этот вызов может блокировать текущий поток и может привести к тому, что приложение перестанет отвечать.

## <a name="wait_for_multiple"></a>wait_for_multiple

Ожидает получения сигнала для нескольких событий.

```cpp
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_PPEvents*<br/>
Массив событий для ожидания. Число событий в массиве указывается параметром `count`.

*count*<br/>
Число событий в массиве, заданном в параметре `_PPEvents`.

*_FWaitAll*<br/>
Если задано значение **true**, параметр указывает, что все события в массиве, указанные в параметре `_PPEvents`, должны быть сигнальными, чтобы удовлетворить ожидания. Если задано значение **false**, то любое событие в массиве, передаваемое в параметре `_PPEvents`, становится сигнальным, что соответствует ожидания.

*_Timeout*<br/>
Указывает число миллисекунд до истечения времени ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает, что время ожидания отсутствует.

### <a name="return-value"></a>Возвращаемое значение

Если ожидание было удовлетворено, индекс в массиве, указанный в параметре `_PPEvents`, удовлетворяющий условию ожидания; в противном случае значение `COOPERATIVE_WAIT_TIMEOUT`, чтобы указать, что время ожидания истекло без соблюдения условия.

### <a name="remarks"></a>Remarks

Если параметр `_FWaitAll` имеет значение `true` чтобы указать, что все события должны быть сигнальными для удовлетворения ожидания, индекс, возвращаемый функцией, не несет никаких специальных значений, Кроме того факта, что он не является значением `COOPERATIVE_WAIT_TIMEOUT`.

> [!IMPORTANT]
> В приложении универсальная платформа Windows (UWP) не вызывайте `wait_for_multiple` в потоке ASTA, так как этот вызов может блокировать текущий поток и может привести к тому, что приложение перестанет отвечать.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
