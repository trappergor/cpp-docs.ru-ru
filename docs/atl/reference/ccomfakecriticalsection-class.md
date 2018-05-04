---
title: Класс CComFakeCriticalSection | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a042e52439579cfb1b4145b1691f5a00128754c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomfakecriticalsection-class"></a>Класс CComFakeCriticalSection
Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Lock](#lock)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Term](#term)|Не выполняет никаких действий, так как она не критической секции.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Не выполняет никаких действий, так как она не критической секции.|  
  
## <a name="remarks"></a>Примечания  
 `CComFakeCriticalSection` зеркально отражает методов [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Однако `CComFakeCriticalSection` не предоставляет критической секции; таким образом, его методы не выполняют никаких действий.  
  
 Как правило, используется `CComFakeCriticalSection` через `typedef` имя, либо `AutoCriticalSection` или `CriticalSection`. При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), оба эти `typedef` имена ссылка `CComFakeCriticalSection`. При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), если они ссылаются на [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection`соответственно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="init"></a>  CComFakeCriticalSection::Init  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="lock"></a>  CComFakeCriticalSection::Lock  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="term"></a>  CComFakeCriticalSection::Term  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock  
 Не выполняет никаких действий, так как она не критической секции.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
