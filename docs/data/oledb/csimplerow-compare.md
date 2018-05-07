---
title: CSimpleRow::Compare | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d79e753f1f4af630c26ef07fbb7241576535ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Сравнивает две строки, чтобы увидеть, если они ссылаются на один и тот же экземпляр строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
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