---
title: "IRowsetImpl::m_bCanScrollBack | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
dev_langs:
- C++
helpviewer_keywords:
- m_bCanScrollBack
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 592d9ec5e0fdf74159592b9340f08ef6ee4ebe45
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplmbcanscrollback"></a>IRowsetImpl::m_bCanScrollBack
Указывает ли поставщик может его прокрутки курсора вперед.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned  m_bCanScrollBack:1;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Связанная с **DBPROP_CANSCROLLBACKWARDS** свойство в **DBPROPSET_ROWSET** группы. Поставщик должен поддерживать **DBPROP_CANSCROLLBACKWARDS** для **m_bCanFetchBackwards** истинным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)