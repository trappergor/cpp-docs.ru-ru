---
title: Класс CComMultiThreadModel
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 7ef803439d2d683633e8f9c00810542dd787541e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327671"
---
# <a name="ccommultithreadmodel-class"></a>Класс CComMultiThreadModel

`CComMultiThreadModel`обеспечивает безопасные потоки методы для приращения и декрементирования значения переменной.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModel
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModel::АвтокритическоеРазелия](#autocriticalsection)|Ссылки класса [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CComMultiThreadModel::Критическаясекция](#criticalsection)|Ссылки класса [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылки класса [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModel::Dэккремент](#decrement)|(Статик) Декреты значения указанной переменной безопасным способом.|
|[CCommultiThreadModel::Увеличение](#increment)|(Статик) Приращения значения указанной переменной безопасным способом.|

## <a name="remarks"></a>Remarks

Как правило, `CComMultiThreadModel` вы используете через одно из двух имен **typedef,** либо "CComObjectThreadModel" (atl-typedefs.md'ccomobjectthreadmodel или "CComGlobalsThreadModel" (atl-typedefs.md'ccomglobalsthreadmodel. Класс, на который ссылается каждый **тип,** зависит от используемой модели потоков, как показано в следующей таблице:

|typedef|Одноразовая резьба|Квартира резьбы|Бесплатное резьбовое|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

СЗ `CComSingleThreadModel`; МЗ`CComMultiThreadModel`

`CComMultiThreadModel`сама определяет три имен **typedef.** `AutoCriticalSection`и `CriticalSection` справочные классы, которые предоставляют методы получения и освобождения права собственности на критический раздел. `ThreadModelNoCS`справочные ссылки класса «CComMultiThreadModelNoCS»(ccommultithreadmodelnocs-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModel::АвтокритическоеРазелия

При `CComMultiThreadModel`использовании, **typedef** имя `AutoCriticalSection` ссылки класса [CComAutoCriticalSection](ccomautocriticalsection-class.md), который предоставляет методы для получения и освобождения собственности на объект критического раздела.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) и [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) также `AutoCriticalSection`содержат определения для . В следующей таблице показана взаимосвязь между классом модели `AutoCriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение `AutoCriticalSection`к, вы можете использовать **имя typedef** [CriticalSection.](#criticalsection) Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Следующий код смоделирован после [CComObjectRootEx](ccomobjectrootex-class.md)и `AutoCriticalSection` демонстрирует, что используется в среде потоков.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

Следующие таблицы показывают `InternalAddRef` результаты и `Lock` методы, `ThreadModel` в зависимости от параметра шаблона и модели резьбы, используемой приложением:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel - CComObjectThreadModel

|Метод|Одноместный или квартирный резьба|Бесплатные потоки|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является безопасным для потока.|Приращение является безопасным для потоков.|
|`Lock`|Ничего не делает; нет критического раздела для блокировки.|Критический раздел заблокирован.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel - CComObjectThreadModel::ThreadModelNoCS

|Метод|Одноместный или квартирный резьба|Бесплатные потоки|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является безопасным для потока.|Приращение является безопасным для потоков.|
|`Lock`|Ничего не делает; нет критического раздела для блокировки.|Ничего не делает; нет критического раздела для блокировки.|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModel::Критическаясекция

При `CComMultiThreadModel`использовании, **typedef** имя `CriticalSection` ссылки класса [CComCriticalSection](ccomcriticalsection-class.md), который предоставляет методы для получения и освобождения собственности на критический объект раздела.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) и [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) также `CriticalSection`содержат определения для . В следующей таблице показана взаимосвязь между классом модели `CriticalSection`потоков и критическим классом раздела, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение `CriticalSection`к, вы можете использовать **typedef** имя [AutoCriticalSection](#autocriticalsection). Не следует `AutoCriticalSection` указывать в глобальных объектах или статических участниках класса, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](#autocriticalsection).

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a>CComMultiThreadModel::Dэккремент

Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement), которая приспонивает значение переменной, на которую указывает *p.*

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая должна быть уничтожена.

### <a name="return-value"></a>Возвращаемое значение

Если результат decrement 0, то `Decrement` возвращает 0. Если результат decrement незерн, то значение возврата также ненулевое, но не может быть равно результату decrement.

### <a name="remarks"></a>Remarks

`InterlockedDecrement`предотвращает одновременное использование этой переменной более одного потока.

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a>CCommultiThreadModel::Увеличение

Эта статическая функция вызывает функцию Win32 [InterlockedIncrement,](/windows/win32/api/winnt/nf-winnt-interlockedincrement)которая приращает значение переменной, на которую указывает *p.*

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на переменную, которая будет приращена.

### <a name="return-value"></a>Возвращаемое значение

Если результат приращения 0, `Increment` то возвращает 0. Если результат приращения незеровен, то значение возврата также ненулевое, но не может быть равно результату приращения.

### <a name="remarks"></a>Remarks

`InterlockedIncrement`предотвращает одновременное использование этой переменной более одного потока.

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS

При `CComMultiThreadModel`использовании , `ThreadModelNoCS` **typedef** имя ссылки класса [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

`CComMultiThreadModelNoCS`обеспечивает безопасные потоки методы для приращения и декрементирования переменной; однако он не предусматривает критический раздел.

[CComSingleThreadModel,](ccomsinglethreadmodel-class.md) а `CComMultiThreadModelNoCS` также `ThreadModelNoCS`содержат определения для . В следующей таблице показана взаимосвязь между классом `ThreadModelNoCS`модели потоков и классом, на который ссылается:

|Класс, определяемый в|Класс, ссылки|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

Смотрите [CComMultiThreadModel::АвтокритическоеСекция](#autocriticalsection).

## <a name="see-also"></a>См. также раздел

[Класс CComSingleThreadModel](ccomsinglethreadmodel-class.md)<br/>
[Класс CComAutoCriticalSection](ccomautocriticalsection-class.md)<br/>
[Класс CComCriticalSection](ccomcriticalsection-class.md)<br/>
[Общие сведения о классах](../atl-class-overview.md)
