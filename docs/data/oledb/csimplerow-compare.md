---
title: "CSimpleRow::Compare | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e49dcc0356c563312c0d73041ab412716694c1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Сравнивает две строки, чтобы увидеть, если они ссылаются на один и тот же экземпляр строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRow`  
 Указатель на объект `CSimpleRow`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение обычно `S_OK`, две строки имеют тот же экземпляр строки, позволяющее определить, или **S_FALSE**, две строки, указывающее, отличаются. В разделе [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) в *Справочник программиста OLE DB* для другие возможные возвращаемые значения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [CSimpleRow-класс](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)