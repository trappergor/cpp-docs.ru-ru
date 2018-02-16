---
title: "IDBInitializeImpl::m_dwStatus | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
dev_langs:
- C++
helpviewer_keywords:
- m_dwStatus
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2ca6b9b072b28225883ff1972475521f0cab76c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="idbinitializeimplmdwstatus"></a>IDBInitializeImpl::m_dwStatus
Флаги источника данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
DWORD m_dwStatus;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Эти флаги укажите или указать состояние различных атрибутов для объекта источника данных. Содержит один или несколько из следующих `enum` значения:  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|**DSF_MASK_INIT**|Маска, чтобы включить восстановление инициализированном состоянии.|  
|**DSF_PERSIST_DIRTY**|Значение, если объект источника данных требует сохраняемости (то есть, если произошли изменения).|  
|**DSF_INITIALIZED**|Значение, если инициализирован источник данных.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)