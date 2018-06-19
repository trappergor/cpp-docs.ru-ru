---
title: Класс CComSingleThreadModel | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 175cc1b867356949ca861f7015dedb6d64c4282f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365104"
---
# <a name="ccomsinglethreadmodel-class"></a>Класс CComSingleThreadModel
Этот класс предоставляет методы для увеличивать и уменьшать значение переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Ссылается на класс `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Ссылки на `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Уменьшает значение заданной переменной. Данная реализация не является потокобезопасным.|  
|[CComSingleThreadModel::Increment](#increment)|Увеличивает значение заданной переменной. Данная реализация не является потокобезопасным.|  
  
## <a name="remarks"></a>Примечания  
 `CComSingleThreadModel` Предоставляет методы для увеличивать и уменьшать значение переменной. В отличие от [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), эти методы не являются потокобезопасными.  

 Как правило, используется `CComSingleThreadModel` посредством одного из двух `typedef` имена, либо [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Класс, который ссылается каждый `typedef` зависит потоковую модель, как показано в следующей таблице:  

  
|typedef|Один потоковой модели|Потоковая модель подразделения|Свободной потоковой модели|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M = `CComMultiThreadModel`  
  
 `CComSingleThreadModel` сам определяет три `typedef` имена. `ThreadModelNoCS` ссылки на `CComSingleThreadModel`. `AutoCriticalSection` и `CriticalSection` ссылки класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), которые предоставляют пустой методы, связанные с получения и освобождения владения критической секции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection  
 При использовании `CComSingleThreadModel`, `typedef` имя `AutoCriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `AutoCriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критической секции, ссылается `AutoCriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 В дополнение к `AutoCriticalSection`, можно использовать `typedef` имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, чтобы избежать отображения кода запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection  
 При использовании `CComSingleThreadModel`, `typedef` имя `CriticalSection` ссылается на класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CComFakeCriticalSection` не предоставляет критическую секцию, его методы не выполняют никаких действий.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `CriticalSection`. В следующей таблице показаны связи между потоковой модели класса и класса критической секции, ссылается `CriticalSection`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 В дополнение к `CriticalSection`, можно использовать `typedef` имя [AutoCriticalSection](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектов или члены статических классов, чтобы избежать отображения кода запуска CRT.  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>  CComSingleThreadModel::Decrement  
 Это статическая функция уменьшает значение переменной указывает `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную на единицу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат декремента.  
  
##  <a name="increment"></a>  CComSingleThreadModel::Increment  
 Это статическая функция уменьшает значение переменной указывает `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на переменную для увеличения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат приращения.  
  
##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS  
 При использовании `CComSingleThreadModel`, `typedef` имя `ThreadModelNoCS` просто ссылается на `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Примечания  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) содержат определения для `ThreadModelNoCS`. В следующей таблице показаны связи между потоковой модели класса и класса, на который указывает `ThreadModelNoCS`:  
  
|Класс, определенный в|Ссылка на класс|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Пример  
 В разделе [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
