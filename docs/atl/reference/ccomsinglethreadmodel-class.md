---
title: Класс CComSingleThreadModel
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
ms.openlocfilehash: 3d8169c999ba96049bc711033f7ba2ef53989663
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327333"
---
# <a name="ccomsinglethreadmodel-class"></a>Класс CComSingleThreadModel

Этот класс предоставляет методы для приращения и декрементирования значения переменной.

## <a name="syntax"></a>Синтаксис

```
class CComSingleThreadModel
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComSingleThreadModel::Автокритическое](#autocriticalsection)|Ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComSingleThreadModel::Критическаясекция](#criticalsection)|Ссылки `CComFakeCriticalSection`класса .|
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылки `CComSingleThreadModel`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSingleThreadModel::D](#decrement)|Уточняет значение указанной переменной. Эта реализация не является безопасной для потока.|
|[CComSingleThreadModel::Increment](#increment)|Приращения значения указанной переменной. Эта реализация не является безопасной для потока.|

## <a name="remarks"></a>Remarks

`CComSingleThreadModel`предоставляет методы для приращения и декремента значения переменной. В отличие от [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS,](../../atl/reference/ccommultithreadmodelnocs-class.md)эти методы не являются безопасными для потоков.

Как правило, `CComSingleThreadModel` вы используете через один из двух **имен typedef,** либо [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Класс, на который ссылается каждый **тип,** зависит от используемой модели потоков, как показано в следующей таблице:

|typedef|Модель одиночного потока|Модель резьбы по квартирам|Бесплатная модель резьбы|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

СЗ `CComSingleThreadModel`; МЗ`CComMultiThreadModel`

`CComSingleThreadModel`сама определяет три имен **typedef.** `ThreadModelNoCS`ссылки `CComSingleThreadModel`. `AutoCriticalSection`и `CriticalSection` эталонный класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), который предоставляет пустые методы, связанные с получением и освобождением права собственности на критический раздел.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel::Автокритическое

При `CComSingleThreadModel`использовании , `AutoCriticalSection` **typedef** имя ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предусмотрен критический раздел, его методы ничего не делают.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат `AutoCriticalSection`определения для . В следующей таблице показана взаимосвязь между классом модели `AutoCriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение `AutoCriticalSection`к, вы можете использовать **имя typedef** [CriticalSection.](#criticalsection) Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel::Критическаясекция

При `CComSingleThreadModel`использовании , `CriticalSection` **typedef** имя ссылки класса [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

Поскольку `CComFakeCriticalSection` не предусмотрен критический раздел, его методы ничего не делают.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат `CriticalSection`определения для . В следующей таблице показана взаимосвязь между классом модели `CriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение `CriticalSection`к, вы можете использовать **typedef** имя [AutoCriticalSection](#autocriticalsection). Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::D

Эта статическая функция деметражев значение переменной указал на *р*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая должна быть уничтожена.

### <a name="return-value"></a>Возвращаемое значение

Результат decrement.

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel::Increment

Эта статическая функция приращает значение переменной, на которую указывает *р.*

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая будет приращена.

### <a name="return-value"></a>Возвращаемое значение

Результат приращения.

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS

При `CComSingleThreadModel`использовании, имя `ThreadModelNoCS` `CComSingleThreadModel` **typedef** просто ссылки.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат `ThreadModelNoCS`определения для . В следующей таблице показана взаимосвязь между классом `ThreadModelNoCS`модели потоков и классом, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
