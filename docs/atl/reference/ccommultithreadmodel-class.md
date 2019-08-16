---
title: Класс Ккоммултисреадмодел
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
ms.openlocfilehash: 74fb68eead498685ef252968124368863e27be75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497103"
---
# <a name="ccommultithreadmodel-class"></a>Класс Ккоммултисреадмодел

`CComMultiThreadModel`предоставляет потокобезопасные методы для увеличения и уменьшения значения переменной.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModel
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md).|
|[Ккоммултисреадмодел:: CriticalSection](#criticalsection)|Ссылается на класс [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылается на класс [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккоммултисреадмодел::D екремент](#decrement)|Статически Уменьшает значение указанной переменной в безопасном для потоков режиме.|
|[Ккоммултисреадмодел:: Increment](#increment)|Статически Увеличивает значение указанной переменной в безопасном для потоков режиме.|

## <a name="remarks"></a>Примечания

Как правило, используется `CComMultiThreadModel` одно из двух имен **typedef** : [ккомобжектсреадмодел] (ATL-typedefs. md # ккомобжектсреадмодел или [ккомглобалссреадмодел] (ATL-typedefs. md # ккомглобалссреадмодел. Класс, на который ссылается каждое **Определение типа** , зависит от используемой потоковой модели, как показано в следующей таблице.

|typedef|Единая Организация|Потоковое подразделение|Свободная организация потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M =`CComMultiThreadModel`

`CComMultiThreadModel`сам определяет три имени **typedef** . `AutoCriticalSection`и `CriticalSection` ссылочные классы, предоставляющие методы для получения и освобождения владения критическим разделом. `ThreadModelNoCS`REFERENCES Class [Ккоммултисреадмоделнокс (ккоммултисреадмоделнокс-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="autocriticalsection"></a>Ккоммултисреадмодел:: Аутокритикалсектион

При использовании `CComMultiThreadModel`имя `AutoCriticalSection` typedef ссылается на класс [ккомаутокритикалсектион](ccomautocriticalsection-class.md), который предоставляет методы для получения и освобождения владения объектом критической секции.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Примечания

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) и [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md) также содержат определения для `AutoCriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, `AutoCriticalSection`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Кроме `AutoCriticalSection`того, можно использовать имя **typedef** [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Следующий код моделируется после [CComObjectRootEx](ccomobjectrootex-class.md)и демонстрирует `AutoCriticalSection` использование в потоковой среде.

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

В следующих таблицах показаны результаты `InternalAddRef` методов и `Lock` `ThreadModel` , в зависимости от параметра шаблона и модели потоков, используемой приложением:

### <a name="threadmodel--ccomobjectthreadmodel"></a>Среадмодел = Ккомобжектсреадмодел

|Метод|Единый или Апартаментный поток|Свободная организация потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является потокобезопасным.|Приращение является потокобезопасным.|
|`Lock`|Не выполняет никаких действий; нет критической секции для блокировки.|Критическая секция заблокирована.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS

|Метод|Единый или Апартаментный поток|Свободная организация потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является потокобезопасным.|Приращение является потокобезопасным.|
|`Lock`|Не выполняет никаких действий; нет критической секции для блокировки.|Не выполняет никаких действий; нет критической секции для блокировки.|

##  <a name="criticalsection"></a>Ккоммултисреадмодел:: CriticalSection

При использовании `CComMultiThreadModel`имя `CriticalSection` typedef ссылается на класс [ккомкритикалсектион](ccomcriticalsection-class.md), который предоставляет методы для получения и освобождения владения объектом критической секции.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Примечания

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) и [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md) также содержат определения для `CriticalSection`. В следующей таблице показана связь между классом потоковой модели и классом критического раздела, `CriticalSection`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Кроме `CriticalSection`того, можно использовать имя **typedef** [аутокритикалсектион](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](#autocriticalsection).

##  <a name="decrement"></a>Ккоммултисреадмодел::D екремент

Эта статическая функция вызывает функцию Win32 [интерлоккеддекремент](/windows/win32/api/winnt/nf-winnt-interlockeddecrement), которая уменьшает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которую необходимо уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Если результат декремента равен 0, то `Decrement` возвращает 0. Если результат декремента равен нулю, то возвращаемое значение также является ненулевым, но может не совпадать с результатом декремента.

### <a name="remarks"></a>Примечания

`InterlockedDecrement`предотвращает одновременное использование этой переменной более чем одним потоком.

##  <a name="increment"></a>Ккоммултисреадмодел:: Increment

Эта статическая функция вызывает функцию Win32 [интерлоккединкремент](/windows/win32/api/winnt/nf-winnt-interlockedincrement), которая увеличивает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на переменную, которая должна быть увеличена.

### <a name="return-value"></a>Возвращаемое значение

Если результатом приращения является 0, то `Increment` возвращает 0. Если результат инкремента равен нулю, то возвращаемое значение также будет ненулевым, но может не совпадать с результатом приращения.

### <a name="remarks"></a>Примечания

`InterlockedIncrement`предотвращает одновременное использование этой переменной более чем одним потоком.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

При использовании `CComMultiThreadModel`имя `ThreadModelNoCS` typedef ссылается на класс [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Примечания

`CComMultiThreadModelNoCS`предоставляет потокобезопасные методы для увеличения и уменьшения переменной; Однако он не предоставляет критическую секцию.

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) , `CComMultiThreadModelNoCS` а также содержит определения `ThreadModelNoCS`для. В следующей таблице показана связь между классом потоковой модели и классом, `ThreadModelNoCS`на который ссылается:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](#autocriticalsection).

## <a name="see-also"></a>См. также

[Класс CComSingleThreadModel](ccomsinglethreadmodel-class.md)<br/>
[Класс CComAutoCriticalSection](ccomautocriticalsection-class.md)<br/>
[Класс CComCriticalSection](ccomcriticalsection-class.md)<br/>
[Обзор класса](../atl-class-overview.md)
