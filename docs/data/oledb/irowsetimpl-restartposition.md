---
title: "IRowsetImpl::RestartPosition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs:
- C++
helpviewer_keywords:
- RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5cfdf198b68b3587146ebc4a666ac2e596d05aba
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Перемещает позицию следующей выборки в его начальное положение; то есть создать его положение при первоначальной набора строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Позиции строк не определено до **GetNextRow** вызывается. Можно переместить вперед в rowet путем вызова `RestartPosition` и затем выборку и прокрутку в обратном направлении.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)