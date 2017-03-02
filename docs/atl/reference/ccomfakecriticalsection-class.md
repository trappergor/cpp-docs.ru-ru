---
title: "Класс CComFakeCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComFakeCriticalSection
- CComFakeCriticalSection
- ATL::CComFakeCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
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
ms.openlocfilehash: 2c1269288e03a8ac9f359dad9acf1a81ddbc84c2
ms.lasthandoff: 02/24/2017

---
# <a name="ccomfakecriticalsection-class"></a>Класс CComFakeCriticalSection
Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критический раздел.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Поскольку нет критических разделов не выполняет никаких действий.|  
|[CComFakeCriticalSection::Lock](#lock)|Поскольку нет критических разделов не выполняет никаких действий.|  
|[CComFakeCriticalSection::Term](#term)|Поскольку нет критических разделов не выполняет никаких действий.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Поскольку нет критических разделов не выполняет никаких действий.|  
  
## <a name="remarks"></a>Примечания  
 `CComFakeCriticalSection`зеркально отражает методов [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Однако `CComFakeCriticalSection` не предоставляет критический раздел; таким образом, его методы ничего не делать.  
  
 Как правило, используется `CComFakeCriticalSection` через `typedef` имя, либо `AutoCriticalSection` или `CriticalSection`. При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), оба эти `typedef` имена ссылка `CComFakeCriticalSection`. При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), если они ссылаются на [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection`соответственно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="a-nameinita--ccomfakecriticalsectioninit"></a><a name="init"></a>CComFakeCriticalSection::Init  
 Поскольку нет критических разделов не выполняет никаких действий.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="a-namelocka--ccomfakecriticalsectionlock"></a><a name="lock"></a>CComFakeCriticalSection::Lock  
 Поскольку нет критических разделов не выполняет никаких действий.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="a-nameterma--ccomfakecriticalsectionterm"></a><a name="term"></a>CComFakeCriticalSection::Term  
 Поскольку нет критических разделов не выполняет никаких действий.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="a-nameunlocka--ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Поскольку нет критических разделов не выполняет никаких действий.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

