---
title: CComMultiThreadModelNoCS Class
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: ef2038a203b6cbfb2564bbe11d508ee43df0fd1b
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328666"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS Class

`CComMultiThreadModelNoCS` Предоставляет методы поточно ориентированные увеличивать и уменьшать значение переменной, без критический раздел блокировки или разблокировки функциональные возможности.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание:|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Ссылается на класс `CComFakeCriticalSection`.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Ссылается на класс `CComMultiThreadModelNoCS`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание:|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Статический) Уменьшает значение указанной переменной в потокобезопасным способом.|
|[CComMultiThreadModelNoCS::Increment](#increment)|(Статический) Увеличивает значение указанной переменной в потокобезопасным способом.|

## <a name="remarks"></a>Примечания

`CComMultiThreadModelNoCS` аналогичен [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) тем, что он предоставляет поточно ориентированные методы для увеличение и уменьшение переменной. Тем не менее, при ссылке критический раздел класса посредством `CComMultiThreadModelNoCS`, методы, такие как `Lock` и `Unlock` не выполняет никаких действий.

Как правило, используется `CComMultiThreadModelNoCS` через `ThreadModelNoCS` **typedef** имя. Это **typedef** определяется в `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
>  Глобальный **typedef** имена [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) и [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) не ссылаются на `CComMultiThreadModelNoCS`.

В дополнение к `ThreadModelNoCS`, `CComMultiThreadModelNoCS` определяет `AutoCriticalSection` и `CriticalSection`. Эти два **typedef** имена ссылок [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), который предоставляет пустой методы, связанные с получения и освобождения критического раздела.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection

При использовании `CComMultiThreadModelNoCS`, **typedef** имя `AutoCriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Примечания

Так как `CComFakeCriticalSection` не предоставляет критическую секцию, ничего не делать его методы.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критическую секцию, ссылается `AutoCriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

В дополнение к `AutoCriticalSection`, можно использовать **typedef** имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если вы хотите исключить в коде запуска CRT.

### <a name="example"></a>Пример

См. в разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection

При использовании `CComMultiThreadModelNoCS`, **typedef** имя `CriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Примечания

Так как `CComFakeCriticalSection` не предоставляет критическую секцию, ничего не делать его методы.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критическую секцию, ссылается `CriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

В дополнение к `CriticalSection`, можно использовать **typedef** имя `AutoCriticalSection`. Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если вы хотите исключить в коде запуска CRT.

### <a name="example"></a>Пример

См. в разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement

Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](/windows/desktop/api/winnt/nf-winnt-interlockeddecrement), который уменьшает значение переменной, на которые указывают *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на переменную на единицу.

### <a name="return-value"></a>Возвращаемое значение

Если результат уменьшения равна 0, то `Decrement` возвращает 0. Если результат уменьшения имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может быть равно результат декремента.

### <a name="remarks"></a>Примечания

**InterlockedDecrement** запрещает использовать эту переменную, одновременно более одного потока.

##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment

Эта статическая функция вызывает функцию Win32 [InterlockedIncrement](/windows/desktop/api/winnt/nf-winnt-interlockedincrement), которая увеличивает значение переменной, на которые указывают *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на переменную для увеличения.

### <a name="return-value"></a>Возвращаемое значение

Если результат приращения равен 0, затем **приращения** возвращает 0. Если результат приращения имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может быть равно результат приращения.

### <a name="remarks"></a>Примечания

**InterlockedIncrement** запрещает использовать эту переменную, одновременно более одного потока.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS

При использовании `CComMultiThreadModelNoCS`, **typedef** имя `ThreadModelNoCS` просто ссылается на `CComMultiThreadModelNoCS`.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Примечания

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класс, который ссылается `ThreadModelNoCS`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Обратите внимание, что определение `ThreadModelNoCS` в `CComMultiThreadModelNoCS` предоставляет симметричные с `CComMultiThreadModel` и `CComSingleThreadModel`. Например, предположим, что в коде `CComMultiThreadModel::AutoCriticalSection` объявлены следующие **typedef**:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Независимо от того, класс, указанный для `ThreadModel` (такие как `CComMultiThreadModelNoCS`), `_ThreadModel` разрешает соответствующим образом.

### <a name="example"></a>Пример

См. в разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
