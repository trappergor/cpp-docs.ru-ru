---
title: "Класс CComFakeCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 6232a3e8b6c392361a1e57681e9ba4dff66d6aa4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="ccomfakecriticalsection-class"></a>Класс CComFakeCriticalSection
Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Lock](#lock)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Term](#term)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Не выполняет никаких действий, так как она не критической секции.|  
  
## <a name="remarks"></a>Примечания  
 `CComFakeCriticalSection`зеркально отражает методов [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Однако `CComFakeCriticalSection` не предоставляет критической секции; таким образом, его методы не выполняют никаких действий.  
  
 Как правило, используется `CComFakeCriticalSection` через `typedef` имя, либо `AutoCriticalSection` или `CriticalSection`. При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), оба эти `typedef` имена ссылка `CComFakeCriticalSection`. При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), если они ссылаются на [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection`соответственно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

