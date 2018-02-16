---
title: "CRowset::IsSameRow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset::IsSameRow
- CRowset.IsSameRow
- IsSameRow
- ATL::CRowset::IsSameRow
- ATL.CRowset.IsSameRow
- CRowset<TAccessor>::IsSameRow
- ATL.CRowset<TAccessor>.IsSameRow
- CRowset<TAccessor>.IsSameRow
- ATL::CRowset<TAccessor>::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IsSameRow method
ms.assetid: 53cba847-52f5-4dd9-973f-bbe7454c425c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c5533361ad27f77b2bd0715fcd9b386e3b28598
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetissamerow"></a>CRowset::IsSameRow
Сравнивает указанной строки с текущей строкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT IsSameRow(HROW hRow) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `hRow`  
 [in] Дескриптор строки для сравнения с текущей строкой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. `S_OK` Указывает, что строки совпадают. Другие значения в разделе [IRowsetIndentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) в *Справочник программиста OLE DB* в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)