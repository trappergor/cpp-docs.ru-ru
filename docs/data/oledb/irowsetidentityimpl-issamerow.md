---
title: "IRowsetIdentityImpl::IsSameRow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IsSameRow method
ms.assetid: e35ad54e-73f1-4dc0-8d8c-9e98202baf0a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68f7b5add310765616146a05b377df58408a8e19
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetidentityimplissamerow"></a>IRowsetIdentityImpl::IsSameRow
Сравнивает два дескрипторы строк для просмотра, если они ссылаются на той же строке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(IsSameRow )(HROW hThisRow,  
   HROW hThatRow);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Чтобы сравнить дескрипторы строк, этот метод приводит **HROW** дескрипторы для **RowClass** элементов и вызовов `memcmp` на указатели.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)