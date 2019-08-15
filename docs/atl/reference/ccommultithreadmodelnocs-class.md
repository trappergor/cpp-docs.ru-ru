---
title: Класс Ккоммултисреадмоделнокс
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
ms.openlocfilehash: 01c7f953b6b8916394ee4c2b5b27cf84af52b920
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497087"
---
# <a name="ccommultithreadmodelnocs-class"></a>Класс Ккоммултисреадмоделнокс

`CComMultiThreadModelNoCS`предоставляет потокобезопасные методы для увеличения и уменьшения значения переменной без блокировки критической секции или разблокировки.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Ссылка на `CComFakeCriticalSection`класс.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Ссылка на `CComMultiThreadModelNoCS`класс.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|Статически Уменьшает значение указанной переменной в безопасном для потоков режиме.|
|[CComMultiThreadModelNoCS::Increment](#increment)|Статически Увеличивает значение указанной переменной в безопасном для потоков режиме.|

## <a name="remarks"></a>Примечания

`CComMultiThreadModelNoCS`аналогичен [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) в том, что он предоставляет потокобезопасные методы для увеличения и уменьшения переменной. Однако при ссылке на класс критической секции с помощью `CComMultiThreadModelNoCS`методы, такие как `Lock` и `Unlock` , не будут выполнять никаких действий.

Обычно используется `CComMultiThreadModelNoCS` `ThreadModelNoCS` имя **typedef** . Это **Определение типа** определено `CComMultiThreadModelNoCS`в `CComMultiThreadModel`, и [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
>  Глобальные имена **typedef** [ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel) и [ккомглобалссреадмодел](atl-typedefs.md#ccomglobalsthreadmodel) не ссылаются `CComMultiThreadModelNoCS`.

В дополнение к `ThreadModelNoCS`, `CComMultiThreadModelNoCS` определяет `AutoCriticalSection` и `CriticalSection`. Эти два последних имени **typedef** ссылаются на [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md), которые предоставляют пустые методы, связанные с получением и освобождением критической секции.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection

При использовании `CComMultiThreadModelNoCS`имя `AutoCriticalSection` typedef ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Примечания

Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `AutoCriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, `AutoCriticalSection`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Кроме `AutoCriticalSection`того, можно использовать имя **typedef** [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection

При использовании `CComMultiThreadModelNoCS`имя `CriticalSection` typedef ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Примечания

Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `CriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, `CriticalSection`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Кроме `CriticalSection`того, можно использовать имя `AutoCriticalSection` **typedef** . Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement

Эта статическая функция вызывает функцию Win32 [интерлоккеддекремент](/windows/win32/api/winnt/nf-winnt-interlockeddecrement), которая уменьшает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которую необходимо уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Если результат декремента равен 0, то `Decrement` возвращает 0. Если результат декремента равен нулю, то возвращаемое значение также является ненулевым, но может не совпадать с результатом декремента.

### <a name="remarks"></a>Примечания

**Интерлоккеддекремент** предотвращает одновременное использование этой переменной более чем одним потоком.

##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment

Эта статическая функция вызывает функцию Win32 [интерлоккединкремент](/windows/win32/api/winnt/nf-winnt-interlockedincrement), которая увеличивает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которая должна быть увеличена.

### <a name="return-value"></a>Возвращаемое значение

Если результат приращения равен 0, то функция **Increment** возвращает 0. Если результат инкремента равен нулю, то возвращаемое значение также будет ненулевым, но может не совпадать с результатом приращения.

### <a name="remarks"></a>Примечания

**Интерлоккединкремент** предотвращает одновременное использование этой переменной более чем одним потоком.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS

При использовании `CComMultiThreadModelNoCS`имя `ThreadModelNoCS` typedef просто ссылается на `CComMultiThreadModelNoCS`.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Примечания

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `ThreadModelNoCS`. В следующей таблице показана связь между классом потоковой модели и классом, `ThreadModelNoCS`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Обратите внимание, что `ThreadModelNoCS` определение `CComMultiThreadModelNoCS` в предоставляет симметрию `CComSingleThreadModel`с `CComMultiThreadModel` и. Например, предположим, что пример кода `CComMultiThreadModel::AutoCriticalSection` объявлен в следующем определении **типа**:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Независимо от класса, указанного для `ThreadModel` ( `CComMultiThreadModelNoCS`например,), `_ThreadModel` разрешается соответствующим образом.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
