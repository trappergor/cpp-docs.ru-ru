---
title: "Класс CComMultiThreadModelNoCS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComMultiThreadModelNoCS
- CComMultiThreadModelNoCS
- ATL.CComMultiThreadModelNoCS
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: dd14e5c941da5383dce19e9f7f539bfb9909759f
ms.lasthandoff: 02/28/2017

---
# <a name="ccommultithreadmodelnocs-class"></a>Класс CComMultiThreadModelNoCS
`CComMultiThreadModelNoCS`Предоставляет методы поточно ориентированные увеличивать и уменьшать значение переменной без критический раздел блокировки или разблокировки функциональные возможности.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>Члены  
  
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
 `CComMultiThreadModelNoCS`Аналогично [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) в том, что он предоставляет методы поточно ориентированные увеличивать и уменьшать переменной. Тем не менее, когда требуется сослаться через класс критический раздел `CComMultiThreadModelNoCS`, методов, таких как `Lock` и `Unlock` не выполняет никаких действий.  
  
 Как правило, используется `CComMultiThreadModelNoCS` через `ThreadModelNoCS` `typedef` имя. Это `typedef` определяется в `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Глобальная `typedef` имена [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) и [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) ссылка не `CComMultiThreadModelNoCS`.  
  
 В дополнение к `ThreadModelNoCS`, `CComMultiThreadModelNoCS` определяет `AutoCriticalSection` и `CriticalSection`. Эти две последние `typedef` имена ссылок [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), который предоставляет пустой методы, связанные с получения и освобождения критического раздела.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `AutoCriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не обеспечивает критическую секцию, ничего не делать его методы.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержит определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класс критическую секцию, ссылается `AutoCriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 В дополнение к `AutoCriticalSection`, можно использовать `typedef` имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если требуется исключить в коде запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `CriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не обеспечивает критическую секцию, ничего не делать его методы.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержит определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класс критическую секцию, ссылается `CriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 В дополнение к `CriticalSection`, можно использовать `typedef` имя `AutoCriticalSection`. Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если требуется исключить в коде запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 Эта статическая функция вызывает функцию Win32 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), который уменьшает значение переменной, на который указывает `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную на единицу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если результат decrement равна 0, то `Decrement` возвращает 0. Если результат decrement ненулевое значение, возвращаемое значение также является ненулевым, но не может равняться результат decrement.  
  
### <a name="remarks"></a>Примечания  
 **InterlockedDecrement** предотвращает несколько потоков одновременно с помощью этой переменной.  
  
##  <a name="a-nameincrementa--ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 Эта статическая функция вызывает функцию Win32 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), который увеличивает значение переменной, на который указывает `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную для увеличения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если результат приращения равна 0, то **приращения** возвращает 0. Если результат приращения ненулевое значение, возвращаемое значение также является ненулевым, но не может равняться результат приращения.  
  
### <a name="remarks"></a>Примечания  
 **InterlockedIncrement** предотвращает несколько потоков одновременно с помощью этой переменной.  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 При использовании `CComMultiThreadModelNoCS`, `typedef` имя `ThreadModelNoCS` просто ссылается на `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Примечания  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) также содержит определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класса ссылается `ThreadModelNoCS`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Обратите внимание, что определение `ThreadModelNoCS` в `CComMultiThreadModelNoCS` предоставляет симметрии с `CComMultiThreadModel` и `CComSingleThreadModel`. Например, предположим, что в коде `CComMultiThreadModel::AutoCriticalSection` объявлены следующие `typedef`:  
  
 [!code-cpp[NVC_ATL_COM&#37;](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Независимо от того, класс, указанный для `ThreadModel` (таких как `CComMultiThreadModelNoCS`), `_ThreadModel` разрешает соответствующим образом.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
