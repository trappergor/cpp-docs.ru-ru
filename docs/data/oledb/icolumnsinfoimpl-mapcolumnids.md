---
title: IColumnsInfoImpl::MapColumnIDs | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
dev_langs:
- C++
helpviewer_keywords:
- MapColumnIDs method
ms.assetid: 7aa2d011-75ba-440a-bafe-ab8fccd16dfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4407e9f2e6aa70f43af2659775517588f503c52f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099645"
---
# <a name="icolumnsinfoimplmapcolumnids"></a>IColumnsInfoImpl::MapColumnIDs
Возвращает массив порядковых номеров столбцов в наборе данных, идентифицируются по заданному столбцу идентификаторов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,  
   const DBID rgColumnIDs[],  
   DBORDINAL rgColumns[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IColumnsInfo::MapColumnIDs](https://msdn.microsoft.com/en-us/library/ms714200.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)   
 [IColumnsInfoImpl::GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)