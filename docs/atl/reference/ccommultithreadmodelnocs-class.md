---
title: Класс CComMultiThreadModelNoCS
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
ms.openlocfilehash: 4d41ffcfccbd7ef65ed86df79bffec1209a88cd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327656"
---
# <a name="ccommultithreadmodelnocs-class"></a>Класс CComMultiThreadModelNoCS

`CComMultiThreadModelNoCS`предоставляет безопасные потоки методы для приращения и декрементирования значения переменной, без критической блокировки сечения или разблокировки функциональности.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Автокритическое](#autocriticalsection)|Ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::Критическаясекция](#criticalsection)|Ссылки `CComFakeCriticalSection`класса .|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Ссылки `CComMultiThreadModelNoCS`класса .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModelNoCS::D](#decrement)|(Статик) Декреты значения указанной переменной безопасным способом.|
|[CCommultiThreadModelNoCS::Увеличение](#increment)|(Статик) Приращения значения указанной переменной безопасным способом.|

## <a name="remarks"></a>Remarks

`CComMultiThreadModelNoCS`похож на [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) в том, что он обеспечивает поток-безопасные методы для приращения и decrementing переменной. Однако, когда вы ссылаетесь на критический класс раздела через, `CComMultiThreadModelNoCS`методы, такие как `Lock` и `Unlock` не будет ничего делать.

Как правило, `CComMultiThreadModelNoCS` вы `ThreadModelNoCS` используете через имя **typedef.** Этот **typedef** определяется в `CComMultiThreadModelNoCS`, `CComMultiThreadModel`и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
> Глобальный **typedef** имена [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) и [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) не ссылаются `CComMultiThreadModelNoCS`.

В дополнение `ThreadModelNoCS` `CComMultiThreadModelNoCS` к `AutoCriticalSection` , `CriticalSection`определяет и . Эти последние два **typedef** имена ссылки [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), который обеспечивает пустые методы, связанные с получением и выпуском критического раздела.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::Автокритическое

При `CComMultiThreadModelNoCS`использовании , `AutoCriticalSection` **typedef** имя ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предусмотрен критический раздел, его методы ничего не делают.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также `AutoCriticalSection`содержат определения для . В следующей таблице показана взаимосвязь между классом модели `AutoCriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

В дополнение `AutoCriticalSection`к, вы можете использовать **имя typedef** [CriticalSection.](#criticalsection) Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::Критическаясекция

При `CComMultiThreadModelNoCS`использовании , `CriticalSection` **typedef** имя ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предусмотрен критический раздел, его методы ничего не делают.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также `CriticalSection`содержат определения для . В следующей таблице показана взаимосвязь между классом модели `CriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

В дополнение `CriticalSection`к, вы можете `AutoCriticalSection`использовать имя **typedef** . Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::D

Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement), которая приспонивает значение переменной, на которую указывает *p.*

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая должна быть уничтожена.

### <a name="return-value"></a>Возвращаемое значение

Если результат decrement 0, то `Decrement` возвращает 0. Если результат decrement незерн, то значение возврата также ненулевое, но не может быть равно результату decrement.

### <a name="remarks"></a>Remarks

**InterlockedDecrement** предотвращает одновременное использование этой переменной более одного потока.

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CCommultiThreadModelNoCS::Увеличение

Эта статическая функция вызывает функцию Win32 [InterlockedIncrement,](/windows/win32/api/winnt/nf-winnt-interlockedincrement)которая приращает значение переменной, на которую указывает *p.*

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая будет приращена.

### <a name="return-value"></a>Возвращаемое значение

Если результат приращения 0, то **приращение** возвращает 0. Если результат приращения незеровен, то значение возврата также ненулевое, но не может быть равно результату приращения.

### <a name="remarks"></a>Remarks

**InterlockedIncrement** предотвращает одновременное использование этой переменной более одного потока.

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS

При `CComMultiThreadModelNoCS`использовании, имя `ThreadModelNoCS` `CComMultiThreadModelNoCS` **typedef** просто ссылки.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также `ThreadModelNoCS`содержат определения для . В следующей таблице показана взаимосвязь между классом `ThreadModelNoCS`модели потоков и классом, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Обратите внимание, `ThreadModelNoCS` что `CComMultiThreadModelNoCS` определение в `CComMultiThreadModel` `CComSingleThreadModel`обеспечивает симметрию с и . Например, предположим, `CComMultiThreadModel::AutoCriticalSection` что код образца в заявленном следующем **typedef:**

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Независимо от класса, `ThreadModel` указанного `CComMultiThreadModelNoCS` `_ThreadModel` для (например, ), решает соответственно.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
