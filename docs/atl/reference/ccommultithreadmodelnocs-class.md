---
title: Класс CComMultiThreadModelNoCS | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758811b10757cd7903b4f1d6218a5f34f8a98462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccommultithreadmodelnocs-class"></a>Класс CComMultiThreadModelNoCS
`CComMultiThreadModelNoCS` Предоставляет методы поточно ориентированного увеличивать и уменьшать значение переменной, без блокировки критической секции или разблокирование функциональные возможности.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Ссылается на класс `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Ссылается на класс `CComMultiThreadModelNoCS`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Статический) Уменьшает значение заданной переменной в потокобезопасным способом.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(Статический) Увеличивает значение заданной переменной в потокобезопасным способом.|  
  
## <a name="remarks"></a>Примечания  
 `CComMultiThreadModelNoCS` Аналогично [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) в том, что он предоставляет методы поточно ориентированного увеличивать и уменьшать переменной. Тем не менее, при создании ссылки класс критической секции через `CComMultiThreadModelNoCS`, методов, таких как `Lock` и `Unlock` не выполняет никаких действий.  
  
 Как правило, используется `CComMultiThreadModelNoCS` через `ThreadModelNoCS` `typedef` имя. Это `typedef` определяется в `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Глобальный `typedef` имена [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) и [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) ссылка не `CComMultiThreadModelNoCS`.  
  
 В дополнение к `ThreadModelNoCS`, `CComMultiThreadModelNoCS` определяет `AutoCriticalSection` и `CriticalSection`. Эти последние две `typedef` имена ссылок [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), которые предоставляют пустой методы, связанные с получения и освобождения критической секции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `AutoCriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критической секции, ссылается `AutoCriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 В дополнение к `AutoCriticalSection`, можно использовать `typedef` имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, чтобы избежать отображения кода запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `CriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критической секции, ссылается `CriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 В дополнение к `CriticalSection`, можно использовать `typedef` имя `AutoCriticalSection`. Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, чтобы избежать отображения кода запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement  
 Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), который уменьшает значение переменной, на который указывает `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную на единицу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если результат декремента равна 0, то `Decrement` возвращает 0. Если результат декремента имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может равно результат декремента.  
  
### <a name="remarks"></a>Примечания  
 **InterlockedDecrement** предотвращает несколько потоков одновременно с помощью этой переменной.  
  
##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment  
 Эта статическая функция вызывает функцию Win32 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), которая увеличивает значение переменной, на который указывает `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную для увеличения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если результат приращения равна 0, то **приращения** возвращает 0. Если результат приращения имеет ненулевое значение, возвращаемое значение также является ненулевым, но не может равно результат приращения.  
  
### <a name="remarks"></a>Примечания  
 **InterlockedIncrement** предотвращает несколько потоков одновременно с помощью этой переменной.  
  
##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `ThreadModelNoCS` просто ссылается на `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Примечания  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержат определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класса, на который указывает `ThreadModelNoCS`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Обратите внимание, что определение `ThreadModelNoCS` в `CComMultiThreadModelNoCS` предоставляет симметричные с `CComMultiThreadModel` и `CComSingleThreadModel`. Например, предположим, что в коде `CComMultiThreadModel::AutoCriticalSection` объявлены следующие `typedef`:  
  
 [!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Независимо от того, класс, указанный для `ThreadModel` (такие как `CComMultiThreadModelNoCS`), `_ThreadModel` разрешает соответствующим образом.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)