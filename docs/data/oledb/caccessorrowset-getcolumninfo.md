---
title: "CAccessorRowset::GetColumnInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
dev_langs: C++
helpviewer_keywords: GetColumnInfo method
ms.assetid: 8ade2388-3c58-43cd-8ed6-499ee0531291
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6a9503f02d5cf7c98f98a31d250e3412b6afec07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorrowsetgetcolumninfo"></a>CAccessorRowset::GetColumnInfo
Возвращает сведения о столбцах из открытого набора строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetColumnInfo(  
   DBORDINAL* pulColumns,  
   DBCOLUMNINFO** ppColumnInfo,  
   LPOLESTR* ppStrings   
) const;  
HRESULT GetColumnInfo(  
   DBORDINAL* pColumns,  
   DBCOLUMNINFO** ppColumnInfo   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Пользователь должен освободить сведения возвращаемого столбца и строки буфера. Использовать второй версии данного метода, при использовании [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) и нуждаются в переопределении привязок.  
  
 Дополнительные сведения см. в разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CAccessorRowset](../../data/oledb/caccessorrowset-class.md)