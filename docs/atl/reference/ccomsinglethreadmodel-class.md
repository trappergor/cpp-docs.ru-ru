---
title: Класс Ккомсинглесреадмодел
ms.date: 2/29/2020
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
ms.openlocfilehash: 9b111e06ba475a5077ba36b2235e8bd530302189
ms.sourcegitcommit: ab8d7b47b63b62892a1256a09b1324a9a136eccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "78215461"
---
# <a name="ccomsinglethreadmodel-class"></a>Класс Ккомсинглесреадмодел

Этот класс предоставляет методы для увеличения и уменьшения значения переменной.

## <a name="syntax"></a>Синтаксис

```
class CComSingleThreadModel
```

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|[Ккомсинглесреадмодел:: Аутокритикалсектион](#autocriticalsection)|Ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).|
|[Ккомсинглесреадмодел:: CriticalSection](#criticalsection)|Ссылается на `CComFakeCriticalSection`класса.|
|[Ккомсинглесреадмодел:: Среадмоделнокс](#threadmodelnocs)|Ссылки `CComSingleThreadModel`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Ккомсинглесреадмодел::D екремент](#decrement)|Уменьшает значение указанной переменной. Эта реализация не является потокобезопасной.|
|[Ккомсинглесреадмодел:: Increment](#increment)|Увеличивает значение указанной переменной. Эта реализация не является потокобезопасной.|

## <a name="remarks"></a>Remarks

`CComSingleThreadModel` предоставляет методы для увеличения и уменьшения значения переменной. В отличие от [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md), эти методы не являются потокобезопасными.

Как правило, `CComSingleThreadModel` используется одним из двух имен **typedef** : [ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel) или [ккомглобалссреадмодел](atl-typedefs.md#ccomglobalsthreadmodel). Класс, на который ссылается каждое **Определение типа** , зависит от используемой потоковой модели, как показано в следующей таблице.

|typedef|Модель с одним потоком|Потоковая модель потоков|Модель свободной потоковой модели|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComSingleThreadModel` сам определяет три имени **typedef** . `ThreadModelNoCS` ссылки `CComSingleThreadModel`. `AutoCriticalSection` и `CriticalSection` ссылочного класса [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md), который предоставляет пустые методы, связанные с получением и освобождением владения критическим разделом.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="autocriticalsection"></a>Ккомсинглесреадмодел:: Аутокритикалсектион

При использовании `CComSingleThreadModel`имя **typedef** `AutoCriticalSection` ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предоставляет критического раздела, его методы не выполняют никаких действий.

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `AutoCriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, на который ссылается `AutoCriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение к `AutoCriticalSection`можно использовать имя **typedef** [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>Ккомсинглесреадмодел:: CriticalSection

При использовании `CComSingleThreadModel`имя **typedef** `CriticalSection` ссылается на класс [ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предоставляет критического раздела, его методы не выполняют никаких действий.

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `CriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, на который ссылается `CriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение к `CriticalSection`можно использовать имя **typedef** [аутокритикалсектион](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>Ккомсинглесреадмодел::D екремент

Эта статическая функция уменьшает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которую необходимо уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Результат декремента.

##  <a name="increment"></a>Ккомсинглесреадмодел:: Increment

Эта статическая функция увеличивает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которая должна быть увеличена.

### <a name="return-value"></a>Возвращаемое значение

Результат приращения.

##  <a name="threadmodelnocs"></a>Ккомсинглесреадмодел:: Среадмоделнокс

При использовании `CComSingleThreadModel`имя **typedef** `ThreadModelNoCS` просто ссылается на `CComSingleThreadModel`.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

[Ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) и [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `ThreadModelNoCS`. В следующей таблице показана связь между классом потоковой модели и классом, на который ссылается `ThreadModelNoCS`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>См. также раздел

[Обзор класса](../../atl/atl-class-overview.md)
