---
title: "IRowsetImpl::m_bCanFetchBack | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
dev_langs: C++
helpviewer_keywords: m_bCanFetchBack
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 09440f8453fe0ee13297c600b148927bacafc5da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplmbcanfetchback"></a>IRowsetImpl::m_bCanFetchBack
Указывает, поддерживает ли поставщик обратной выборка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Связанная с **DBPROP_CANFETCHBACKWARDS** свойство в **DBPROPSET_ROWSET** группы. Поставщик должен поддерживать **DBPROP_CANFETCHBACKWARDS** для **m_bCanFetchBackwards** истинным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)