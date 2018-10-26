---
title: Класс CComMultiThreadModel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85d36b329a28ddac09e981fa9ca0a01cb8b0bedf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060381"
---
# <a name="ccommultithreadmodel-class"></a>Класс CComMultiThreadModel

`CComMultiThreadModel` Предоставляет методы поточно ориентированные увеличивать и уменьшать значение переменной.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModel
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Ссылается на класс [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылается на класс [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|(Статический) Уменьшает значение указанной переменной в потокобезопасным способом.|
|[CComMultiThreadModel::Increment](#increment)|(Статический) Увеличивает значение указанной переменной в потокобезопасным способом.|

## <a name="remarks"></a>Примечания

Как правило, используется `CComMultiThreadModel` посредством одного из двух **typedef** имена, [CComObjectThreadModel] (atl-typedefs.md #ccomobjectthreadmodel или [CComGlobalsThreadModel] (atl-typedefs.md #ccomglobalsthreadmodel. Класс, который ссылается каждый **typedef** зависит потоковую модель, как показано в следующей таблице:

|typedef|Последовательная обработка|Потоковое|Свободных потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComMultiThreadModel` сам определяет три **typedef** имена. `AutoCriticalSection` и `CriticalSection` ссылки на классы, предоставляющие методы получения и освобождения владения критической секции. `ThreadModelNoCS` ссылки на класс [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection

При использовании `CComMultiThreadModel`, **typedef** имя `AutoCriticalSection` ссылается на класс [CComAutoCriticalSection](ccomautocriticalsection-class.md), который предоставляет методы для получения и освобождения владения критической секции объект.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Примечания

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) и [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) также содержат определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критическую секцию, ссылается `AutoCriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение к `AutoCriticalSection`, можно использовать **typedef** имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если вы хотите исключить в коде запуска CRT.

### <a name="example"></a>Пример

Следующий код моделируется [CComObjectRootEx](ccomobjectrootex-class.md)и демонстрирует `AutoCriticalSection` , используемых в среде потоков.

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

В следующих таблицах показаны результаты `InternalAddRef` и `Lock` методы, в зависимости от `ThreadModel` параметр шаблона и модели потоков, используемых приложением:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel

|Метод|Один или потоковое|Свободных потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является поточно ориентированной.|Приращение является поточно ориентированной.|
|`Lock`|Не выполняет никаких действий; Нет критических раздела для блокировки.|Критический раздел заблокирован.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS

|Метод|Один или потоковое|Свободных потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является поточно ориентированной.|Приращение является поточно ориентированной.|
|`Lock`|Не выполняет никаких действий; Нет критических раздела для блокировки.|Не выполняет никаких действий; Нет критических раздела для блокировки.|

##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection

При использовании `CComMultiThreadModel`, **typedef** имя `CriticalSection` ссылается на класс [CComCriticalSection](ccomcriticalsection-class.md), который предоставляет методы для получения и освобождения владения объект критической секции.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Примечания

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) и [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) также содержат определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критическую секцию, ссылается `CriticalSection`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

В дополнение к `CriticalSection`, можно использовать **typedef** имя [AutoCriticalSection](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если вы хотите исключить в коде запуска CRT.

### <a name="example"></a>Пример

См. в разделе [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModel::Decrement

Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement), который уменьшает значение переменной, на которые указывают *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на переменную на единицу.

### <a name="return-value"></a>Возвращаемое значение

Если результат уменьшения равна 0, то `Decrement` возвращает 0. Если результат уменьшения имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может быть равно результат декремента.

### <a name="remarks"></a>Примечания

`InterlockedDecrement` запрещает несколько потоков одновременно с помощью этой переменной.

##  <a name="increment"></a>  CComMultiThreadModel::Increment

Эта статическая функция вызывает функцию Win32 [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement), которая увеличивает значение переменной, на которые указывают *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на переменную для увеличения.

### <a name="return-value"></a>Возвращаемое значение

Если результат приращения равен 0, затем `Increment` возвращает 0. Если результат приращения имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может быть равно результат приращения.

### <a name="remarks"></a>Примечания

`InterlockedIncrement` запрещает несколько потоков одновременно с помощью этой переменной.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

При использовании `CComMultiThreadModel`, **typedef** имя `ThreadModelNoCS` ссылается на класс [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Примечания

`CComMultiThreadModelNoCS` Предоставляет поточно ориентированные методы для увеличение и уменьшение переменной; Тем не менее она предоставляет критический раздел.

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) и `CComMultiThreadModelNoCS` также содержат определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класс, который ссылается `ThreadModelNoCS`:

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

См. в разделе [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

## <a name="see-also"></a>См. также

[Класс CComSingleThreadModel](ccomsinglethreadmodel-class.md)<br/>
[Класс CComAutoCriticalSection](ccomautocriticalsection-class.md)<br/>
[Класс CComCriticalSection](ccomcriticalsection-class.md)<br/>
[Общие сведения о классе](../atl-class-overview.md)
