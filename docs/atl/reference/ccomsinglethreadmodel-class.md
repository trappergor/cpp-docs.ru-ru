---
title: "Класс CComSingleThreadModel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSingleThreadModel
- CComSingleThreadModel
- ATL::CComSingleThreadModel
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: ff5d8d2ced1d6fe0196888d8c746844ace8307f8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsinglethreadmodel-class"></a>Класс CComSingleThreadModel
Этот класс предоставляет методы для увеличивать и уменьшать значение переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Ссылается на класс `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылки на `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Уменьшает значение заданной переменной. Эта реализация не является потокобезопасным.|  
|[CComSingleThreadModel::Increment](#increment)|Увеличивает значение заданной переменной. Эта реализация не является потокобезопасным.|  
  
## <a name="remarks"></a>Примечания  
 `CComSingleThreadModel`Предоставляет методы для увеличивать и уменьшать значение переменной. В отличие от [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), эти методы не являются поточно ориентированными.  

 Как правило, используется `CComSingleThreadModel` посредством одного из двух `typedef` имена, либо [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Ссылаться на каждый класс `typedef` зависит потоковую модель, как показано в следующей таблице:  

  
|typedef|Однопотоковую модель|Потоковая модель подразделения|Бесплатная потоковая модель|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|С|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`сам определяет три `typedef` имена. `ThreadModelNoCS`ссылки на `CComSingleThreadModel`. `AutoCriticalSection`и `CriticalSection` ссылаться на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), который предоставляет пустой методы, связанные с получения и освобождения владения критической секции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 При использовании `CComSingleThreadModel`, `typedef` имя `AutoCriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не обеспечивает критическую секцию, ничего не делать его методы.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержит определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класс критическую секцию, ссылается `AutoCriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 В дополнение к `AutoCriticalSection`, можно использовать `typedef` имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если требуется исключить в коде запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 При использовании `CComSingleThreadModel`, `typedef` имя `CriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не обеспечивает критическую секцию, ничего не делать его методы.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержит определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класс критическую секцию, ссылается `CriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 В дополнение к `CriticalSection`, можно использовать `typedef` имя [AutoCriticalSection](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, если требуется исключить в коде запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::Decrement  
 Это статическая функция уменьшает значение переменной указывает `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную на единицу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат decrement.  
  
##  <a name="a-nameincrementa--ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel::Increment  
 Это статическая функция уменьшает значение переменной указывает `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную для увеличения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат приращения.  
  
##  <a name="a-namethreadmodelnocsa--ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 При использовании `CComSingleThreadModel`, `typedef` имя `ThreadModelNoCS` просто ссылается на `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Примечания  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержит определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класса ссылается `ThreadModelNoCS`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

